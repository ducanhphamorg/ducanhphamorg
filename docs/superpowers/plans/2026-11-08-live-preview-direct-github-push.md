# Direct GitHub Push & Interactive Live Preview Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the manual "Copy HTML & Open GitHub Commit" workflow with an automated, 1-click Direct GitHub API Push that verifies the `@ducanhphamorg` account, and replace the hidden/obstructed live preview with an interactive Peek Preview mode featuring a floating control bar.

**Architecture:** Update `img/CV/My_CV.html` with:
1. Interactive Peek Preview:
   - When clicking `👁️ Live Preview`, close/minimize `#editor-modal`, scroll smoothly to `#cv-sheet`, and activate `#cv-preview-bar` (a fixed floating action bar at the bottom containing `✏️ Back to Editor` and `🚀 Push to GitHub`).
2. 1-Click Direct GitHub API Push:
   - Replace the manual copy-paste button with `🚀 Push to GitHub (@ducanhphamorg)`.
   - `directPushToGitHub()` performs automated git push:
     - Prompts for GitHub Personal Access Token (classic `repo` scope) if not already saved in session.
     - Validates token against `https://api.github.com/user` ensuring user is `@ducanhphamorg`.
     - Fetches existing file SHA via `GET https://api.github.com/repos/ducanhphamorg/ducanhphamorg/contents/img/CV/My_CV.html`.
     - Serializes updated HTML with proper UTF-8 Base64 encoding.
     - Commits changes directly to `main` via `PUT https://api.github.com/repos/ducanhphamorg/ducanhphamorg/contents/img/CV/My_CV.html`.
     - Displays realtime commit feedback and status toast.
3. Token Prompt Modal (`#token-modal`):
   - User-friendly dialog explaining token creation with 1-click shortcut link to GitHub token generation page with `repo` scope pre-selected.
   - Token is stored in `sessionStorage` for the duration of the browsing session.

**Tech Stack:** HTML5, CSS3 (Floating Bar, Animation), JavaScript (DOM API, GitHub REST API v3, UTF-8 Base64, Crypto).

## Global Constraints
- Only authenticated owners (`isOwnerAuthenticated() === true`) can initiate GitHub push.
- Token must belong to `@ducanhphamorg` (enforced via API check).
- Zero external libraries; must work 100% on `htmlpreview.github.io` and standard browsers.
- Git Author: Strictly `ducanhphamorg <ducanh040202003@gmail.com>`.

## Review Focus
1. UTF-8 Base64 encoding: Vietnamese characters and special Unicode symbols in `img/CV/My_CV.html` must not be corrupted during base64 encoding (`btoa(unescape(encodeURIComponent(str)))`).
2. SHA synchronization: Ensure current file SHA is freshly queried immediately before `PUT` to prevent `409 Conflict`.
3. Floating preview bar usability: Must stay visible without obstructing CV content on both desktop and mobile viewports.
4. Existing test suites in `scratch/` must pass 100%.

---

### Task 1: Create Floating Preview Bar UI & Peek Preview Mode

**Files:**
- Modify: `img/CV/My_CV.html`

- [ ] **Step 1: Add CSS and HTML for `#cv-preview-bar`**
Add `#cv-preview-bar` floating at the bottom with buttons `✏️ Back to Editor`, `🚀 Push to GitHub`, and `✖ Exit`.
- [ ] **Step 2: Update `applyFormToPreview()` to hide modal and show `#cv-preview-bar`**
- [ ] **Step 3: Implement `returnToEditor()` and `exitPreviewMode()`**

---

### Task 2: Implement Direct GitHub API Push & Token Prompt Modal

**Files:**
- Modify: `img/CV/My_CV.html`

- [ ] **Step 1: Add `#token-modal` dialog for first-time Token input**
- [ ] **Step 2: Implement `directPushToGitHub()` and `saveTokenAndPush()`**
- [ ] **Step 3: Replace manual copy button in modal footer with `🚀 Push to GitHub`**

---

### Task 3: Verify and Update Automated Tests

**Files:**
- Modify: `scratch/test_dropdown_hotkeys.js`

- [ ] **Step 1: Add automated tests for Peek Preview mode and Direct GitHub Push**
- [ ] **Step 2: Run all 4 test suites to verify 100% PASS**

---

### Task 4: Commit and Push to Main

- [ ] **Step 1: Stage, commit with author `ducanhphamorg <ducanh040202003@gmail.com>`, and push to `origin main`**
