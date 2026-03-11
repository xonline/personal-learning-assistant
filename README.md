# Personal Learning Assistant

A self-improving AI companion that learns how **you** like to work. Silently captures your preferences, learns from errors, recognizes success patterns, and improves continuously—all without interrupting you.

## 🎯 What It Does

This plugin watches everything and learns:

- **Your preferences** — Communication style, risk tolerance, pace, output format
- **From your mistakes** — Errors, what went wrong, what you'd prefer instead
- **What works well** — Patterns you use repeatedly, approaches that succeed
- **From your feedback** — Every comment, modification, and explicit guidance

Everything is captured silently. You review it anytime you want.

## 🔄 How It Works

### Three Tiers of Learning

**Tier 1: Silent Capture** (Hooks)
- After every tool execution, learning signals are captured
- No interruptions, no notifications
- Data stored locally in `/cowork-learning/`

**Tier 2: Pattern Recognition** (Skills)
- Preferences Learner → identifies your style
- Error Analyzer → learns from failures
- Pattern Recognizer → finds success patterns
- Feedback Integrator → processes your explicit guidance

**Tier 3: Review & Improvement** (Commands)
- `/show-preferences` — See what's been learned about you
- `/review-learning` — Comprehensive review of all data
- `/trigger-analysis` — Get improvement recommendations
- `/reset-learning` — Clear everything and start fresh

### Technical Architecture

This plugin uses Cowork's hook system to operate silently:

**PostToolUse Hook** (Automatic Signal Capture)
- Triggered after every tool execution (Bash, Read, Write, etc.)
- Captures: tool name, input, output, success/failure, execution time
- Inference: derives signals about your preferences and error patterns
- Storage: appends to `/cowork-learning/patterns.json`
- Result: No user interaction required

**SessionStart Hook** (Preference Loading)
- Triggered when you start a new Cowork session
- Loads: learned preferences from `/cowork-learning/preferences.json`
- Application: applies learned preferences to initial context
- Result: System knows your style from the first interaction

**How This Differs from Manual Learning:**
- Traditional ML: user trains model → explicit labels required
- Manual feedback: you tell system what's wrong → interrupts your work
- This plugin: silently observes your feedback through modifications → learns continuously

### Data Flow & Storage

```
Cowork Session
    ↓
Tool Execution (Bash, Read, Write, etc.)
    ↓
PostToolUse Hook (triggered automatically)
    ↓
4 Skills Process the Signal:
├─ preference-learner → infers working style
├─ error-analyzer → captures failures
├─ pattern-recognizer → finds success patterns
└─ feedback-integrator → detects your modifications
    ↓
Local JSON Storage (/cowork-learning/)
├─ preferences.json → your style profile
├─ errors.json → failures and lessons
├─ patterns.json → what works for you
└─ feedback.json → your corrections
    ↓
SessionStart Hook (next session)
    ↓
Your preferences automatically applied
```

### Git Integration with Cowork

The plugin code itself is version-controlled on GitHub:

**Repository:** `https://github.com/xonline/personal-learning-assistant`

**File Structure:**
```
personal-learning-assistant/
├── .claude-plugin/
│   └── plugin.json (manifest)
├── skills/
│   ├── preference-learner/SKILL.md
│   ├── error-analyzer/SKILL.md
│   ├── pattern-recognizer/SKILL.md
│   └── feedback-integrator/SKILL.md
├── commands/
│   ├── show-preferences.md
│   ├── review-learning.md
│   ├── trigger-analysis.md
│   └── reset-learning.md
├── hooks/
│   └── hooks.json (PostToolUse & SessionStart)
├── README.md
└── LICENSE

```

**Why Git Matters:**
- Plugin code tracked and versioned on GitHub
- Easy to share with others
- Updates can be published as new releases
- Community can contribute improvements
- Your learning data stays local (not in Git)

**What's NOT in Git:**
- `/cowork-learning/` directory — excluded by `.gitignore`
- Your personal learning data — stays private on your machine
- Logs or temporary files — excluded by `.gitignore`

### How Cowork Plugins Work (Context for This Plugin)

When you install this plugin in Cowork:

1. **Plugin Installation**
   - `.plugin` file (ZIP archive) extracted
   - `plugin.json` read to register skills and commands
   - Skills registered with Cowork system
   - Hooks subscribed to events

2. **During Your Session**
   - Every tool you use (Bash, Read, Write, etc.) → PostToolUse hook fires
   - Hook passes tool metadata to 4 skills
   - Skills process and store learning data
   - You don't see any UI or interruption

3. **When You Request Learning Review**
   - Run `/review-learning` command
   - Triggers skill to aggregate all captured data
   - Formats and presents findings to you
   - You can approve, correct, or modify

4. **On Next Session Start**
   - SessionStart hook loads your preferences
   - System applies what it learned
   - You benefit from learned preferences immediately

### Why This Architecture Works

**Silent Learning**
- No modal dialogs asking "Did you like that?"
- No inline notifications
- No interruptions to your flow
- Data captured from *your actions*, not questions

**Local Privacy**
- Learning data stored in `/cowork-learning/` on your machine
- Cowork can't see it without filesystem access
- No cloud services involved
- You control when to review

**Automatic Improvement**
- More interactions → better accuracy
- Learning compounds over time
- Early models imperfect; later models refined
- Confidence scores show how much data supports each preference

**On-Demand Control**
- Review learning whenever you want
- Correct inaccuracies anytime
- Reset everything if needed
- Guide the learning with explicit feedback

## 🚀 Getting Started

### First Time

Just use Cowork normally. The plugin works silently in the background, learning from everything you do.

### After a Few Days

