# Default User File Structure Documentation

**Platform:** Clovitek Voice & Video Platform  
**Version:** 2.0  
**Created:** January 13, 2026

---

## Overview

This document defines the **default file structure** that is automatically created when a new user signs up. The structure supports multiple use cases including course creation, audiobook production, voice profile management, and general content storage. Users can customize this structure later through the File Manager, but this provides a sensible starting point.

---

## Design Principles

The default structure follows these core principles:

1. **Use Case Separation** - Clear boundaries between courses, audiobooks, and other content types
2. **Consistent Patterns** - Similar folder hierarchies across different content types
3. **Source/Processed Separation** - Original files always preserved separately from AI-generated content
4. **Scalability** - Structure works for 1 project or 1,000 projects
5. **Cloud-First** - Designed for S3 storage with efficient path structures
6. **AI-Friendly** - Clear conventions that AI systems can follow automatically

---

## Root User Structure

```
s3://bucket-name/users/{user_email}/
├── profile/                        # User account & voice profiles
├── courses/                        # Educational content (NIR, etc.)
├── audiobooks/                     # Book-to-audio projects
├── presentations/                  # Standalone presentations
├── voice_profiles/                 # Voice cloning & customization
├── uploads/                        # Temporary upload staging
├── exports/                        # Final deliverables
├── templates/                      # User-created templates
└── trash/                          # Soft-deleted items (30-day retention)
```

---

## 1. Profile Structure

User account information and system preferences.

```
profile/
├── user_metadata.json              # Account info, preferences
├── subscription.json               # Plan, billing, usage limits
├── api_keys/                       # Generated API keys
│   ├── key_001.json
│   └── key_002.json
├── activity_logs/                  # User action history
│   ├── 2026-01/
│   │   ├── activity_2026-01-13.json
│   │   └── ...
│   └── ...
└── preferences/
    ├── ui_settings.json            # Theme, layout preferences
    ├── default_voice_profile.json  # Default voice selection
    └── notification_settings.json
```

### User Metadata Example

**File:** `user_metadata.json`

```json
{
  "user_id": "usr_abc123",
  "email": "vitaly@clovitek.com",
  "name": "Vitaly Kirkpatrick",
  "created_at": "2026-01-13T00:00:00Z",
  "timezone": "America/Los_Angeles",
  "default_voice_profile": "vitaly_nir_instructor",
  "storage_used_gb": 12.5,
  "storage_limit_gb": 100.0,
  "projects": {
    "courses": 1,
    "audiobooks": 0,
    "presentations": 5
  }
}
```

---

## 2. Courses Structure

Educational content with lessons, quizzes, and engagement materials.

```
courses/
├── course_001_nir_fundamentals/
├── course_002_python_basics/
└── course_003_data_science/
```

### Course Folder Template

```
course_{id}_{name}/
├── course_metadata.json            # Course configuration
├── README.md                        # Course overview
├── structure/                       # Organizational units
│   ├── weeks/                       # OR modules/ OR sections/
│   │   ├── week_01/
│   │   ├── week_02/
│   │   └── ...
│   └── lessons/                     # All lessons (flat or nested)
│       ├── L01_lesson_name/
│       ├── L02_lesson_name/
│       └── ...
├── engagement_materials/
│   ├── quizzes/
│   ├── worksheets/
│   ├── discussion_prompts/
│   └── reference_guides/
├── assessments/
│   ├── weekly_quizzes/
│   └── final_exam/
├── assets/                          # Course-wide media
│   ├── images/
│   ├── branding/
│   └── templates/
└── exports/
    ├── full_course/
    ├── by_week/
    └── platform_specific/
```

### Lesson Folder Template (Detailed)

