# NIR Course Design & Architecture (DNA) Template

## 1. Core Philosophy

This document outlines the design and architectural principles for creating a professional, high-tech, and information-rich NIR spectroscopy course. The core philosophy is to teach through visual metaphor, balancing aesthetic beauty with educational clarity. This template is designed to be reusable for the creation of any new professional NIR course.

### 1.1. Key Principle: Information Density

- **Comprehensive Content:** Slides should contain substantial text content (3-5 bullet points, full sentences, detailed explanations), not be minimalist.
- **Synergistic Visuals and Text:** The visual and textual elements of a slide should work together to teach the concept, with each providing a different layer of information.
- **Standalone Learning:** Slides should be designed to be self-contained, allowing students to learn the material even without narration.
- **Example:** A slide about the "Garbage In, Garbage Out" principle should not only visually represent the concept but also include 3-4 bullet points explaining the consequences of poor sample preparation.

---

## 2. Visual Design

### 2.1. Color Palette

| Color | Hex Code | Usage |
|:------|:---------|:------|
| **Dark Navy** | `#001122` | Primary background |
| **Cyan** | `#00D9FF` | Headings, accents, "cool" side of comparisons |
| **Gold/Orange** | `#FFB800` | Key concepts, "warm" side of comparisons |
| **White** | `#FFFFFF` | Body text, labels |
| **Teal Glow** | `#00FFCC` | Glowing lines, waves, highlights |

---

### 2.2. Typography

| Element | Font | Size | Color | Weight |
|:--------|:-----|:-----|:------|:-------|
| **Main Title** | Sans-serif (Inter, Helvetica) | 72-96px | White | Bold (700-900) |
| **Section Label** | Sans-serif | 32px | Cyan | Bold |
| **Subtitle** | Sans-serif | 48px | White | Regular (400) |
| **Key Concepts** | Sans-serif | 36px | Gold | Bold |
| **Body Text** | Sans-serif | 24-28px | White | Regular |
| **Presenter Credit** | Sans-serif | 24px | White | Light (300) |

---

### 2.3. Background Treatment

The background is **never a solid color**. It is a deep, textured 'canyon navy blue' that subtly incorporates thematic elements from the lesson itself. It always includes:

