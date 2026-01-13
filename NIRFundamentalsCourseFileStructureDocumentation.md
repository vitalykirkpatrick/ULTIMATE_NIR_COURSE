# NIR Fundamentals Course: File Structure Documentation

**Course:** NIR Fundamentals - Your Complete Guide to Near-Infrared Spectroscopy  
**Instructor:** Vitaly Kirkpatrick  
**Duration:** 8 Weeks, 32 Lessons  
**Created:** January 13, 2026

---

## Overview

This document defines the complete file structure for the NIR Fundamentals course, designed to support an AI-powered narration and video generation system. The structure accommodates video lectures, engagement materials, assessments, and supplemental resources across an 8-week curriculum.

---

## Root Structure

```
nir_fundamentals/
├── course_metadata.json           # Course-level configuration
├── README.md                       # Course overview and navigation
├── weeks/                          # Weekly content organization
├── engagement_materials/           # Cross-lesson materials
├── assessments/                    # Quizzes and exams
├── reference_guides/               # Downloadable PDFs
├── assets/                         # Shared media assets
└── exports/                        # Final deliverables
```

---

## Course Metadata Structure

**File:** `course_metadata.json`

```json
{
  "course_id": "nir_fundamentals_v1",
  "title": "NIR Fundamentals: Your Complete Guide to Near-Infrared Spectroscopy",
  "instructor": {
    "name": "Vitaly Kirkpatrick",
    "voice_profile_id": "vitaly_nir_instructor",
    "email": "vitaly@clovitek.com"
  },
  "structure": {
    "total_weeks": 8,
    "total_lessons": 32,
    "organization_type": "weekly"
  },
  "created_at": "2026-01-13T00:00:00Z",
  "version": "1.0.0",
  "platform": "Coursera",
  "target_audience": "Students, lab technicians, managers evaluating new technologies",
  "prerequisites": "None - no advanced chemistry degree required"
}
```

---

## Weekly Structure

Each week follows a consistent pattern:

```
weeks/
├── week_01_the_big_picture/
├── week_02_science_of_nir/
├── week_03_nir_vs_the_world/
├── week_04_nir_in_action/
├── week_05_how_instruments_work/
├── week_06_understanding_data/
├── week_07_practical_skills/
└── week_08_your_nir_journey/
```

### Week Folder Template

```
week_XX_topic_name/
├── week_metadata.json              # Week-level configuration
├── README.md                        # Week overview
├── lessons/                         # Individual lesson folders
├── weekly_quiz/                     # Graded assessment
└── discussion_prompts/              # Forum questions
```

**Example:** `week_metadata.json`

```json
{
  "week_number": 1,
  "title": "The Big Picture - Laying the Foundation",
  "goal": "To put NIR in context. Before we dive into the specifics of NIR, we need to understand the world it lives in.",
  "lessons": [
    {"lesson_id": "L01", "title": "Welcome & Your Learning Journey"},
    {"lesson_id": "L02", "title": "What is Analytical Chemistry? A Historical Perspective"},
    {"lesson_id": "L03", "title": "The Story of Spectroscopy: From Newton's Prism to Modern Instruments"},
    {"lesson_id": "L04", "title": "Why NIR Matters in Today's World"}
  ],
  "engagement_materials": [
    {"type": "discussion_prompt", "after_lesson": "L04"},
    {"type": "weekly_quiz", "covers_lessons": ["L01", "L02", "L03", "L04"]}
  ]
}
```

---

## Lesson Structure (Optimized)

Each lesson follows this standardized structure:

