
# NIR Course Production: HTML Content Page Standards

**Version 1.0 | Last Updated: January 12, 2026**

---

## 1. Guiding Philosophy: The Digital Textbook

The HTML content page serves as the "digital textbook" for each lesson. It complements the video lecture by providing:

-   **Deeper Dives:** More detailed explanations, data tables, and background information.
-   **Visual Clarity:** High-quality, annotated images that break down complex concepts.
-   **Accessibility:** A text-based alternative for students who prefer reading or have hearing impairments.
-   **A Searchable Resource:** A place for students to quickly find specific terms or concepts.

The design must be clean, professional, and prioritize readability above all else.

---

## 2. Page Structure

Every HTML content page must follow this standard structure:

1.  **Lesson Title (`<h1>`):** The full title of the lesson.
2.  **Key Takeaway (`<blockquote>`):** A single, powerful sentence that summarizes the most important concept from the lesson.
3.  **Introduction (`<p>`):** A short paragraph that sets the stage for the content, mirroring the "Hook" from the narration.
4.  **Main Body (Headings `<h2>`, `<p>`, `<ul>`):**
    -   The core content of the lesson, broken down into logical sections with `<h2>` headings.
    -   Use paragraphs (`<p>`) for explanations and unordered lists (`<ul>`) for key points.
    -   This section should expand on the narration, not just repeat it.
5.  **Explanatory Images (`<img>` with `<figure>`):**
    -   Integrate high-quality images throughout the body to illustrate concepts.
6.  **Summary (`<h2>` and `<ul>`):**
    -   A final section titled "Summary" with 2-4 bullet points that recap the key learning objectives.

---

## 3. Image Requirements

Images are the most critical component of the HTML page.

-   **Purpose:** All images must be *explanatory*. They are not decoration. They must be created specifically to illustrate a concept from the lesson.
-   **Background:** All explanatory images **must be on a clean, white background (`#FFFFFF`)**. This ensures consistency and focus.
-   **Annotations:** Use clear text overlays, arrows, and callouts directly on the image to explain different parts of a diagram, chart, or concept. Use the standard **Lato** font.
-   **Quality:** Images must be high-resolution and saved in **PNG or JPEG format**.
-   **Captions:** Every image must be wrapped in a `<figure>` tag with a `<figcaption>` that clearly describes what the image is showing.

**Example of a good explanatory image:** A diagram of an NIR instrument with each component (source, monochromator, detector) clearly labeled with text and arrows, all on a plain white background.

---

## 4. Markup & Formatting (HTML)

-   **Semantic HTML:** Use proper semantic tags (`<h1>`, `<h2>`, `<p>`, `<ul>`, `<li>`, `<blockquote>`, `<figure>`, `<figcaption>`). Do not use `<div>` for everything.
-   **Bold (`<strong>`):** Use `<strong>` to emphasize key terms and concepts (e.g., **chemometrics**, **overtones**). Do not overuse it.
-   **Clean Code:** The HTML should be well-formatted and easy to read.
-   **No Inline Styles:** Do not use inline `style="..."` attributes. All styling will be handled by the learning platform's global CSS.

---

## 5. The Workflow for Creation

1.  **Start with the Narration Script:** The HTML page is an extension of the narration.
2.  **Identify Key Concepts for Visuals:** Read through the script and identify the 2-3 most complex ideas that would benefit from an explanatory image.
3.  **Create the Images:** Design the high-quality, annotated images on a white background.
4.  **Write the Text:** Write the body content, expanding on the narration and referencing the images you created.
5.  **Assemble the HTML:** Combine the text and images into a clean, semantic HTML file.

This process ensures that the text and visuals are perfectly aligned and that the final page is a cohesive, high-value learning asset.