```
L##_lesson_name/
├── lesson_metadata.json
├── README.md
├── source/                          # Original content
│   ├── slides/                      # PNG slides (1920x1080)
│   │   ├── slide_001.png
│   │   └── ...
│   ├── narration/                   # Original scripts
│   │   ├── slide_001.txt
│   │   └── narration_master.md
│   └── presentation.pptx            # Original PowerPoint
├── processed/                       # AI-generated content
│   ├── audio/                       # Generated audio
│   │   ├── slide_001.mp3
│   │   └── metadata/
│   ├── rewritten/                   # AI-enhanced scripts
│   │   ├── slide_001_rewritten.txt
│   │   └── rewrite_log.json
│   └── subtitles/
│       ├── lesson_video.srt
│       └── lesson_video.vtt
├── video/                           # Final video output
│   ├── lesson_video.mp4
│   ├── lesson_video_720p.mp4
│   ├── production_notes.md
│   └── thumbnails/
├── supplemental/                    # Lesson-specific materials
│   ├── practice_quiz.json
│   ├── worksheet.pdf
│   └── additional_resources.md
└── web/                             # Web delivery
    ├── lesson_page.html
    └── embed_code.html
```

---

## 3. Audiobooks Structure

Book-to-audio conversion projects with chapter-based organization.

```
audiobooks/
├── book_001_awakening_memories/
├── book_002_nir_handbook/
└── book_003_data_analysis_guide/
```

### Audiobook Folder Template

```
book_{id}_{title}/
├── book_metadata.json              # Book configuration
├── README.md                        # Book overview
├── source/                          # Original content
│   ├── manuscript/                  # Source text files
│   │   ├── full_manuscript.docx
│   │   ├── full_manuscript.txt
│   │   └── full_manuscript.pdf
│   ├── chapters/                    # Split by chapter
│   │   ├── chapter_01.txt
│   │   ├── chapter_02.txt
│   │   └── ...
│   └── metadata/
│       ├── table_of_contents.json
│       └── chapter_metadata.json
├── narrator_manifests/              # AudiobookSmith context
│   ├── cultural_context.json       # Cultural references
│   ├── idioms_expressions.json     # Idiomatic phrases
│   ├── names_pronunciation.json    # Character names
│   ├── poems_poetry.json           # Embedded poetry
│   ├── proverbs_sayings.json       # Proverbs & sayings
│   ├── songs_lyrics.json           # Song lyrics
│   ├── religious_texts.json        # Religious references
│   ├── kinship_terms.json          # Family relationships
│   └── cultural_terms.json         # Specialized terminology
├── processed/                       # AI processing
│   ├── analysis/                    # Content analysis
│   │   ├── sentiment_analysis.json
│   │   ├── character_analysis.json
│   │   └── pacing_analysis.json
│   ├── rewritten/                   # Enhanced for narration
│   │   ├── chapter_01_narration.txt
│   │   ├── chapter_02_narration.txt
│   │   └── rewrite_log.json
│   └── audio/                       # Generated audio files
│       ├── chapter_01.mp3
│       ├── chapter_02.mp3
│       └── metadata/
│           ├── chapter_01_meta.json
│           └── ...
├── final/                           # Final audiobook output
│   ├── full_audiobook.mp3          # Single file version
│   ├── chapters/                    # Chapter-by-chapter
│   │   ├── chapter_01.mp3
│   │   ├── chapter_02.mp3
│   │   └── ...
│   ├── metadata/
│   │   ├── audiobook_metadata.json
│   │   ├── chapter_timestamps.json
│   │   └── production_notes.md
│   └── cover_art/
│       ├── cover_3000x3000.jpg     # Audible spec
│       └── cover_1400x1400.jpg     # iTunes spec
├── supplemental/
│   ├── author_bio.md
│   ├── book_description.md
│   └── marketing_copy.md
└── exports/
    ├── audible/                     # Audible ACX format
    ├── itunes/                      # Apple Books format
    └── google_play/                 # Google Play format
```

### Book Metadata Example

**File:** `book_metadata.json`

```json
{
  "book_id": "book_001",
  "title": "Awakening Memories: A Ukrainian-American Journey",
  "author": "Vitaly Kirkpatrick",
  "narrator": "Vitaly Kirkpatrick",
  "voice_profile_id": "vitaly_memoir_narrator",
  "genre": "Memoir",
  "language": "en-US",
  "isbn": "978-1234567890",
  "publication_date": "2021-02-07",
  "total_chapters": 24,
  "estimated_duration_hours": 8.5,
  "narrator_context": {
    "cultural_background": "Ukrainian-American",
    "time_period": "1980s-2020s",
    "special_considerations": [
      "Ukrainian names and places",
      "LDS Church terminology",
      "Immigrant experience themes"
    ]
  },
  "processing_settings": {
    "narration_style": "personal_memoir",
    "pacing": "moderate",
    "emotional_tone": "reflective",
    "pronunciation_guides_enabled": true
  },
  "created_at": "2026-01-13T00:00:00Z",
  "status": "in_progress"
}
```