```
L##_Lesson_Name/
├── lesson_metadata.json            # Lesson configuration
├── README.md                        # Lesson overview
├── source/                          # Original content
│   ├── slides/                      # Source slides (PNG, 1920x1080)
│   │   ├── slide_001.png
│   │   ├── slide_002.png
│   │   └── ...
│   ├── narration/                   # Original narration scripts
│   │   ├── slide_001.txt
│   │   ├── slide_002.txt
│   │   └── narration_master.md     # Combined script
│   └── presentation.pptx            # Original PowerPoint (optional)
├── processed/                       # AI-generated content
│   ├── audio/                       # Generated audio files
│   │   ├── slide_001.mp3
│   │   ├── slide_002.mp3
│   │   └── metadata/                # Audio generation logs
│   │       ├── slide_001_meta.json
│   │       └── ...
│   ├── rewritten/                   # AI-enhanced scripts
│   │   ├── slide_001_rewritten.txt
│   │   ├── slide_002_rewritten.txt
│   │   └── rewrite_log.json        # Rewrite parameters & results
│   └── subtitles/                   # Generated captions
│       ├── lesson_video.srt
│       ├── lesson_video.vtt
│       └── subtitle_metadata.json
├── video/                           # Final video output
│   ├── lesson_video.mp4             # Combined video (slides + audio)
│   ├── lesson_video_720p.mp4       # Lower resolution version
│   ├── production_notes.md          # Video specs, timestamps, render log
│   └── thumbnails/                  # Video thumbnails
│       ├── thumbnail_main.jpg
│       └── thumbnail_preview.gif
├── supplemental/                    # Lesson-specific materials
│   ├── practice_quiz.json           # Optional practice quiz
│   ├── worksheet.pdf                # Optional hands-on exercise
│   └── additional_resources.md     # Links, references
└── web/                             # Web delivery assets
    ├── lesson_page.html             # Standalone lesson page
    ├── embed_code.html              # Video embed snippet
    └── assets/                      # Page-specific CSS/JS
```

### Lesson Metadata Example

**File:** `lesson_metadata.json`

```json
{
  "lesson_id": "L01",
  "lesson_number": 1,
  "title": "Welcome & Your Learning Journey",
  "week": 1,
  "duration_minutes": 8,
  "slide_count": 12,
  "keywords": ["NIR course", "spectroscopy training", "analytical chemistry basics", "learn NIR online"],
  "learning_objectives": [
    "Meet your instructor and understand their real-world experience",
    "Navigate the course platform and find all the resources",
    "Understand the goals and learning outcomes of NIR Fundamentals"
  ],
  "voice_profile": "vitaly_nir_instructor",
  "presentation_type": "education",
  "target_word_count_per_slide": "95-125",
  "created_at": "2026-01-13T00:00:00Z",
  "status": "draft",
  "video_specs": {
    "resolution": "1920x1080",
    "fps": 30,
    "codec": "H.264",
    "bitrate": "5000k"
  }
}
```

---

## Engagement Materials Structure

```
engagement_materials/
├── practice_quizzes/
│   ├── practice_quiz_01_science_of_nir.json
│   └── practice_quiz_02_sample_presentation.json
├── discussion_prompts/
│   ├── discussion_01_measurement_impact.md
│   ├── discussion_02_nir_applications.md
│   └── discussion_03_gigo_principle.md
├── hands_on_worksheets/
│   ├── worksheet_01_reading_first_spectrum/
│   │   ├── worksheet.pdf
│   │   ├── answer_key.pdf
│   │   ├── sample_spectra/
│   │   │   ├── spectrum_wheat.png
│   │   │   ├── spectrum_corn.png
│   │   │   └── spectrum_plastic.png
│   │   └── instructions.md
│   └── worksheet_02_model_validation/
│       ├── worksheet.pdf
│       ├── answer_key.pdf
│       ├── validation_plot.png
│       └── rubric.md
└── capstone_exercise/
    ├── lesson_31_capstone/
    │   ├── instructions.pdf
    │   ├── sample_spectra/
    │   │   ├── sample_01_wheat.csv
    │   │   ├── sample_02_corn.csv
    │   │   ├── sample_03_plastic.csv
    │   │   └── ...
    │   ├── assessment_rubric.md
    │   └── solution_guide.pdf
```

---

## Assessments Structure

