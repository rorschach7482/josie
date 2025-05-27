**Implementation Plan – Smart Document Assistant (V1)**

---

## 🚀 Project Scope

The goal is to build a lightweight, privacy-first AI assistant that integrates with Google Drive, indexes selected folders, and enables fast document retrieval via conversational search. This plan breaks down development into 3 phases optimized for simplicity, scalability, and low bug surface.

---

## ✅ Phase 1: Core Infrastructure & Permissions

**Objective:** Set up auth, Google Drive access, and backend architecture.

### Step 1.1 – Google Sign-In Integration

* Implement OAuth flow using Google Identity Services
* Secure access token storage and refresh handling

### Step 1.2 – Folder Selection UI

* Let user browse and pick a Drive folder (no full Drive scan)
* Store folder ID in user profile in Supabase

### Step 1.3 – File Fetching Logic

* Fetch metadata (name, ID, MIME type, created/modified date)
* Limit to first 100 files for free tier

### Step 1.4 – Database Schema Setup (Supabase)

* Users table
* Documents table (with summary, tags, history)

---

## 🤖 Phase 2: Indexing + AI Assistant

**Objective:** Process files, extract insights, and enable chat-based retrieval.

### Step 2.1 – Background Indexing Worker

* Trigger on folder confirmation
* Fetch and parse file content (PDFs, Docs)
* Send to OpenAI for summary + tagging
* Store metadata in Supabase

### Step 2.2 – Progress Tracking

* Display progress bar in-app
* Update every 5–10 files processed

### Step 2.3 – Chat Interface

* Implement left-hand chat panel
* Allow user to ask natural questions

### Step 2.4 – Search Matching Logic

* Process query
* Rank matches based on file content, tags, and recency

### Step 2.5 – Results Panel

* Right-hand panel shows:

  * Document title + icon
  * Summary (from AI)
  * Tags
  * Mini file history
  * "Open in Drive" link

---

## 🗃️ Phase 3: Preview UI + Polishing

**Objective:** Finalize file preview UX, limits, and onboarding polish.

### Step 3.1 – Document Preview Panel

* Slide-in or modal preview for selected file
* Show:

  * Summary
  * Tags
  * History (renamed/moved)
  * Drive button

### Step 3.2 – Free Tier Enforcement

* Block scan/search after:

  * 100 docs scanned OR
  * 100 queries used
* Prompt to upgrade (copy only; no billing for V1)

### Step 3.3 – Empty + Edge States

* No files found
* Invalid file types
* Nothing matches search

### Step 3.4 – Final QA + Deployment

* Manual testing of all flows
* Supabase rules + Drive scope review
* Launch to selected test group

---

## ⚠️ Notes

* No file editing, moving, or renaming
* No notifications or reminders in V1
* No admin role or multi-user collaboration

This implementation plan is designed to get a minimal, clean, working MVP shipped efficiently with low technical risk.