### Narrator Manifest Example

**File:** `narrator_manifests/names_pronunciation.json`

```json
{
  "manifest_type": "names_pronunciation",
  "book_id": "book_001",
  "entries": [
    {
      "name": "Chernivtsi",
      "pronunciation": "chair-NEET-see",
      "phonetic": "tʃɛrˈnivt͡si",
      "context": "City in Ukraine where author was born",
      "first_appearance_chapter": 1
    },
    {
      "name": "Krapiva",
      "pronunciation": "krah-PEE-vah",
      "phonetic": "kraˈpʲivə",
      "context": "Author's childhood village",
      "first_appearance_chapter": 2
    }
  ]
}
```

---

## 4. Presentations Structure

Standalone presentations not part of a course.

```
presentations/
├── presentation_001_quarterly_review/
├── presentation_002_product_launch/
└── presentation_003_conference_talk/
```

### Presentation Folder Template

```
presentation_{id}_{name}/
├── presentation_metadata.json
├── README.md
├── source/
│   ├── slides/
│   │   ├── slide_001.png
│   │   └── ...
│   ├── narration/
│   │   ├── slide_001.txt
│   │   └── narration_master.md
│   └── presentation.pptx
├── processed/
│   ├── audio/
│   ├── rewritten/
│   └── subtitles/
├── video/
│   ├── presentation_video.mp4
│   └── production_notes.md
└── exports/
    ├── video_files/
    └── web_embed/
```

---

## 5. Voice Profiles Structure

Voice cloning, customization, and profile management.

```
voice_profiles/
├── profile_001_vitaly_nir_instructor/
├── profile_002_vitaly_memoir_narrator/
└── profile_003_custom_voice/
```

### Voice Profile Folder Template

```
profile_{id}_{name}/
├── profile_metadata.json           # Voice configuration
├── README.md                        # Profile description
├── wizard_data/                     # Voice Profile Wizard output
│   ├── wizard_responses.json       # User answers from wizard
│   ├── analysis_results.json       # AI analysis of sources
│   └── profile_generation_log.json
├── analysis_data/                   # Source material analysis
│   ├── sources/                     # Original source files
│   │   ├── book/                    # Books, manuscripts
│   │   │   ├── vitaly_book.pdf
│   │   │   └── vitaly_book.txt
│   │   ├── resumes/                 # Professional documents
│   │   │   ├── resume_2024.pdf
│   │   │   └── cover_letters/
│   │   ├── articles/                # Published articles
│   │   ├── transcripts/             # Speech transcripts
│   │   └── social_media/            # Social media posts
│   ├── scraped_content/             # Web-scraped content
│   │   ├── linkedin_profile.json
│   │   ├── blog_posts/
│   │   └── interviews/
│   └── analysis_results/            # AI analysis output
│       ├── vocabulary_analysis.json
│       ├── sentence_structure.json
│       ├── tone_analysis.json
│       └── personality_traits.json
├── voice_samples/                   # Audio samples for cloning
│   ├── sample_001.mp3
│   ├── sample_002.mp3
│   ├── sample_003.mp3
│   └── metadata/
│       ├── sample_001_meta.json
│       └── ...
├── cloned_voices/                   # Cloned voice IDs
│   ├── elevenlabs/
│   │   ├── voice_id.txt
│   │   └── clone_metadata.json
│   └── unmixr/
│       ├── voice_id.txt
│       └── clone_metadata.json
├── rewriter_config/                 # AI rewriter settings
│   ├── rewriter_system_prompt.txt
│   ├── opening_patterns.json
│   ├── style_guidelines.json
│   └── forbidden_phrases.json
└── test_outputs/                    # Test narrations
    ├── test_001_output.txt
    ├── test_001_audio.mp3
    └── test_results.json
```

### Voice Profile Metadata Example

**File:** `profile_metadata.json`