```
assessments/
├── weekly_quizzes/
│   ├── quiz_week_01_big_picture/
│   │   ├── quiz.json                # Questions, answers, metadata
│   │   ├── quiz_config.json         # Time limit, passing score
│   │   └── README.md
│   ├── quiz_week_02_science_of_light/
│   ├── quiz_week_03_nir_vs_world/
│   ├── quiz_week_04_nir_in_action/
│   ├── quiz_week_05_instruments/
│   ├── quiz_week_06_understanding_data/
│   └── quiz_week_07_practical_considerations/
└── final_exam/
    ├── final_exam.json              # 40 questions
    ├── exam_config.json             # 90 min, 70% passing
    ├── study_guide.pdf
    └── README.md
```

### Quiz JSON Structure

**File:** `quiz.json`

```json
{
  "quiz_id": "quiz_week_01",
  "title": "Week 1: The Big Picture",
  "description": "Comprehensive quiz covering Lessons 1-4",
  "question_count": 10,
  "time_limit_minutes": 30,
  "passing_score_percent": 70,
  "attempts_allowed": 3,
  "questions": [
    {
      "question_id": "q01",
      "type": "multiple_choice",
      "question": "Which of the following best describes analytical chemistry?",
      "options": [
        "The study of chemical reactions",
        "The science of measuring chemical composition",
        "The art of synthesizing new compounds",
        "The process of purifying substances"
      ],
      "correct_answer": 1,
      "explanation": "Analytical chemistry focuses on measuring and determining the composition of substances.",
      "points": 1,
      "difficulty": "easy"
    }
  ]
}
```

---

## Reference Guides Structure

```
reference_guides/
├── guide_01_spectroscopy_family_tree/
│   ├── spectroscopy_family_tree.pdf
│   ├── spectroscopy_family_tree.png     # High-res image
│   ├── source/
│   │   └── spectroscopy_family_tree.ai  # Adobe Illustrator source
│   └── README.md
├── guide_02_nir_vs_competition/
│   ├── nir_comparison_chart.pdf
│   ├── nir_comparison_chart.png
│   └── README.md
├── guide_03_anatomy_nir_spectrometer/
│   ├── nir_spectrometer_diagram.pdf
│   ├── nir_spectrometer_diagram.png
│   └── README.md
└── guide_04_chemometrics_glossary/
    ├── chemometrics_glossary.pdf
    ├── chemometrics_glossary.md         # Markdown version
    └── README.md
```

---

## Shared Assets Structure

```
assets/
├── images/
│   ├── course_banner.jpg
│   ├── instructor_photo.jpg
│   ├── course_logo.png
│   └── week_thumbnails/
│       ├── week_01_thumbnail.jpg
│       └── ...
├── branding/
│   ├── color_palette.json
│   ├── fonts/
│   └── logo_variations/
├── templates/
│   ├── slide_template.pptx
│   ├── video_intro_template.mp4
│   └── video_outro_template.mp4
└── audio/
    ├── intro_music.mp3
    ├── outro_music.mp3
    └── transition_sounds/
```

---

## Exports Structure

```
exports/
├── full_course/
│   ├── nir_fundamentals_complete.zip
│   └── manifest.json
├── by_week/
│   ├── week_01_export.zip
│   ├── week_02_export.zip
│   └── ...
├── scorm_packages/
│   ├── nir_fundamentals_scorm_1.2.zip
│   └── nir_fundamentals_scorm_2004.zip
└── platform_specific/
    ├── coursera/
    ├── udemy/
    └── teachable/
```

---

## S3 Storage Path Convention

All files are stored in S3 with the following path structure:

```
s3://bucket-name/
└── users/
    └── {user_email}/
        └── courses/
            └── nir_fundamentals/
                ├── course_metadata.json
                ├── weeks/
                │   └── week_01_the_big_picture/
                │       └── lessons/
                │           └── L01_Welcome_Your_Learning_Journey/
                │               ├── source/slides/slide_001.png
                │               ├── processed/audio/slide_001.mp3
                │               └── video/lesson_video.mp4
                ├── engagement_materials/
                ├── assessments/
                ├── reference_guides/
                ├── assets/
                └── exports/
```

