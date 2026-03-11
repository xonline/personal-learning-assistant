---
name: reset-learning
description: Clear all learned data and start fresh. Wipes preferences, error logs, patterns, and feedback. Useful if you want to reset or if learning is inaccurate.
example: |
  User types: /reset-learning
  Assistant confirms deletion and resets all learning files
---

# /reset-learning

Clear all learned data and start fresh. This command wipes everything and resets the learning system.

## What Gets Deleted

```
LEARNING FILES CLEARED:
├─ preferences.json — All learned preferences (communication, risk, pace, format, tools)
├─ errors.json — All captured errors and failures
├─ error-patterns.json — All extracted lessons from errors
├─ patterns.json — All success patterns identified
├─ pattern-confidence.json — All confidence scores for patterns
├─ feedback.json — All feedback captured
└─ feedback-lessons.json — All lessons extracted from feedback

TOTAL DATA CLEARED: Everything
REMAINING: Just the plugin (skills, commands, hooks)
```

## Why You Might Do This

- **Start fresh** — You want to reset the learning and start over
- **Inaccurate data** — The system learned the wrong patterns
- **Major change** — You changed how you work and want clean slate
- **Privacy** — You want to delete all historical data
- **Testing** — You want to see learning from zero

## How to Use It

Just type: `/reset-learning`

The system will:
1. Confirm you want to delete all learning data
2. Back up old data (optional, for safety)
3. Clear all learning files
4. Start fresh with empty learning state

## After Reset

After resetting:
- ✅ Plugin still works normally
- ✅ Skills are ready to learn again
- ✅ Commands available as before
- ✅ Hooks capture new data from scratch
- ❌ All old preferences/patterns/errors are gone

The system will take a few interactions to rebuild a new learning profile.

## Recovery

Once deleted, learning data CANNOT be recovered. So be careful! If you're unsure, use `/review-learning` first to see what will be deleted.

## Alternative: Selective Reset

Instead of full reset, you can:
- "Forget pattern X" — removes one pattern
- "Update preference Y to Z" — corrects one preference
- "That lesson is wrong" — removes one error lesson

Just tell me and I'll update selectively without full reset.