```json
{
  "profile_id": "profile_001",
  "profile_name": "vitaly_nir_instructor",
  "display_name": "Vitaly - NIR Instructor",
  "created_at": "2026-01-13T00:00:00Z",
  "voice_type": "cloned",
  "vendor": "ElevenLabs",
  "cloned_voice_id": "21m00Tcm4TlvDq8ikWAM",
  "personality": {
    "role": "consultant",
    "tone": "friendly_professional",
    "expertise_level": "expert",
    "teaching_style": "practical_storyteller"
  },
  "language_style": {
    "sentence_length": "10-15 words",
    "vocabulary_level": "accessible",
    "technical_depth": "moderate",
    "use_analogies": true,
    "use_personal_anecdotes": true
  },
  "narration_settings": {
    "presentation_type": "education",
    "target_word_count": "95-125",
    "opening_pattern_variety": 15,
    "avoid_phrases": ["Let's talk about", "Today we're going to", "In this slide"]
  },
  "source_materials": {
    "books": 1,
    "articles": 5,
    "resumes": 3,
    "transcripts": 2,
    "total_words_analyzed": 125000
  }
}
```

---

## 6. Uploads Structure

Temporary staging area for file uploads before processing.

```
uploads/
├── 2026-01/                         # Organized by month
│   ├── upload_20260113_143022/      # Timestamp-based folders
│   │   ├── upload_metadata.json
│   │   ├── files/
│   │   │   ├── presentation.pptx
│   │   │   └── narration_scripts.zip
│   │   └── processing_status.json
│   └── upload_20260113_150334/
│       ├── upload_metadata.json
│       ├── files/
│       │   └── book_manuscript.docx
│       └── processing_status.json
└── 2026-02/
```

### Upload Metadata Example

**File:** `upload_metadata.json`

```json
{
  "upload_id": "upload_20260113_143022",
  "user_id": "usr_abc123",
  "upload_type": "presentation",
  "source": "local_file",
  "uploaded_at": "2026-01-13T14:30:22Z",
  "files": [
    {
      "filename": "presentation.pptx",
      "size_bytes": 5242880,
      "mime_type": "application/vnd.openxmlformats-officedocument.presentationml.presentation"
    }
  ],
  "processing_status": "completed",
  "destination": "courses/course_001_nir_fundamentals/weeks/week_01/lessons/L01_Welcome/",
  "completed_at": "2026-01-13T14:35:10Z"
}
```

---

## 7. Exports Structure

Final deliverables ready for download or distribution.

```
exports/
├── courses/
│   ├── nir_fundamentals_complete_20260113.zip
│   └── python_basics_week_01_20260110.zip
├── audiobooks/
│   ├── awakening_memories_audible_20260112.zip
│   └── nir_handbook_itunes_20260108.zip
├── presentations/
│   ├── quarterly_review_video_20260105.mp4
│   └── product_launch_slides_20260107.zip
└── voice_profiles/
    ├── vitaly_nir_instructor_export_20260113.json
    └── custom_voice_export_20260110.json
```

---

## 8. Templates Structure

User-created templates for reuse across projects.

```
templates/
├── course_templates/
│   ├── template_001_weekly_course/
│   │   ├── template_metadata.json
│   │   └── structure/
│   └── template_002_modular_course/
├── presentation_templates/
│   ├── template_001_corporate/
│   └── template_002_educational/
├── slide_templates/
│   ├── title_slide.pptx
│   ├── content_slide.pptx
│   └── conclusion_slide.pptx
└── document_templates/
    ├── worksheet_template.pdf
    └── quiz_template.json
```

---

## 9. Trash Structure

Soft-deleted items with 30-day retention before permanent deletion.

```
trash/
├── deleted_2026-01-13/
│   ├── course_002_python_basics/
│   │   ├── deletion_metadata.json
│   │   └── [original folder structure]
│   └── presentation_005_old_version/
│       ├── deletion_metadata.json
│       └── [original folder structure]
└── deleted_2026-01-12/
```

### Deletion Metadata Example

**File:** `deletion_metadata.json`

```json
{
  "deleted_at": "2026-01-13T10:30:00Z",
  "original_path": "courses/course_002_python_basics/",
  "deleted_by": "usr_abc123",
  "reason": "user_requested",
  "permanent_deletion_date": "2026-02-12T10:30:00Z",
  "can_restore": true,
  "size_bytes": 52428800
}
```

---

