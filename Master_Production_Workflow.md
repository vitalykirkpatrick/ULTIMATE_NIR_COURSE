# Master Production Workflow v2.0 (Learning-Optimized)

This document outlines the official, learning-optimized workflow for creating all course lessons. This process is designed to maximize student comprehension and retention by following dual-channel learning principles.

---

## **Core Philosophy: Narration-First, Content-Rich Design**

We create the complete learning experience for a slide (narration + visuals + text) as a single, cohesive unit. The narration guides the visual design, and the on-screen text reinforces the narration.

---

## **The 10-Step Production Workflow**

### **Phase 1: Content Creation (The Foundation)**

**Step 1: Write the Narration Script (95+ words)**
- **Objective:** Create a compelling, structured narrative for the slide.
- **Process:** Follow the v2.1 strict system:
    - **Hook:** Grab the student's attention.
    - **Body:** Explain the core concept.
    - **Bridge:** Connect to the next idea.
- **Output:** A complete, 95+ word narration script for a single slide.

**Step 2: Extract Key On-Screen Text**
- **Objective:** Identify the most critical information from the narration to display visually.
- **Process:** Review the narration script and pull out:
    - Key phrases and definitions
    - Important bullet points
    - Data points or statistics
    - The core takeaway message
- **Output:** A concise set of text that will be integrated into the slide image.

### **Phase 2: Visual Design & Generation**

**Step 3: Design the Slide Visuals**
- **Objective:** Create a visual concept that complements the narration and on-screen text.
- **Process:** Based on the narration and key text, design a visual that:
    - Reinforces the core concept (e.g., a bridge for "analyst as a bridge")
    - Follows the Design DNA (thematic background, two-column layout, etc.)
    - Incorporates the on-screen text in a clear, readable way.
- **Output:** A detailed design concept for the slide.

**Step 4: Generate the Slide Image**
- **Objective:** Create the final, high-quality slide image.
- **Process:** Use the `generate_image` tool with a detailed prompt that includes:
    - The design concept from Step 3.
    - The on-screen text from Step 2.
    - All relevant design standards (colors, fonts, layout).
- **Output:** A final, 1280x720 WebP slide image.

### **Phase 3: Audio & Content Pages**

**Step 5: Generate the Narration Audio**
- **Objective:** Create the high-quality audio for the slide.
- **Process:** Use the `generate_speech` tool with the narration script from Step 1.
- **Output:** A final MP3 audio file.

**Step 6: Write the HTML Content Page**
- **Objective:** Create the detailed, long-form written content for the lesson.
- **Process:** Expand on the narration script with:
    - In-depth explanations
    - Real-world examples
    - Case studies
    - Explanatory images (white background)
- **Output:** A complete HTML file for the lesson's content page.

### **Phase 4: Assembly & Quality Control**

**Step 7: Assemble the Lesson Package**
- **Objective:** Organize all lesson assets into a clean folder structure.
- **Process:** Create a folder for the lesson and place all assets inside:
    - `slides/` (all slide images)
    - `narrations/` (all audio files)
    - `content.html`
    - `supplemental_materials/` (quizzes, worksheets, etc.)
- **Output:** A complete, organized lesson package.

**Step 8: Perform QC Check**
- **Objective:** Ensure all assets meet the established quality standards.
- **Process:** Use the Master QC System checklist to review:
    - Slide design consistency
    - Narration audio quality
    - HTML content accuracy
    - File naming conventions
- **Output:** A QC-approved lesson package.

### **Phase 5: Final Delivery**

**Step 9: Upload to All Platforms**
- **Objective:** Back up all lesson assets to the cloud.
- **Process:** Upload the complete lesson package to:
    - Google Drive
    - S3
    - GitHub
- **Output:** All assets securely stored and versioned.

**Step 10: Deliver to User**
- **Objective:** Present the completed lesson to the user for final approval.
- **Process:** Use the `message` tool to deliver the lesson package with a summary of the work completed.
- **Output:** A happy user!