Run `/review-learning` to see what's been captured:
- What errors you've made and lessons learned
- What patterns of success you have
- What your preferences look like
- Overall confidence in the model

### Provide Feedback Anytime

- "I prefer X" — corrects a misunderstood preference
- "That lesson is wrong because..." — fixes an error analysis
- "Keep doing more of this" — confirms a success pattern
- Just tell me and the system updates

## 📊 Learning Data

All learning is stored locally in `/cowork-learning/`:

```
/cowork-learning/
├── preferences.json — Your style profile
├── errors.json — Failures and lessons
├── patterns.json — Success patterns
├── feedback.json — Feedback captured
└── analysis-log.json — Analysis runs
```

**Privacy:** All data stays on your machine. Nothing leaves your laptop.

**Data Format Example (preferences.json):**
```json
{
  "communication_style": {
    "brevity_preference": {
      "score": 0.78,
      "value": "concise",
      "confidence": 0.82,
      "observations": 24
    },
    "explanation_depth": {
      "score": 0.65,
      "value": "moderate",
      "confidence": 0.71,
      "observations": 18
    }
  },
  "risk_tolerance": {
    "verification_level": {
      "score": 0.45,
      "value": "ask-first",
      "confidence": 0.89,
      "observations": 34
    }
  }
}
```

## 💡 Commands Reference

| Command | Purpose |
|---------|---------|
| `/show-preferences` | Display learned preferences with confidence levels |
| `/review-learning` | See errors, patterns, lessons, feedback summary |
| `/trigger-analysis` | Get improvement recommendations based on learning |
| `/reset-learning` | Clear all data and start fresh |

## 🎓 What Gets Learned

### Communication Style
- Preference for brevity vs detail
- Need for code examples
- Explanation depth preference
- Tone (formal vs casual)

### Risk Tolerance
- Verification level (minimal to paranoid)
- Ask-before-executing preference
- Error recovery approach
- Caution vs action-oriented

### Pace
- Speed vs thoroughness balance
- Iteration preference
- Back-and-forth tolerance

### Output Format
- Files vs inline preference
- Programming language preferences
- Markdown format style

### Tool Preferences
- Most-used tools
- Tools to avoid
- Efficiency patterns

### Success Patterns
- Approaches that work consistently
- Techniques you reuse
- Tools you always choose

### Error Lessons
- Mistakes and root causes
- What you want instead
- Patterns to avoid

## 🔐 Privacy & Control

- ✅ All data stored locally
- ✅ No data sent to cloud
- ✅ You control what's learned
- ✅ You can reset anytime
- ✅ Completely private
- ✅ Learning data excluded from Git repo

## ⚙️ How It Learns

### Automatic Learning (Hooks)
After every tool execution:
1. Success/failure captured
2. Output quality assessed
3. Tool effectiveness logged
4. Preferences inferred
5. Errors flagged

### Your Feedback
- Approvals confirm preferences
- Modifications reveal mismatches
- Explicit guidance overrides patterns
- Corrections improve accuracy

### Continuous Improvement
Learning compounds over time:
- 10 interactions = initial patterns
- 50 interactions = emerging confidence
- 100+ interactions = high-confidence model
- Patterns get refined continuously

## 🛠️ Customization

The plugin learns automatically, but you can customize by:
- Running `/review-learning` and correcting inaccuracies
- Using `/trigger-analysis` to get recommendations
- Explicitly stating preferences ("I prefer X")
- Resetting with `/reset-learning` if needed

## 📈 Confidence Scores

Each learned preference has a confidence score (0-100):
- **90-100%** = Very confident (observed many times, consistent)
- **70-89%** = Confident (observed multiple times)
- **50-69%** = Moderate confidence (emerging pattern)
- **<50%** = Low confidence (need more data)

Confidence increases as more data is observed. Early analyses have lower confidence; later ones are more accurate.

## 🔄 Integration with Oracle Server

This plugin works standalone locally. If you also want to integrate with your Oracle server's self-improvement framework, the learning files can be synced to:

```
Oracle Server: /cowork-learning/
```

For now, everything runs locally on your machine.

## 📝 Example Learning Session

### Day 1-3
- Plugin silently observes tool use
- Captures success/failure signals
- Starts building initial preferences

### Day 4-5
- `/review-learning` shows emerging patterns
- You confirm 3-4 preferences are accurate
- You correct 1 preference ("Actually I prefer X")

### Day 6+
- Confidence increases as patterns repeat
- `/trigger-analysis` starts giving meaningful recommendations
- System knows your style and applies it automatically
- `/show-preferences` shows detailed, high-confidence profile

## 🎯 Goals

This plugin exists to:
1. **Learn you** — Understand how you work
2. **Adapt** — Match your preferences without asking
3. **Improve** — Get better at helping you over time
4. **Respect** — Do it silently, on your terms
5. **Empower** — Let you review and guide learning

## 📞 Getting Help

If something seems wrong:
- Run `/review-learning` to see what was captured
- Run `/trigger-analysis` to get recommendations
- Tell the system: "That's not right, actually I prefer..."
- Use `/reset-learning` if you want a fresh start

## 🎓 Tips for Best Learning

1. **Be explicit about preferences** — "I prefer this" helps the system learn faster
2. **Review periodically** — `/review-learning` every 1-2 weeks
3. **Correct mistakes** — If learned preference is wrong, say so
4. **Give time** — System learns better with 50+ interactions
5. **Trust the process** — Over time it gets very accurate

---

**Version:** 0.1.0
**Author:** Poy
**Storage:** Local machine only
**Privacy:** 100% private, nothing leaves your laptop
**Repository:** https://github.com/xonline/personal-learning-assistant

Enjoy your personal learning assistant! 🚀
