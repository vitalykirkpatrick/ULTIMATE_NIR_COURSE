# NIR Narration System v2.0
**Complete Voice Generation System for NIR Essentials Course**

**Version:** 2.0  
**Date:** January 8, 2026  
**Author:** Vitaly Kirkpatrick  
**Purpose:** Production-ready narration system with accurate background, simple language, and pattern variety

---

## 🎯 What's New in v2.0

### ✅ Fixed Issues:
1. **Accurate Background** - Vitaly framed as consultant/expert, not lab employee
2. **Simple Language** - Short sentences (10-15 words), conversational tone
3. **Pattern Variety** - 15 opening patterns, 90%+ uniqueness
4. **No False Claims** - All stories verified against real professional background

### ❌ Removed:
1. Flowery, complex language
2. False work history (lab audits, QC employment)
3. Dramatic storytelling
4. Repetitive opening patterns

---

## 📦 Package Contents

```
nir-narration-system-v2/
├── code/
│   ├── ai_narration_rewriter_v2.py       # Core AI rewriter with pattern variety
│   ├── narration_generator_api.py         # Flask API for narration generation
│   ├── generate_lesson_complete.py        # Complete lesson workflow
│   └── elevenlabs_audio_generator.py      # Audio generation service
│
├── databases/
│   ├── NIR_ESSENTIALS_STORY_DATABASE.md   # Approved stories by topic
│   ├── OPENING_PATTERNS_DATABASE.md       # 15 pattern types with examples
│   ├── VITALY_REAL_BACKGROUND.md          # Professional background reference
│   └── voice_profiles.db                  # SQLite database schema
│
├── docs/
│   ├── SETUP_GUIDE.md                     # Installation instructions
│   ├── API_DOCUMENTATION.md               # API endpoints and usage
│   ├── STORY_GUIDELINES.md                # How to write accurate stories
│   ├── PATTERN_SELECTION_GUIDE.md         # Choosing opening patterns
│   └── TROUBLESHOOTING.md                 # Common issues and fixes
│
├── examples/
│   ├── lesson_001_corrected/              # Complete Lesson 001 (11 slides)
│   │   ├── *.txt                          # Narration text files
│   │   ├── *.mp3                          # Generated audio files
│   │   └── results.json                   # Generation metadata
│   ├── before_after_comparison.md         # Show improvements
│   └── pattern_variety_examples.md        # Pattern usage examples
│
├── tests/
│   ├── test_ai_rewriter.py                # Unit tests for rewriter
│   ├── test_pattern_variety.py            # Pattern tracking tests
│   └── test_story_accuracy.py             # Background accuracy tests
│
├── README.md                              # This file
├── CHANGELOG.md                           # Version history
├── LICENSE.md                             # MIT License
└── requirements.txt                       # Python dependencies
```

---

## 🚀 Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Configure Environment
```bash
cp .env.example .env
# Edit .env with your API keys:
# - OPENAI_API_KEY
# - ELEVENLABS_API_KEY
```

### 3. Initialize Database
```bash
python code/init_database.py
```

### 4. Generate Narrations
```bash
python code/generate_lesson_complete.py --lesson 001
```

### 5. Start API Server
```bash
python code/narration_generator_api.py
```

---

## 📚 Key Features

### 1. Accurate Professional Background
✅ Vitaly as NIR Technology Expert & Consultant  
✅ Works WITH companies (not employed BY them)  
✅ Correct framing: "During plant visits..." not "When I worked in the lab..."

### 2. Simple, Direct Language
✅ Short sentences (10-15 words max)  
✅ Everyday vocabulary  
✅ Conversational tone  
✅ No flowery language

### 3. Pattern Variety (90%+ Unique)
✅ 15 opening pattern types  
✅ Database tracking  
✅ Automatic rotation  
✅ Prevents repetition

### 4. Story Database
✅ Approved stories by topic  
✅ Culinary background stories  
✅ Plant visit observations  
✅ Client conversations  
✅ Universal analogies

---

## 🎓 Vitaly's Real Background

