**Design Guidelines (V1)**

---

## 🎨 Design Principles

* **Clarity over cleverness:** Prioritize legibility and confidence
* **Calm UI:** Soft tones, clean spacing, low visual noise
* **Trust by design:** Respectful microcopy, privacy-focused UI
* **Chat is primary, results are critical** – everything revolves around that relationship

---

## 🖌️ Colors (Tailwind-based)

| Purpose          | Value                 |
| ---------------- | --------------------- |
| Primary (brand)  | `#2563EB` (blue-600)  |
| Background       | `#F9FAFB` (gray-50)   |
| Foreground text  | `#111827` (gray-900)  |
| Subtle text      | `#6B7280` (gray-500)  |
| Panel BG         | `#FFFFFF` (white)     |
| Border / divider | `#E5E7EB` (gray-200)  |
| Tag background   | `#EEF2FF` (indigo-50) |

---

## ✏️ Typography

* **Font:** Inter (system fallback: `sans-serif`)
* **Sizes:**

  * `text-xl` for section titles
  * `text-base` for body
  * `text-sm` for meta/notes
* **Font weight:**

  * Semibold for labels and summaries
  * Regular for body

---

## □ Spacing & Layout

* **Container padding:** `p-6` or `p-8`
* **Grid gap:** `gap-4` or `gap-6`
* **Chat layout:** `flex-col h-full` (scrollable area, sticky input)
* **Results panel:** Fixed width or responsive min-w-\[400px]

---

## 🛏️ Components (Shadcn UI)

### Buttons

* `Button` (primary): solid blue-600, white text
* `Button` (secondary): border-gray-300, text-gray-700
* `IconButton`: for Drive links or quick actions (rounded-md, hover\:bg-gray-100)

### Chat Input

* Uses `Textarea` with auto-grow
* Submit on `Enter`, newline with `Shift+Enter`

### Document Card (Result)

* `Card` with border, subtle shadow
* Includes:

  * Title
  * Summary
  * Tags (`Badge`)
  * Mini history row
  * “Open in Drive” icon/button

### Preview Panel

* `Sheet` or modal with tabs or sections:

  * Summary
  * Metadata
  * File history

### Others

* `Tooltip` for Drive actions
* `Separator` for dividing summary/history
* `Skeleton` states for loading results

---

## 🔍 Interactions & Feedback

* **Hover:** subtle bg (`hover:bg-gray-50`)
* **Focus state:** strong border (`focus:ring-2 focus:ring-blue-500`)
* **Loading:** `Spinner` during AI queries and indexing
* **Empty state:** icon + friendly copy (“No matches found yet”)

---

## 🚫 What Not to Include in V1

* Dark mode
* Animations or transitions
* File upload components
* Multi-theme support

This guideline ensures your UI feels modern, functional, and easy to scale — while staying focused on the primary use case of fast document retrieval.
