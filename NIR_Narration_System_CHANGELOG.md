# Changelog

All notable changes to the NIR Narration System will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.0] - 2026-01-08

### 🎉 Major Release - Complete System Overhaul

### Added
- **Story Database** - Comprehensive database of approved stories organized by topic
- **Opening Patterns Database** - 15 pattern types with examples and usage guidelines
- **Pattern Variety Tracking** - SQLite database tracking to ensure 90%+ uniqueness
- **Background Verification System** - Ensures all stories match Vitaly's real professional background
- **Simple Language Enforcement** - 10-15 word sentence limit, forbidden words list
- **Complete Documentation** - Setup guides, API docs, story guidelines, troubleshooting

### Changed
- **Professional Background** - Corrected from "lab employee" to "consultant/expert"
- **Story Framing** - Changed from false claims to accurate consultant perspective
- **Language Style** - Simplified from flowery/complex to direct/conversational
- **Narration Length** - Optimized to 95-120 words per slide
- **AI Prompt** - Complete rewrite with accurate background and style guidelines

### Fixed
- ❌ **False Work History** - Removed claims of lab audits, QC employment, plant management
- ❌ **Flowery Language** - Eliminated complex vocabulary (buzzing, myriad, plethora, etc.)
- ❌ **Pattern Repetition** - Implemented tracking to prevent repetitive openings
- ❌ **Long Sentences** - Enforced 10-15 word maximum per sentence
- ❌ **Dramatic Storytelling** - Replaced with simple, direct explanations

### Removed
- Forbidden words list (buzzing, myriad, plethora, delve, embark, journey, unlock, etc.)
- False background claims
- Overly dramatic narrative style
- Repetitive opening patterns

---

## [1.0.0] - 2025-12-24

### Initial Release

### Added
- Basic AI narration rewriting using OpenAI GPT-4
- ElevenLabs voice synthesis integration
- Pattern tracking database (10 patterns)
- Voice profile management
- Flask API for narration generation
- SSML support for pauses and emphasis

### Features
- Converts technical narration to engaging style
- Adds personal stories and analogies
- Generates audio with Vitaly's voice
- Tracks opening patterns to reduce repetition

### Known Issues
- Background accuracy problems (false work history claims)
- Language too flowery and complex
- Pattern variety only ~60-70%
- Long, complex sentences

---

## Version Comparison

### v1.0 vs v2.0

| Feature | v1.0 | v2.0 |
|---------|------|------|
| **Background Accuracy** | ❌ False claims | ✅ 100% accurate |
| **Language Style** | ❌ Flowery, complex | ✅ Simple, direct |
| **Sentence Length** | ❌ 20-30 words | ✅ 10-15 words |
| **Pattern Variety** | ❌ 60-70% | ✅ 90%+ |
| **Story Database** | ❌ None | ✅ Comprehensive |
| **Documentation** | ❌ Minimal | ✅ Complete |
| **Testing** | ❌ None | ✅ Unit tests |

---

## Migration Guide (v1.0 → v2.0)

### Breaking Changes
1. **AI Prompt Format** - Completely rewritten, not backward compatible
2. **Database Schema** - Added `pattern_type` tracking
3. **API Endpoints** - Added `opening_pattern` parameter

### Migration Steps

#### 1. Backup Existing Data
```bash
cp /var/www/app.clovitek.com/server/voice_profiles.db voice_profiles_v1_backup.db
```

#### 2. Update Code
```bash
cd /var/www/app.clovitek.com/server
git pull origin main
pip install -r requirements.txt
```

#### 3. Run Database Migration
```bash
python migrations/migrate_v1_to_v2.py
```

#### 4. Regenerate All Narrations
```bash
python code/regenerate_all_lessons.py --version 2.0
```

#### 5. Verify Results
```bash
python tests/test_pattern_variety.py
python tests/test_story_accuracy.py
```

---

## Upcoming Features (v2.1)

### Planned
- [ ] Multi-language support (Spanish, Portuguese)
- [ ] A/B testing framework for narration styles
- [ ] Advanced NIR course story database
- [ ] Real-time pattern variety monitoring dashboard
- [ ] Automated quality checks before audio generation
- [ ] Integration with video generation pipeline

### Under Consideration
- [ ] Voice cloning for multiple instructors
- [ ] Student feedback integration
- [ ] Adaptive narration based on student performance
- [ ] Interactive narration with branching scenarios

---

## Bug Fixes by Version

### v2.0.0 (2026-01-08)
- Fixed false work history claims in ALCOA lessons
- Fixed flowery language in technical explanations
- Fixed pattern repetition (scenario used 5x in one lesson)
- Fixed long sentences (30+ words)
- Fixed incorrect consultant framing

### v1.0.0 (2025-12-24)
- Initial release, no bug fixes

---

## Performance Improvements

### v2.0.0
- AI rewrite time: 3-5 seconds (unchanged)
- Audio generation: 5-10 seconds (unchanged)
- Pattern selection: <0.1 seconds (new feature)
- Database queries: Optimized with indexes
- Total generation time: ~8-15 seconds per slide

---

## Security Updates

### v2.0.0
- Added `.env` file for API keys (not committed to git)
- Implemented environment variable validation
- Added API key rotation documentation
- Secured database with proper permissions

---

## Documentation Updates

### v2.0.0
- Added comprehensive README
- Created API documentation
- Wrote story guidelines
- Added pattern selection guide
- Created troubleshooting guide
- Added deployment instructions

---

## Contributors

- **Vitaly Kirkpatrick** - Project Lead, Content Creator
- **AI Development Team** - System Architecture, Implementation

---

## License

MIT License - See LICENSE.md for details

---

## Support

For issues, questions, or feature requests:
- GitHub Issues: https://github.com/vitalykirkpatrick/clovitek/issues
- Email: vitaly@vitalykirkpatrick.com
- Documentation: `/docs/`
