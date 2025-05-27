**App Flow, Pages, and Roles (V1)**

---

## 🚀 Core Experience Summary

All users are equal — no admin roles. The app is designed around a single user connecting their Google Drive, selecting a folder, and using AI-powered search to find documents.

---

## 🔎 Pages & States

### 1. **Landing Page (`/`)**

* Value proposition
* CTA: “Sign in with Google”

### 2. **Onboarding (`/onboarding` or modal flow)**

* Google OAuth authentication
* Step 1: Permission scope request
* Step 2: Select folder from Drive
* Step 3: Confirm folder → trigger indexing
* Final: Progress screen with scan status

### 3. **Dashboard (`/app`)**

Split into two main panels:

#### Left: Chat Panel

* Chat log
* Chat input (natural language)
* Prompts (e.g., “Try: Show me my passport”)

#### Right: Results Panel

* List of document cards (matching query)
* Each card shows:

  * Title
  * AI-generated summary
  * Tags (badges)
  * History notes (renamed, moved)
  * “Open in Drive” button

### 4. **Preview Panel (Slide-over or Modal)**

* Opens when user clicks a result
* Includes:

  * Summary
  * Tags
  * File history
  * Drive button

### 5. **Progress View (`/indexing` or overlay modal)**

* Shown during initial folder scan
* “Scanning 37 of 100 files…”
* Updates dynamically
* Auto-redirects to `/app` when done

### 6. **Usage Limit Reached (`/upgrade` or inline prompt)**

* Triggered at 100 files or 100 chat queries
* Copy-only upgrade screen (no billing in V1)

### 7. **Error States & Edge Screens**

* No files found
* Invalid folder selected
* API errors
* Google access revoked

---

## 📅 App Flow Summary (Step-by-Step)

1. User lands on homepage
2. Signs in with Google
3. Selects folder
4. Confirms indexing
5. Views progress bar
6. App notifies when ready
7. Enters chat, asks a question
8. Views results in right panel
9. Clicks a file → opens preview
10. Repeats until usage limit is hit
11. Sees upgrade prompt (if exceeded)

---

## 🔑 User Roles

* **Single role: Basic user**
* No admin panel or sharing functionality
* All metadata and actions are user-scoped only

---

This flow ensures that users feel guided, secure, and supported through a focused document retrieval experience — with zero distractions from non-core features.