- **Base:** Dark navy (#001122)
- **Thematic Elements:** Faint, 'ghostly' outlines of visuals related to the lesson topic (e.g., wheat stalks for a bread lesson, molecules for a chemistry lesson) are integrated into the navy blue texture. These should be very subtle and not distract from the main content.
- **Glowing Accents:** Soft cyan glows in corners or behind visuals
- **Grid Lines:** Optional faint grid pattern for technical slides

### **CRITICAL VISUAL PROHIBITIONS:**

**NEVER include the following elements in any slide:**
- ❌ **White borders** around the slide or content
- ❌ **Monitor/screen frames** showing content displayed on a device
- ❌ **Theater/presentation mode** effects (slide within a slide)
- ❌ **Device mockups** (laptops, tablets, phones) displaying slide content
- ❌ **Bezels, frames, or borders** that create a "screen within a screen" effect
- ❌ **Office furniture, meeting rooms, or presentation contexts** in the background

**Instead:**
- ✅ Content should fill the entire slide canvas edge-to-edge
- ✅ Backgrounds should be clean, abstract, or contextually relevant (e.g., lab, factory, field)
- ✅ Visual elements should be integrated directly into the slide composition
- ✅ Use depth, lighting, and composition to create visual interest, not artificial frames

---

## 3. Slide Types & Layouts

### **A. Title Slide**
**Purpose:** Introduce the lesson and list Key Concepts.

**CRITICAL VISUAL CONTENT REQUIREMENT:**

**Every title slide MUST include:**
- ✅ **Visual elements that show what the lesson is about** (not just title + text)
- ✅ **Use realistic real-world images WHERE NECESSARY** (equipment, facilities, people, processes)
- ✅ **Use conceptual graphics/icons where appropriate** (abstract concepts, theory, frameworks)
- ✅ **Combination of visuals + text** that represent the lesson content
- ❌ **NOT just title + key concepts text** - must have visual storytelling

**When to use realistic photos:**
- Title slides (set visual context)
- Equipment/instrument demonstrations
- Application examples (grain elevators, dairy facilities, production lines)
- People/processes (analysts working, sampling, testing)
- Real-world scenarios

**When conceptual graphics are appropriate:**
- Abstract scientific concepts (light, molecules, energy)
- Comparisons and contrasts
- Diagrams, flowcharts, timelines
- Data visualizations
- Theoretical frameworks

**Examples:**
- Lesson about instruments → Show actual NIR spectrometer equipment in a lab (realistic photo)
- Lesson about applications → Show real grain elevator or dairy facility (realistic photo)
- Lesson about light & matter → Show conceptual graphics of electromagnetic waves (graphics/icons)
- Lesson about learning journey → Show path/progression with learning milestones (conceptual graphics)

**CRITICAL HEADER AND FOOTER RULES:**

**For ALL Title Slides (Course-Level AND Lesson-Level):**
- ❌ NO header text
- ❌ NO footer text
- ❌ NO "Presented by" credit (instructor already introduced in L00)
- ✅ Just the title content in the center and Key Concepts panel

**For Content Slides Within a Lesson (all slides AFTER the title slide):**
- ✅ Top-left corner: Lesson title in small cyan text (e.g., "Introduction to NIR Spectroscopy")
- ❌ NO Key Concepts panel (only on title slide)
- ❌ NO footer text
- ❌ NO "Presented by" credit
- ❌ NO slide numbers
- ❌ NO lesson numbers on slides (e.g., "L02" or "Lesson 2")

**Lesson Numbering Policy:**
- Lesson numbers are used in **file naming** (e.g., `L02_What_is_Analytical_Chemistry.mp4`)
- Lesson numbers appear in the **platform interface** (course navigation, LMS, website)
- Lesson numbers are in **video titles and metadata**
- **Slides remain clean** with only the lesson title in top-left corner (e.g., "What is Analytical Chemistry?")
- This follows Coursera and MOOC best practices: platform handles navigation, slides stay professional and reusable

**Key Concepts Panel:**
- Appears ONLY on the title slide
- NOT on content slides

**Layout:**
- **Center-Top:** Main lesson title (White, large, bold)
- **Left Side:** 3D visualization or realistic photo related to the lesson topic
- **Right Side:** Key Concepts panel (fixed position, consistent across all lessons)
- **NO FOOTER on any slide**

**Key Concepts Panel Specifications:**
- **Location:** Always on the RIGHT side of title slides (fixed position)
- **Visual Treatment:** 
  - Semi-transparent dark panel (#001122 with 70-80% opacity)
  - **SUBTLE cyan/teal GLOW** (#00FFCC or #00D9FF) around the box edges (**4-6px soft glow**, NOT thick border)
  - Rounded corners (8-12px border-radius) for modern look
  - Panel should feel integrated into the slide, not floating
- **Size:** Fixed dimensions across all title slides (approximately 350-400px width × 450-500px height, positioned 60-80px from right edge, 140-160px from top)
- **Header:** "KEY CONCEPTS" in white or cyan (#00D9FF), bold, 24-28px, left-aligned within panel
- **Content Format:** 3-5 bullet points, each with:
  - Small glowing icon to the left (20-24px, cyan #00D9FF, line-art style)
  - Descriptive phrase with **MINIMAL COLOR-CODING** (see COLOR_CODING_STRATEGY.md):
    - **90% of text should be WHITE**
    - Only 1-2 key words per bullet get colored (NOT whole phrases)
    - Many bullets have ZERO colored words (this is intentional and correct)
    - **Cyan (#00D9FF)** - Primary concepts (1-2 words max per bullet)
    - **Purple/Magenta (#B87FFF)** - Technical details (rarely used)
    - **Orange/Gold (#FFB800)** - Warnings/critical alerts ONLY
  - Supporting text in white (#FFFFFF)
  - Examples: "• Viscosity & Homogeneity" (NO color), "• **Temperature** Control" (only "Temperature" colored)
- **Icon Style:** Line art, glowing cyan, simple and recognizable, 20-24px
- **Typography:** Bold key terms (1-2 words max), regular weight for all other text
- **Consistency:** Use the same panel size, glow effect, layout, and RESTRAINED color strategy for every title slide

**CRITICAL: Restrained Color-Coding Strategy**

Based on analysis of successful previous lessons, color must be used **EXTREMELY SPARINGLY**:

- **90% of text should be WHITE** - Color is the exception, not the rule
- **Only 1-2 words per bullet** get colored (maximum)
- **Many bullets have ZERO colored words** - This is intentional and correct
- **NEVER color full sentences** - Only single key terms
- **NEVER color supporting words** (and, vs, the, is, of, in, etc.)
- **If unsure, keep it white** - Less is more

**Examples from Successful Lessons:**
- "• Miniaturization (Handhelds)" - NO color, all white ✅
- "• Cloud Connectivity & IoT" - NO color, all white ✅
- "• **Viscosity** & Homogeneity" - Only "Viscosity" colored ✅
- "• **Temperature** Control" - Only "Temperature" colored ✅

**Why Restrained Color Improves Learning:**
- More professional and easier to read
- Focuses attention on what truly matters
- Doesn't overwhelm students with visual noise
- Color becomes impactful when used sparingly
- Matches industry-leading course design (Coursera, edX, Udacity)

**See COLOR_CODING_STRATEGY.md for complete guidelines.**

**Visual Style:** The 3D visual should be a metaphor for the lesson (e.g., data network for chemometrics, bridge for analyst role).

**Key Concepts Text:** Should be descriptive phrases (e.g., "The Analyst as a Bridge", "ALCOA+ Principles", "Data Integrity"), not single words.

---

### **B. Conceptual Explanation Slide**
**Purpose:** Explain a single concept using a visual metaphor.

**Layout:**
- **Top-Center:** Question or concept title (White, large)
- **Center:** Large 3D visualization (Venn diagram, molecular model, flowchart, etc.)
- **Bottom or Side:** Explanatory text (3-5 sentences or bullet points) with key terms highlighted in Cyan or Gold
- **Annotations:** Direct labels on the visual itself

**Visual Style:** The visual AND the text work together to teach the concept. Neither is sufficient alone. The visual provides the metaphor, the text provides the explanation and context.

**Text Content:** Should include:
- Definition or explanation of the concept
- Why it matters
- How it applies to NIR analysis
- Key takeaway or rule

---

### **C. Comparison Slide**
**Purpose:** Compare two approaches, methods, or concepts side-by-side.

**Layout:**
- **Top-Center:** "X VS. Y" (Cyan for X, Gold for Y)
- **Left Half:** Cyan-themed visual + heading + icon + description
- **Right Half:** Gold-themed visual + heading + icon + description
- **Bottom-Center:** Summary statement (White)

**Visual Style:** Symmetrical split-screen. Each side has its own color identity but shares the same dark navy background.

---

### **D. Process/Workflow Slide**
**Purpose:** Show a step-by-step process or workflow.

**Layout:**
- **Top-Center:** Title of the process (e.g., "The Calibration Workflow")
- **Center:** A visual flowchart with 4-6 numbered steps. Each step has a title and a brief description.
- **Arrows:** Use glowing teal arrows to connect the steps and show the flow.

**Visual Style:** The flowchart should be clean and easy to follow. Use icons to represent each step.

---

### **E. Data Visualization Slide**
**Purpose:** Present data in a visually compelling way.

**Layout:**
- **Top-Center:** Title of the chart or graph.
- **Center:** A large, clean, and easy-to-read chart (bar chart, line chart, scatter plot, etc.).
- **Annotations:** Callouts to highlight key data points or trends.
- **Bottom:** A brief summary or interpretation of the data.

**Visual Style:** Use the course color palette. The chart should be the hero of the slide. Avoid chart junk (unnecessary grid lines, labels, etc.).

---

### **F. Case Study / Example Slide**
**Purpose:** Illustrate a concept with a real-world example.

**Layout:**
- **Top-Left:** "CASE STUDY: [Application]"
- **Left Half:** A high-quality, realistic photo of the application (e.g., a pharmaceutical production line, a farmer in a field).
- **Right Half:**
  - **Problem:** (1-2 sentences)
  - **Solution:** (1-2 sentences describing the NIR method)
  - **Results:** (2-3 bullet points with quantitative outcomes, e.g., "Reduced testing time by 95%")

**Visual Style:** A clean, professional layout that tells a story.

---

## 4. Content & Structure

### 4.1. Lesson Structure

Each lesson should follow a consistent structure:

1.  **Title Slide:** Introduce the topic and key concepts.
2.  **Recap of Previous Lesson:** (Optional, for continuity).
3.  **Core Concepts:** (3-5 slides explaining the main ideas).
4.  **Examples / Case Studies:** (1-2 slides illustrating the concepts).
5.  **Lesson Recap:** Summarize the key takeaways.
6.  **Next Steps:** Preview the next lesson.

### 4.2. Narration Script

- **Tone:** Professional, engaging, and enthusiastic.
- **Pacing:** Speak clearly and at a moderate pace.
- **Content:** The script should expand on the slide content, not just read it verbatim. Provide additional context, examples, and insights.

---

## 5. Quality Control (QC) Process

Before finalizing any lesson, it must go through a rigorous QC process:

1.  **Design Review:** Does the lesson adhere to all the design principles in this DNA document?
2.  **Content Review:** Is the content accurate, clear, and concise?
3.  **Grammar & Spelling:** Is the text free of errors?
4.  **Visual Review:** Are all visuals high-quality and relevant?
5.  **Narration Review:** Is the narration clear, engaging, and in sync with the slides?

This DNA document is the single source of truth for the design and quality of the NIR course. It should be consulted for all new lesson creation and for any updates to existing lessons.
