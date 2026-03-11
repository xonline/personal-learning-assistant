---
name: pattern-recognizer
description: Silently identify and recognize what's working well. Track successful approaches, popular commands, approved outputs, and patterns of success. Learn what to do MORE of.
---

# Pattern Recognizer

A silent tracker of success. While Error Analyzer tracks what goes wrong, this skill tracks what goes right—and builds a library of winning patterns.

## What This Skill Does

This skill observes what works and gets better:

1. **Success tracking** — Logs when Poy approves output without changes
2. **Command analysis** — Tracks which commands/approaches you use most
3. **Approach patterns** — Identifies which strategies consistently succeed
4. **Tool effectiveness** — Recognizes which tools work best for different tasks
5. **Style validation** — Confirms when preferences were met well

## Success Signals

The skill identifies success through:

- **No modifications** — You approve output as-is (✅ this style worked)
- **Reuse patterns** — You use same command/approach multiple times (✅ you like this)
- **Positive feedback** — You explicitly approve or praise work
- **Retention** — You keep using the same approach (✅ proven effective)
- **Speed** — Fast completion without back-and-forth (✅ efficient)

## What Gets Captured

For each success pattern:

```
{
  "timestamp": "2026-03-11T14:30:00Z",
  "pattern_id": "unique-hash",
  "pattern_type": "approach|command|tool|style|format",
  "description": "what worked well",
  "success_signals": [
    "approved_without_changes",
    "used_again_on_2026-03-11",
    "faster_than_baseline"
  ],
  "context": {
    "task_type": "category of work",
    "tools_used": ["list", "of", "tools"],
    "preferred_style_met": ["list", "of", "preferences"],
    "efficiency_gain": "20% faster than alternative"
  },
  "frequency": 3,
  "last_successful_use": "2026-03-11T14:30:00Z",
  "confidence": 85,
  "recommendation": "use this approach for similar tasks"
}
```

## Pattern Categories

- **Approach patterns** — "When task is X, approach Y consistently succeeds"
- **Command patterns** — "You always use `/show-preferences` when starting"
- **Tool patterns** — "You prefer Bash over Python for file operations"
- **Style patterns** — "You approve concise explanations with code examples"
- **Format patterns** — "You want results as files, not inline"
- **Pace patterns** — "You iterate quickly when building, prefer thorough review when deploying"

## Silent Operation

This skill:
- ✅ Tracks successes silently
- ✅ Builds confidence over time
- ✅ Identifies winning patterns
- ❌ Does NOT change behavior automatically
- ❌ Does NOT push patterns
- ❌ Does NOT over-celebrate

## Data Storage

All pattern data stored locally in:
```
/cowork-learning/patterns.json (success patterns)
/cowork-learning/pattern-confidence.json (confidence scores)
```

Review anytime with `/review-learning`.

## Learning Over Time

The more you work with Cowork:
- Pattern confidence increases (from 40% → 95%)
- Recommendations become more specific
- Approach suggestions become more accurate
- The system knows what you like AND what you dislike
