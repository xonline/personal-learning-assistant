---
name: error-analyzer
description: Silently capture and analyze errors, failures, and modifications Poy makes to work. Learn what went wrong and what improvements are needed. Build a library of avoided mistakes for continuous improvement.
---

# Error Analyzer

A silent tracker that captures what goes wrong and what Poy wants different. Over time, it builds a library of mistakes and improvements to avoid repeating them.

## What This Skill Does

Whenever something fails or Poy requests a change, this skill logs:

1. **What failed** — The specific task, output, or approach
2. **Why it failed** — Root cause (if identifiable)
3. **What you wanted instead** — Your preferred outcome
4. **Context** — What was being done, what went before, what comes after
5. **Lesson** — The pattern to avoid or improve on

## Error Classification

Errors are categorized for better learning:

- **Implementation errors** — Code didn't work, syntax wrong, logic flawed
- **Output format errors** — Right content, wrong format or structure
- **Approach errors** — Task done, but way you wanted different
- **Verification errors** — Didn't check thoroughly, missed edge case
- **Preference errors** — Ignored your style/pace/risk preference
- **Tool errors** — Wrong tool used for the job
- **Communication errors** — Explanation too vague, too detailed, wrong tone

## What Gets Captured

For each error:

```
{
  "timestamp": "2026-03-11T14:30:00Z",
  "error_id": "unique-hash",
  "error_type": "implementation|format|approach|verification|preference|tool|communication",
  "severity": "minor|moderate|critical",
  "what_happened": "description of failure",
  "root_cause": "why it failed",
  "what_poy_wanted": "preferred outcome",
  "context": {
    "task": "what was being done",
    "previous_output": "what came before",
    "tools_used": ["list", "of", "tools"],
    "preferences_ignored": ["list if applicable"]
  },
  "lesson": "if X then avoid Y, next time try Z",
  "confidence": 0-100
}
```

## Learning Pattern: The Error-Improvement Loop

1. **Error occurs** → Hook captures it
2. **Poy corrects it** → Hook logs the correction
3. **Pattern extracted** → "When doing X, Poy prefers Y approach"
4. **Confidence tracked** → If same error happens 3+ times, confidence increases
5. **Future prevention** → Used to guide future similar tasks

## Silent Operation

This skill:
- ✅ Logs all errors silently
- ✅ Analyzes root causes
- ✅ Extracts lessons
- ❌ Does NOT interrupt
- ❌ Does NOT suggest fixes
- ❌ Does NOT apologize or over-explain

## Data Storage

All error logs stored locally in:
```
/cowork-learning/errors.json
/cowork-learning/error-patterns.json (lessons extracted)
```

Review anytime with `/review-learning`.