## File Naming Conventions

### General Rules

1. **Use snake_case** for all folder and file names
2. **No spaces** - use underscores instead
3. **Lowercase** - except for lesson IDs (L01, L02)
4. **Descriptive names** - avoid generic names like "file1.txt"
5. **Include version numbers** when applicable (v1, v2)
6. **Timestamps** for uploads/exports: YYYYMMDD_HHMMSS

### Specific Patterns

| Type | Pattern | Example |
|------|---------|---------|
| Course | `course_{id}_{name}` | `course_001_nir_fundamentals` |
| Audiobook | `book_{id}_{title}` | `book_001_awakening_memories` |
| Presentation | `presentation_{id}_{name}` | `presentation_001_quarterly_review` |
| Lesson | `L##_{name}` | `L01_Welcome_Your_Learning_Journey` |
| Chapter | `chapter_{number}` | `chapter_01`, `chapter_02` |
| Slide | `slide_{number}` | `slide_001.png`, `slide_012.png` |
| Audio | `slide_{number}.mp3` or `chapter_{number}.mp3` | `slide_001.mp3`, `chapter_01.mp3` |
| Video | `{content}_video.mp4` | `lesson_video.mp4`, `presentation_video.mp4` |
| Metadata | `{resource}_metadata.json` | `lesson_metadata.json`, `book_metadata.json` |
| Upload | `upload_{timestamp}` | `upload_20260113_143022` |
| Export | `{content}_{format}_{date}` | `nir_fundamentals_complete_20260113.zip` |

---

## S3 Path Examples

### Course Lesson Video
```
s3://clovitek-platform/users/vitaly@clovitek.com/courses/course_001_nir_fundamentals/structure/weeks/week_01/lessons/L01_Welcome_Your_Learning_Journey/video/lesson_video.mp4
```

### Audiobook Chapter Audio
```
s3://clovitek-platform/users/vitaly@clovitek.com/audiobooks/book_001_awakening_memories/processed/audio/chapter_01.mp3
```

### Voice Profile Source Material
```
s3://clovitek-platform/users/vitaly@clovitek.com/voice_profiles/profile_001_vitaly_nir_instructor/analysis_data/sources/book/vitaly_book.pdf
```

### Presentation Video
```
s3://clovitek-platform/users/vitaly@clovitek.com/presentations/presentation_001_quarterly_review/video/presentation_video.mp4
```

---

## Auto-Creation on User Signup

When a new user signs up, the system automatically creates:

```bash
# Root structure
users/{user_email}/profile/
users/{user_email}/courses/
users/{user_email}/audiobooks/
users/{user_email}/presentations/
users/{user_email}/voice_profiles/
users/{user_email}/uploads/
users/{user_email}/exports/
users/{user_email}/templates/
users/{user_email}/trash/

# Profile files
users/{user_email}/profile/user_metadata.json
users/{user_email}/profile/subscription.json
users/{user_email}/profile/preferences/ui_settings.json
users/{user_email}/profile/preferences/default_voice_profile.json
users/{user_email}/profile/preferences/notification_settings.json

# Placeholder README files
users/{user_email}/courses/README.md
users/{user_email}/audiobooks/README.md
users/{user_email}/presentations/README.md
users/{user_email}/voice_profiles/README.md
```

---

## AI System Instructions

### For Course Processing

1. **Detect upload type**: presentation, zip file, or cloud link
2. **Create course folder**: `courses/course_{id}_{name}/`
3. **Extract slides**: Save to `source/slides/`
4. **Extract narration**: Save to `source/narration/`
5. **Read lesson metadata**: Understand voice profile, word count targets
6. **Process with AI**: Rewrite scripts, generate audio
7. **Save processed files**: To `processed/audio/`, `processed/rewritten/`
8. **Generate video**: Combine slides + audio → `video/lesson_video.mp4`
9. **Update status**: Mark lesson as "complete" in metadata

### For Audiobook Processing

1. **Detect book upload**: DOCX, PDF, TXT, or EPUB
2. **Create audiobook folder**: `audiobooks/book_{id}_{title}/`
3. **Split into chapters**: Save to `source/chapters/`
4. **Read narrator manifests**: Load pronunciation guides, cultural context
5. **Analyze content**: Character analysis, pacing, sentiment
6. **Process with AI**: Rewrite for narration with context awareness
7. **Generate audio**: Chapter-by-chapter with proper pronunciation
8. **Save final audiobook**: To `final/chapters/` and `final/full_audiobook.mp3`
9. **Generate metadata**: Chapter timestamps, production notes

