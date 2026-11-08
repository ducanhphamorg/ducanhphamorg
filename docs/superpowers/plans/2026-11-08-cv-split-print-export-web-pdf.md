# CV Split Print and Export Web PDF Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Split the existing "Print / Export Web PDF" into two separate functions in the CV dropdown menu ("Export Web PDF (Standard A4)" and "Print CV (Printer / Paper)"), bringing the total displayed functions to 4, and optimize `@media print` CSS and JS font pre-loading to prevent font errors, color loss, and layout misalignment.

**Architecture:** Update `img/CV/My_CV.html` with:
1. Enhanced `@media print` CSS (`@page { size: A4 portrait; margin: 0; }`, `-webkit-print-color-adjust: exact !important; print-color-adjust: exact !important;`, exact 210mm x 297mm sheet clamping, zero margin overflow protection).
2. Four distinct dropdown items inside `#download-menu`:
   - `Download Original PDF (LaTeX A4)`
   - `Export Web PDF (Standard A4)`
   - `Print CV (Printer / Paper)`
   - `Copy Shareable Online Link`
3. Dedicated JavaScript handler `exportWebPdf()` that ensures web fonts (`document.fonts.ready`) and images are loaded, sets optimal PDF document title (`Pham_Duc_Anh_CV`), provides helpful toast guidance, and opens the PDF export dialog.
4. Dedicated JavaScript handler `triggerPrintCv()` that opens the standard physical print dialog.

**Tech Stack:** HTML5, CSS3 (`@media print`, CSS Grid/Flexbox), JavaScript (DOM, Web Fonts API, Canvas/Print API).

## Global Constraints
- Strictly 4 items displayed in the download/action dropdown menu.
- Perfect vector PDF fidelity (exact colors, crisp avatar photo, zero column shifting, zero orphan page).
- Git Author: Strictly `ducanhphamorg <ducanh040202003@gmail.com>`.
- Plaintext password must never appear anywhere in source files.

## Review Focus
1. `document.fonts.ready` support in diverse browser environments (fallback gracefully if `document.fonts` is undefined).
2. Document title restoration: restore original `document.title` cleanly after print/export dialog closes (`window.onafterprint` or timeout).
3. Dropdown UI layout: min-width and styling to comfortably accommodate the 4 distinct action rows without overflow.
4. Existing test suite compatibility: maintain 100% pass rate across all 4 verification tests.

---

### Task 1: Update `@media print` CSS & Add `exportWebPdf()` Function

**Files:**
- Modify: `img/CV/My_CV.html`

- [ ] **Step 1: Enhance `@media print` CSS for exact A4 formatting & color preservation**
Add `-webkit-print-color-adjust: exact !important; print-color-adjust: exact !important;` to body and all CV elements. Set `@page { size: A4 portrait; margin: 0; }` and clamp `.cv` to `210mm x 297mm` with `overflow: hidden !important;`.

- [ ] **Step 2: Add 4 items in `#download-menu` in `img/CV/My_CV.html`**
Update `#download-menu` with:
1. `Download Original PDF (LaTeX A4)`
2. `Export Web PDF (Standard A4)` (`onclick="exportWebPdf()"`)
3. `Print CV (Printer / Paper)` (`onclick="triggerPrintCv()"`)
4. `Copy Shareable Online Link` (`onclick="copyShareCvLink()"`)

- [ ] **Step 3: Implement `exportWebPdf()` in JavaScript**
Implement `exportWebPdf()` with `closeDownloadDropdown()`, `document.fonts.ready` check, temporary document title switch, toast feedback, and `window.print()` trigger.

---

### Task 2: Verify & Update Test Suites

**Files:**
- Modify: `scratch/test_dropdown_hotkeys.js`

- [ ] **Step 1: Update `scratch/test_dropdown_hotkeys.js` to assert all 4 dropdown items and test `exportWebPdf()`**
- [ ] **Step 2: Run all 4 test suites to verify 100% PASS**
Run:
`node scratch/test_dropdown_hotkeys.js`
`node scratch/test_e2e_logic.js`
`node scratch/test_edge_fixes.js`
`node scratch/verify_repo.js`

---

### Task 3: Commit and Push to Main

- [ ] **Step 1: Git stage, commit with required author and push to origin main**
