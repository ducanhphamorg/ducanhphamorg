# Smart CV Editor Form & Formatting Helper Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Transform the Owner Editor Modal into a user-friendly, structured Smart Form with a mini Format Toolbar (`Bold`, `Bullet`, `Number`, `Clear`), split single-string fields (Achievements, Languages) into structured inputs with zero special character requirements, strictly enforce Owner Authentication before allowing any editing, and streamline the Live Preview ➔ GitHub Commit workflow.

**Architecture:** Update `img/CV/My_CV.html` with:
1. Strict Security Guard: `openEditorModal()` checks `if (!isOwnerAuthenticated()) { openAuthModal(); return; }`.
2. Format Toolbar Helper: `applyTextFormat(elementId, formatType)` providing 1-click `Bold`, `Bullet`, `Number`, and `Clear` for any textarea/input without typing markdown manually.
3. Structured Fields:
   - Achievement: Split into `f-ach-title` (Title) and `f-ach-sub` (Subtitle/Program).
   - Languages: Split into `f-lang-name` (Language) and `f-lang-level` (Level selector/input with presets).
   - Skills: Add Format Toolbar and helper insertion buttons (`+ Add Technical Skill`, `+ Add Soft Skill`).
   - Projects: Add Format Toolbar for each project's description textarea.
4. Smooth Preview & Commit: Clear status messages and streamlined buttons (`👁️ Live Preview`, `🐙 Copy & Commit to GitHub`, `💾 Download My_CV.html`).

**Tech Stack:** HTML5, CSS3 (Flexbox/Grid, Toolbars), JavaScript (DOM Text Selection API, Regex, Crypto SHA-512).

## Global Constraints
- Only authenticated owners (`isOwnerAuthenticated() === true`) can open or edit the CV form.
- No heavy external third-party libraries (Quill, TinyMCE, etc.) to ensure 100% offline & `htmlpreview.github.io` sandboxed iframe compatibility.
- Git Author: Strictly `ducanhphamorg <ducanh040202003@gmail.com>`.
- Plaintext password must never appear in any code or file.

## Review Focus
1. Unauthenticated access prevention: verify `openEditorModal()` strictly redirects to `openAuthModal()` when `isOwnerVerified` is false.
2. Selection range handling: `applyTextFormat()` must correctly wrap selection or insert template at cursor and restore selection focus across Edge/Chrome.
3. Backward compatibility with template JSON: `collectFormData()` and `populateEditorForm()` must seamlessly handle existing CV template data without data loss.
4. All existing tests in `test_dropdown_hotkeys.js`, `test_e2e_logic.js`, `test_edge_fixes.js`, and `verify_repo.js` must pass 100%.

---

### Task 1: Add Format Toolbar CSS & Text Formatting Engine in JavaScript

**Files:**
- Modify: `img/CV/My_CV.html`

- [ ] **Step 1: Add CSS for `.fmt-toolbar`, `.fmt-btn`, and enhanced form field groups**
- [ ] **Step 2: Implement `applyTextFormat(targetId, type)` supporting `bold`, `bullet`, `number`, and `clear`**
- [ ] **Step 3: Add strict authentication check inside `openEditorModal()`**

---

### Task 2: Redesign Form Fields & Toolbar Integration in HTML

**Files:**
- Modify: `img/CV/My_CV.html`

- [ ] **Step 1: Replace raw Achievement input with split `f-ach-title` & `f-ach-sub`**
- [ ] **Step 2: Replace raw Language input with structured `f-lang-name` & `f-lang-level`**
- [ ] **Step 3: Attach Format Toolbar to `f-about`, `f-skills`, and project descriptions**
- [ ] **Step 4: Update `populateEditorForm()` and `collectFormData()` to map the new structured fields**

---

### Task 3: Verify with Automated Tests

**Files:**
- Modify: `scratch/test_edge_fixes.js` & `scratch/test_dropdown_hotkeys.js`

- [ ] **Step 1: Add tests verifying unauthenticated `openEditorModal()` is blocked**
- [ ] **Step 2: Add tests verifying `applyTextFormat()` handles bold, bullet, and number formatting**
- [ ] **Step 3: Run all 4 verification test suites and verify 100% PASS**

---

### Task 4: Commit and Push to Main

- [ ] **Step 1: Stage, commit with author `ducanhphamorg <ducanh040202003@gmail.com>` and push to `origin main`**