### Current Role
**Industry Sales Manager, Feed & Grain** at FOSS North America (2022-Present)
- NIR Technology Expert & Consultant (15+ years)
- Works WITH Fortune 500 clients (Nestlé, Cargill, PepsiCo, Tyson, ADM)
- Visits plants as consultant/expert
- Trains QA managers, plant managers, lab staff

### Education
- **Culinary Arts** - Chernivtsi Vocational School (Valedictorian)
- **MBA** - University of Utah
- **BS Computer Science** - Utah Valley State University
- **BS Electronics Engineering** - Chernivtsi National University

### Key Distinction
**Vitaly is the EXPERT who HELPS companies, not an employee OF those companies**

---

## 📖 Opening Pattern Types

### 15 Pattern Types:
1. **personal_story** - Real culinary/consulting experience
2. **reflective_question** - Thought-provoking question
3. **direct_fact** - Clear statement of fact
4. **surprising_statistic** - Unexpected data point
5. **cooking_metaphor** - Culinary analogy
6. **challenge** - Present a problem
7. **scenario** - Paint a picture
8. **observation** - Plant visit insights
9. **comparison** - Show contrasts
10. **universal_analogy** - Everyday examples
11. **client_conversation** - What clients say
12. **simple_truth** - Fundamental principle
13. **contrast** - Before/after, wrong/right
14. **definition** - Clear explanation
15. **bridge_concept** - Connect lessons

### Pattern Selection Strategy:
- Track usage in database
- Select least-used patterns
- Maximum 2 uses per lesson
- Aim for 90%+ variety

---

## 💡 Example Narrations

### Before (v1.0 - Flowery & Inaccurate):
> "I first met ALCOA+ principles in a lab audit. It was clear these rules keep data honest and reliable. They're the backbone of how we handle data, ensuring everything's complete, consistent, and trustworthy."

**Problems:**
- ❌ False claim ("lab audit" implies he was audited as employee)
- ❌ Long sentences
- ❌ Generic language

### After (v2.0 - Simple & Accurate):
> "QA managers often tell me, 'Vitaly, the ALCOA+ principles are like our recipe for data.' They're right. It's like when I was training in the culinary arts. A good recipe keeps your dish consistent and trustworthy."

**Improvements:**
- ✅ Accurate framing (consultant perspective)
- ✅ Short sentences (10-15 words)
- ✅ Personal culinary connection (real background)
- ✅ Conversational tone

---

## 🔧 API Endpoints

### Generate Narration
```bash
POST /api/narration/generate
Content-Type: application/json

{
  "original_text": "Sample preparation is critical...",
  "profile_id": "vitaly_kirkpatrick",
  "lesson_id": "001",
  "slide_number": 4,
  "slide_title": "ALCOA Principles",
  "opening_pattern": "client_conversation"
}
```

### Response:
```json
{
  "rewritten_text": "QA managers often tell me...",
  "word_count": 103,
  "pattern_used": "client_conversation",
  "audio_url": "/audio/001_slide_04.mp3"
}
```

---

## 📊 Pattern Variety Results

### Lesson 001 Results:
- **Total Slides:** 11
- **Unique Patterns:** 10
- **Pattern Variety:** 90.9%
- **Average Words:** 76 per slide

### Pattern Distribution:
- scenario: 2x
- simple_truth: 1x
- universal_analogy: 1x
- client_conversation: 1x
- surprising_statistic: 1x
- cooking_metaphor: 1x
- observation: 1x
- personal_story: 1x
- reflective_question: 1x
- bridge_concept: 1x

---

## 🗄️ Database Schema

### Tables:
1. **voice_profiles** - Voice settings and preferences
2. **opening_patterns_used** - Pattern usage tracking
3. **narration_history** - Generated narrations log
4. **lesson_jobs** - Batch generation jobs

### Pattern Tracking Query:
```sql
SELECT pattern_type, COUNT(*) as usage_count
FROM opening_patterns_used
WHERE profile_id = 'vitaly_kirkpatrick'
AND used_at > datetime('now', '-30 days')
GROUP BY pattern_type
ORDER BY usage_count ASC
```

