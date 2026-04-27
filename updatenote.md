## Update Notes

======================================================================================================================================
**New update Apr 27**

1. **Idea Details Page:** Add a click action to each idea block to navigate to its own dedicated page. Design the layout for these individual idea pages.
2. **Update Feature:** Implement the ability to update/edit an existing idea.
3. **Delete/Modify:** Add functionality to delete and modify ideas.
4. **Sorting:** Implement sorting capabilities for the ideas list.
5. **References Section:** Add a references section to each idea to store and manage related external links.
6. **Image Upload:** Update or implement the image upload feature.
7. **Bug Fix:** Fix the "Add Idea" feature (currently broken/unclickable).

======================================================================================================================================
**New update Apr 27 12:21 PM**

# Project: Jasverine's Creative Hall - Development Roadmap

## 📋 Project Overview
A personal idea hosting website built with a static frontend, intended for deployment on GitHub Pages with a GitHub-based "database" (JSON/HTML files).

---

## ✅ Completed Tasks
* **Item 2 (Update Feature):** Implemented the ability to update and edit existing ideas.
* **Item 3 (Delete/Modify):** Added functionality to delete and modify ideas from the system.
* **Item 4 (Sorting):** Implemented sorting capabilities to organize the ideas list.
* **Item 5 (References Section):** Added a dedicated section within each idea to store and manage external reference links.
* **Item 6 (Image Upload - UI):** Developed the interface for users to select and upload images.
* **Item 7 (Bug Fix - Add Idea):** Resolved the issue where the "Add Idea" button was unresponsive.

---

## ⏳ Pending Tasks
* **Item 1 (Idea Details Page):** Create a dedicated navigation flow and layout for viewing full idea details.

---

## 🐛 Known Issues & Action Items

### 1. Routing & Navigation (Critical)
* **Issue:** Clicking on an idea block currently triggers a **404 Error**.
* **Action Required:** Redesign the routing logic. Ensure that when a new idea is created, the corresponding HTML/Markdown file is correctly generated or the dynamic route is properly handled to display the full content.

### 2. Image Persistence & Organization (High)
* **Issue:** Uploaded images disappear after a page reload because they are only stored in volatile memory.
* **Action Required:** * Integrate GitHub REST API to commit images directly to the repository.
    * **Workflow:** When an image is uploaded, the system must automatically create a subdirectory in `/image/` named after the `Idea_ID`.
    * Store the image within that specific folder to ensure permanent hosting.

### 3. UI Display (Medium)
* **Issue:** Cover images/thumbnails are not appearing when the website is in **Grid View**.
* **Action Required:** Debug the data-binding between the image file path in the database and the CSS/HTML `<img>` tags in the grid component.

---

## 💡 Technical Recommendations & Refinements

### 1. Database Refactoring (Activity Log)
To improve tracking and maintainability, the database schema should be updated to include an **Audit Trail**.
* **Structure:** Every idea and category should have an associated `activity_log` array.
* **Tracked Events:** Creation date, edit timestamps, status changes (e.g., Draft to Published), and deletion logs.

======================================================================================================================================
**New update Apr 27 12:27 PM**

### 2. New Data Architecture (Folder-based Storage)
Refactor the storage system to use a structured folder hierarchy for better asset management and scalability.

* **Folder Structure:** Each individual idea will have its own dedicated directory at `data/[idea_id]/`.
    * This folder will contain all associated assets: text content, images, and any other idea-specific files.
* **Centralized Metadata (Summary JSON):** A master JSON file (e.g., `data/summary.json`) will be implemented to act as the primary database for the website's index.
    * **Fields included:** `id`, `title`, `tag`, `categories`, `created_date`, `modified_date`, `cover_image_path`, etc.
    * **Purpose:** This allows the website to load the Grid View and search features instantly without having to scan every individual idea folder.

**Proposed Directory Mapping:**
```text
/root
  /data
    /summary.json (Master metadata list)
    /DS-2024-001 (Idea Folder)
       - content.html/md
       - image1.jpg
       - references.json
    /AI-2024-005 (Idea Folder)
       - content.html/md
       - cover.png
```