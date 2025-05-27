## 📄 App Overview

An AI-powered assistant that connects to a user's Google Drive, scans and organizes selected folders, and enables lightning-fast document retrieval through natural language chat. The app does not store documents, only metadata, and offers a clean, split-view interface that feels like a command center for personal documents.

---

## 🌎 Target Audience

* Busy professionals with cluttered Google Drives
* Individuals managing personal/family documents (IDs, contracts, insurance)
* Users frustrated with poor search and disorganization in cloud storage

---

## 🔹 Core Features (V1)

1. **Google Sign-In Only**

   * Authenticates users and enables Drive access

2. **Folder-Based Drive Connection**

   * Users choose which folder to scan

3. **Background Indexing**

   * AI processes files to extract summaries, tags, and metadata
   * Progress bar shown during scan

4. **Conversational Search (Chat-First UI)**

   * Users type questions like "Show me Alex's passport"
   * Assistant returns document results with summaries and context

5. **Split View Interface**

   * Left: Chat window
   * Right: Document results

6. **Document Preview Panel**

   * Inline viewer with:

     * AI-generated summary
     * Tags
     * File history (renamed, moved, etc.)
     * "Open in Drive" button

7. **Manual Upload via Drive Only**

   * No upload inside the app
   * Files must be added to Drive folders

8. **Free Tier Limitations**

   * 100 documents indexed
   * 100 chat queries

---

## 🚀 High-Level Technical Stack (Recommended)

* **Frontend:** React + Shadcn UI + Tailwind CSS
* **Backend:** Supabase (Postgres + Auth + Storage)
* **AI Layer:** OpenAI (GPT-4-Turbo or 3.5-turbo for summaries)
* **File API:** Google Drive SDK (read-only)

---

## 🔢 Conceptual Data Model

**Documents Table:**

* File ID
* Name
* Folder path
* Summary
* Tags
* History (renamed, moved)

**Users Table:**

* User ID
* Google email
* Folder connected
* # of docs scanned
* # of queries used

---

## 🎨 UI/UX Principles

* Clean, distraction-free UI
* Focused on clarity, not features
* Language is helpful, human, and confident
* Everything leads back to the search

---

## 🔐 Security Considerations

* Use Google OAuth scopes responsibly (read-only)
* Never store actual documents
* Clear user messaging on what is accessed and how
* Encrypt metadata in database

---

## ✅ Development Phases

**Phase 1: Foundation**

* Google Sign-In + Folder selection
* Drive file access + metadata extraction

**Phase 2: AI + Search Core**

* Indexing flow
* Chat UI with search and result display

**Phase 3: Preview & UX Polish**

* Document preview panel
* Progress UI, Open in Drive
* Limits + edge handling

---

## ⚠️ Potential Challenges & Solutions

* **Trust barrier:** Use metaphors, visuals, and privacy-first language
* **Slow indexing:** Show progress bar, prioritize key documents
* **Bad search results:** Allow feedback and continual improvement