### For Voice Profile Creation

1. **User completes wizard**: Collect source materials, preferences
2. **Create profile folder**: `voice_profiles/profile_{id}_{name}/`
3. **Store wizard data**: Save responses to `wizard_data/`
4. **Analyze sources**: Extract writing style, vocabulary, tone
5. **Generate rewriter config**: Create custom system prompts
6. **Clone voice** (if audio provided): Save voice IDs to `cloned_voices/`
7. **Test profile**: Generate sample narrations to `test_outputs/`
8. **Save profile metadata**: Complete configuration in `profile_metadata.json`

---

## Storage Quotas & Limits

| Plan Tier | Storage Limit | Courses | Audiobooks | Voice Profiles |
|-----------|---------------|---------|------------|----------------|
| Free | 5 GB | 1 | 0 | 1 |
| Starter | 50 GB | 5 | 2 | 3 |
| Professional | 200 GB | 20 | 10 | 10 |
| Enterprise | Unlimited | Unlimited | Unlimited | Unlimited |

---

## File Manager Features (Future Implementation)

Users will be able to:

- **Rename folders** and files
- **Move content** between folders
- **Create custom folders** outside default structure
- **Tag content** for organization
- **Search across** all files
- **Bulk operations** (move, delete, export)
- **Share folders** with collaborators
- **Set permissions** on folders
- **Create shortcuts** to frequently accessed content
- **Archive old projects** to cold storage

---

## Migration Path

For existing users with content in old structure:

1. **Backup existing data** to `exports/migration_backup_{date}/`
2. **Create new structure** with auto-creation script
3. **Map old paths to new paths** using migration mapping file
4. **Copy files** to new locations
5. **Update database references** to new paths
6. **Validate migration** - check all files accessible
7. **Mark old structure** for deletion after 30 days
8. **Notify user** of successful migration

---

## Summary Comparison

| Use Case | Root Folder | Key Subfolders | Primary Output |
|----------|-------------|----------------|----------------|
| **Course** | `courses/` | `weeks/`, `lessons/`, `assessments/` | `video/lesson_video.mp4` |
| **Audiobook** | `audiobooks/` | `chapters/`, `narrator_manifests/` | `final/full_audiobook.mp3` |
| **Presentation** | `presentations/` | `slides/`, `narration/` | `video/presentation_video.mp4` |
| **Voice Profile** | `voice_profiles/` | `analysis_data/`, `cloned_voices/` | `profile_metadata.json` |

---

## Implementation Checklist

### Phase 1: Core Structure
- [ ] Implement auto-creation script for new user signup
- [ ] Create S3 bucket structure with proper IAM policies
- [ ] Build folder creation API endpoints
- [ ] Test with sample user accounts

### Phase 2: Upload Processing
- [ ] Implement file upload handler (local files)
- [ ] Implement URL download handler (cloud links)
- [ ] Implement ZIP extraction handler
- [ ] Route uploads to correct destination folders

### Phase 3: AI Integration
- [ ] Connect AI rewriter to read from `source/narration/`
- [ ] Configure AI to save to `processed/rewritten/`
- [ ] Connect audio generator to read rewritten scripts
- [ ] Configure audio generator to save to `processed/audio/`

### Phase 4: Video Generation
- [ ] Implement video combiner (slides + audio)
- [ ] Generate subtitles and save to `processed/subtitles/`
- [ ] Create production notes and save to `video/`
- [ ] Generate multiple resolutions (720p, 1080p)

### Phase 5: File Manager UI
- [ ] Build file browser interface
- [ ] Implement rename, move, delete operations
- [ ] Add search and filter functionality
- [ ] Create bulk operations interface

### Phase 6: Migration
- [ ] Build migration script for existing users
- [ ] Test migration with sample data
- [ ] Deploy migration in batches
- [ ] Validate all migrated content

---

**Document Version:** 2.0  
**Last Updated:** January 13, 2026  
**Maintained By:** Clovitek Engineering Team