**Example S3 Path:**
```
s3://clovitek-courses/users/vitaly@clovitek.com/courses/nir_fundamentals/weeks/week_01_the_big_picture/lessons/L01_Welcome_Your_Learning_Journey/video/lesson_video.mp4
```

---

## File Naming Conventions

### Slides
- Format: `slide_{number}.png`
- Example: `slide_001.png`, `slide_012.png`
- Zero-padded to 3 digits for proper sorting

### Audio Files
- Format: `slide_{number}.mp3`
- Example: `slide_001.mp3`, `slide_012.mp3`
- Must match corresponding slide number

### Narration Scripts
- Original: `slide_{number}.txt`
- Rewritten: `slide_{number}_rewritten.txt`
- Master: `narration_master.md` (all slides combined)

### Video Files
- Main: `lesson_video.mp4`
- Alternate resolutions: `lesson_video_{resolution}.mp4`
- Example: `lesson_video_720p.mp4`, `lesson_video_1080p.mp4`

### Subtitles
- SRT format: `lesson_video.srt`
- WebVTT format: `lesson_video.vtt`

### Metadata Files
- JSON format: `{resource_name}_metadata.json`
- Example: `lesson_metadata.json`, `quiz_metadata.json`

---

## AI System Instructions

When your AI system generates narration and processes slides, it should:

1. **Read lesson metadata** from `lesson_metadata.json` to understand:
   - Voice profile to use
   - Target word count per slide
   - Presentation type (education/company)

2. **Process slides in order**:
   - Read original narration from `source/narration/slide_{number}.txt`
   - Apply AI rewriting using voice profile settings
   - Save rewritten version to `processed/rewritten/slide_{number}_rewritten.txt`
   - Log rewrite parameters to `processed/rewritten/rewrite_log.json`

3. **Generate audio**:
   - Use rewritten script as input
   - Generate audio file to `processed/audio/slide_{number}.mp3`
   - Save generation metadata to `processed/audio/metadata/slide_{number}_meta.json`

4. **Create video**:
   - Combine slides from `source/slides/` with audio from `processed/audio/`
   - Generate final video to `video/lesson_video.mp4`
   - Create production notes in `video/production_notes.md`
   - Generate subtitles to `processed/subtitles/`

5. **Update status**:
   - Update `lesson_metadata.json` with status: "processing" → "complete"
   - Log all operations with timestamps

---

## Complete NIR Fundamentals Course Structure

### Week 1: The Big Picture (4 Lessons)

```
week_01_the_big_picture/
├── lessons/
│   ├── L01_Welcome_Your_Learning_Journey/
│   ├── L02_What_Is_Analytical_Chemistry/
│   ├── L03_Story_Of_Spectroscopy/
│   └── L04_Why_NIR_Matters_Today/
├── discussion_prompts/
│   └── discussion_01_measurement_impact.md
└── weekly_quiz/
    └── quiz_week_01_big_picture/
```

### Week 2: The Science of Light & Matter (4 Lessons)

```
week_02_science_of_nir/
├── lessons/
│   ├── L05_Electromagnetic_Spectrum/
│   ├── L06_Light_And_Matter_Interaction/
│   ├── L07_Molecular_Vibrations/
│   └── L08_Why_NIR_Works_Overtones/
├── reference_guides/
│   └── spectroscopy_family_tree.pdf
├── practice_quizzes/
│   └── practice_quiz_01_science_of_nir.json
└── weekly_quiz/
    └── quiz_week_02_science_of_light/
```

### Week 3: NIR vs. The World (4 Lessons)

```
week_03_nir_vs_the_world/
├── lessons/
│   ├── L09_NIR_Vs_Wet_Chemistry/
│   ├── L10_NIR_Vs_Other_Spectroscopy/
│   ├── L11_Reading_Basic_NIR_Spectrum/
│   └── L12_Data_101_What_Is_Spectrum/
├── reference_guides/
│   └── nir_comparison_chart.pdf
├── hands_on_worksheets/
│   └── worksheet_01_reading_first_spectrum/
└── weekly_quiz/
    └── quiz_week_03_nir_vs_world/
```

