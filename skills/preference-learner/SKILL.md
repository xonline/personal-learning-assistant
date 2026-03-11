---
name: preference-learner
description: Silently learn and capture Poy's work preferences including communication style, risk tolerance, pace, and output format. Trigger automatically during all interactions to build an accurate preference profile over time.
---

# Preference Learner

A silent observer that learns how Poy prefers to work. It captures style, approach, and behavioral patterns without interruption and stores them for later review.

## What This Skill Does

As Claude works with Poy in Cowork, this skill runs silently in the background and extracts preference signals from:

- **Communication style** — Do you prefer brief, concise responses or detailed explanations with context?
- **Risk tolerance** — Do you prefer caution (verify everything, ask questions) or action-oriented (just do it, iterate)?
- **Pace** — Do you like thorough, methodical approaches or fast iteration?
- **Output format** — Do you prefer code, markdown, files, or conversational responses?
- **Tool preferences** — Which tools do you use most? Which do you avoid?
- **Feedback patterns** — How do you typically modify or approve work?

## How It Works

1. **Observation** — Every interaction, tool use, and output is observed
2. **Signal extraction** — The skill identifies preference signals in:
   - What you approve without changes (✅ you like this style)
   - What you modify (this preference wasn't met)
   - What commands you use (reveals priorities)
   - How you phrase requests (reveals expectations)
3. **Pattern building** — Over time, patterns emerge (e.g., "Poy prefers concise, actionable responses with caution about edge cases")
4. **Storage** — Preferences are logged locally in a persistent preference file

## What Gets Captured

The preference profile includes:

```
{
  "communication_style": {
    "brief_or_detailed": "scale 1-10",
    "code_examples_needed": true/false,
    "explanation_depth": "minimal|moderate|deep",
    "tone": "formal|casual|technical"
  },
  "risk_tolerance": {
    "verification_level": "minimal|thorough|paranoid",
    "ask_before_executing": true/false,
    "error_recovery_preference": "fail_fast|safe_first"
  },
  "pace": {
    "speed_vs_thoroughness": "scale 1-10",
    "iteration_preferred": true/false,
    "minimal_back_and_forth": true/false
  },
  "output_format": {
    "prefers_files": true/false,
    "prefers_inline": true/false,
    "preferred_languages": ["py", "ts", "bash"],
    "markdown_format_preference": "structured|freeform"
  },
  "tool_preferences": {
    "most_used": ["Read", "Write", "Bash"],
    "avoided": [],
    "efficiency_signals": []
  },
  "confidence_levels": {
    "communication": 0-100,
    "risk_tolerance": 0-100,
    "pace": 0-100
  }
}
```

## Silent Operation

This skill captures signals but does NOT:
- Interrupt you
- Suggest improvements
- Ask clarifying questions
- Modify its behavior automatically

It simply logs observations. You review them later with `/review-learning` if you want.

## Data Persistence

All learned preferences are stored locally in:
```
/cowork-learning/preferences.json
```

The file is always available for review but never forced on you.