---

## 🚨 Common Mistakes to Avoid

### ❌ False Background Claims:
- "When I worked in the lab..." (never worked there)
- "I first met ALCOA+ in a lab audit" (never audited)
- "In my years as a QC technician..." (never was QC tech)

### ✅ Correct Framing:
- "During plant visits, I've seen..."
- "QA managers often ask me..."
- "While helping a client implement NIR..."
- "In my culinary training..."

---

## 📝 Story Selection Guide

### For Each Slide:
1. **Culinary related?** → Use culinary story
2. **Seen in plant visits?** → Use observation story
3. **Client question?** → Use client conversation
4. **Universal concept?** → Use analogy
5. **None apply?** → Explain directly (no story)

### Story Frequency:
- 3-5 stories per lesson (8-12 slides)
- Mix story types for variety
- Not every slide needs a story
- Keep stories brief (2-3 sentences)

---

## 🔄 Deployment

### VPS Server Deployment:
```bash
# 1. Copy files to server
scp -r nir-narration-system-v2/ root@server:/var/www/

# 2. Install dependencies
ssh root@server "cd /var/www/nir-narration-system-v2 && pip install -r requirements.txt"

# 3. Setup systemd service
sudo cp deployment/narration-api.service /etc/systemd/system/
sudo systemctl enable narration-api
sudo systemctl start narration-api

# 4. Configure nginx
sudo cp deployment/nginx.conf /etc/nginx/sites-available/narration-api
sudo ln -s /etc/nginx/sites-available/narration-api /etc/nginx/sites-enabled/
sudo systemctl reload nginx
```

---

## 🧪 Testing

### Run All Tests:
```bash
pytest tests/
```

### Test AI Rewriter:
```bash
python tests/test_ai_rewriter.py
```

### Test Pattern Variety:
```bash
python tests/test_pattern_variety.py
```

### Test Story Accuracy:
```bash
python tests/test_story_accuracy.py
```

---

## 📈 Performance Metrics

### Generation Speed:
- AI Rewrite: ~3-5 seconds per slide
- Audio Generation: ~5-10 seconds per slide
- Total: ~8-15 seconds per slide

### Quality Metrics:
- Pattern Variety: 90%+ target
- Word Count: 95-120 words per slide
- Sentence Length: 10-15 words average
- Background Accuracy: 100%

---

## 🔐 Security

### API Keys:
- Store in `.env` file (never commit)
- Use environment variables in production
- Rotate keys regularly

### Database:
- SQLite for development
- PostgreSQL recommended for production
- Regular backups to Google Drive

---

## 📞 Support

### Issues:
- GitHub Issues: https://github.com/vitalykirkpatrick/clovitek/issues
- Email: vitaly@vitalykirkpatrick.com

### Documentation:
- Full docs: `/docs/`
- API docs: `/docs/API_DOCUMENTATION.md`
- Story guidelines: `/docs/STORY_GUIDELINES.md`

---

## 📜 License

MIT License - See LICENSE.md for details

---

## 🙏 Acknowledgments

- **OpenAI** - GPT-4 for AI rewriting
- **ElevenLabs** - Voice synthesis
- **FOSS North America** - Professional support

---

## 📅 Version History

### v2.0 (January 8, 2026)
- ✅ Fixed background accuracy (consultant vs employee)
- ✅ Simplified language (10-15 word sentences)
- ✅ Added pattern variety system (90%+ unique)
- ✅ Created story database
- ✅ Removed false claims

### v1.0 (December 2025)
- Initial release
- Basic AI rewriting
- ElevenLabs integration
- Pattern tracking

---

## 🎯 Next Steps

1. Generate all lessons for NIR Essentials course
2. Create Advanced NIR course story database
3. Add more opening pattern types
4. Implement A/B testing for narration styles
5. Add multi-language support

---

**For detailed documentation, see `/docs/` directory.**