### Week 4: NIR in Action (4 Lessons)

```
week_04_nir_in_action/
├── lessons/
│   ├── L13_NIR_In_Agriculture/
│   ├── L14_NIR_In_Food_Industry/
│   ├── L15_NIR_In_Pharmaceuticals/
│   └── L16_NIR_In_Other_Industries/
├── discussion_prompts/
│   └── discussion_02_nir_applications.md
└── weekly_quiz/
    └── quiz_week_04_nir_in_action/
```

### Week 5: How NIR Instruments Work (4 Lessons)

```
week_05_how_instruments_work/
├── lessons/
│   ├── L17_Inside_NIR_Instrument/
│   ├── L18_Different_Types_NIR_Instruments/
│   ├── L19_Choosing_Right_Instrument/
│   └── L20_Sample_Presentation/
├── reference_guides/
│   └── nir_spectrometer_diagram.pdf
├── practice_quizzes/
│   └── practice_quiz_02_sample_presentation.json
└── weekly_quiz/
    └── quiz_week_05_instruments/
```

### Week 6: Understanding NIR Data (4 Lessons)

```
week_06_understanding_data/
├── lessons/
│   ├── L21_What_Is_Chemometrics/
│   ├── L22_Calibration_Teaching_Machine/
│   ├── L23_Validation_How_Know_Working/
│   └── L24_Common_Mistakes_How_Avoid/
├── reference_guides/
│   └── chemometrics_glossary.pdf
├── hands_on_worksheets/
│   └── worksheet_02_model_validation/
└── weekly_quiz/
    └── quiz_week_06_understanding_data/
```

### Week 7: Practical Considerations (4 Lessons)

```
week_07_practical_skills/
├── lessons/
│   ├── L25_Sample_Preparation/
│   ├── L26_Building_Good_Calibration/
│   ├── L27_GIGO_Principle/
│   └── L28_Troubleshooting_Common_Issues/
├── discussion_prompts/
│   └── discussion_03_gigo_principle.md
└── weekly_quiz/
    └── quiz_week_07_practical_considerations/
```

### Week 8: Your NIR Journey (4 Lessons)

```
week_08_your_nir_journey/
├── lessons/
│   ├── L29_Method_Development_Workflow/
│   ├── L30_Working_With_Vendors/
│   ├── L31_Capstone_Exercise/
│   └── L32_Your_Next_Steps/
├── capstone_exercise/
│   └── lesson_31_capstone/
└── final_exam/
    └── final_exam.json
```

---

## Summary Statistics

| Metric | Count |
|--------|-------|
| Total Weeks | 8 |
| Total Lessons | 32 |
| Practice Quizzes | 2 |
| Weekly Graded Quizzes | 7 |
| Discussion Prompts | 3 |
| Hands-On Worksheets | 2 |
| Reference Guides | 4 |
| Capstone Exercise | 1 |
| Final Exam | 1 |
| **Total Engagement Materials** | **20** |

---

## Implementation Checklist

- [ ] Create root course directory structure
- [ ] Generate all 8 week folders with metadata
- [ ] Create all 32 lesson folders with template structure
- [ ] Upload source slides to `source/slides/` for each lesson
- [ ] Upload original narration scripts to `source/narration/`
- [ ] Configure lesson metadata JSON files
- [ ] Create all engagement materials folders
- [ ] Prepare quiz JSON files for all 7 weekly quizzes
- [ ] Prepare final exam JSON file
- [ ] Design and upload 4 reference guide PDFs
- [ ] Create 2 hands-on worksheet packages
- [ ] Set up S3 bucket with proper path structure
- [ ] Configure AI system to read/write to correct paths
- [ ] Test end-to-end workflow: slides → narration → audio → video
- [ ] Validate all file naming conventions
- [ ] Create course export packages

---

**Document Version:** 1.0  
**Last Updated:** January 13, 2026  
**Maintained By:** Vitaly Kirkpatrick / Clovitek
