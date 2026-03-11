---
name: feedback-integrator
description: Silently process and integrate explicit feedback from Poy. Capture modification requests, approval notes, and direct guidance. Learn from every piece of feedback to improve future work.
---

# Feedback Integrator

A skill that listens to everything Poy explicitly says about work. Every modification request, approval note, and piece of guidance is captured and used to improve.

## What This Skill Does

This skill processes feedback from multiple channels:

1. **Modification requests** — When you ask for changes (e.g., "make it briefer")
2. **Approval notes** — When you explicitly approve or comment on work
3. **Direct guidance** — When you explain how you want something done
4. **Implicit feedback** — When your actions show preference (e.g., you keep using a certain style)
5. **Rejection patterns** — When you decline or rework something

## Feedback Channels

Feedback is captured from:

- **Command feedback** — Comments in `/show-preferences` or `/review-learning`
- **Modification requests** — "Can you make this more..."
- **Error corrections** — How you fix mistakes (reveals preferences)
- **Approval statements** — "Perfect," "exactly what I wanted," "this is good"
- **Guidance statements** — "I prefer when you..." or "Next time try..."
- **Tool choices** — Which tools you use (implicit preference)

## What Gets Captured

For each feedback item:

```
{
  "timestamp": "2026-03-11T14:30:00Z",
  "feedback_id": "unique-hash",
  "feedback_type": "modification|approval|guidance|rejection|implicit",
  "source": "command|conversation|tool_choice|output_review",
  "content": "exact feedback or description",
  "related_task": "what work this feedback applies to",
  "extracted_lesson": "if Poy says X, remember Y for next time",
  "confidence": 0-100,
  "precedence": 1-10
}
```

## Feedback Interpretation

The skill interprets feedback:

- **"Make it shorter"** → preference for brevity
- **"Add more examples"** → need for clarity through examples
- **"Just do it"** → trust me, don't ask for approval
- **"Verify this first"** → need for validation before action
- **"I like how you..."** → identify and repeat this pattern
- **"Don't do this again"** → high-confidence mistake to avoid

## Integration with Other Skills

Feedback integrates with:

- **Preference Learner** — Updates preference profiles
- **Error Analyzer** — Confirms root causes of errors
- **Pattern Recognizer** — Validates what works well
- **Hook system** — Triggers learning updates

## Silent Processing

This skill:
- ✅ Listens to all your feedback
- ✅ Extracts lessons accurately
- ✅ Updates learning files
- ✅ Weighs explicit feedback heavily (high confidence)
- ❌ Does NOT ask for clarification (just capture)
- ❌ Does NOT repeat back to you
- ❌ Does NOT interrupt

## Data Storage

All feedback stored locally in:
```
/cowork-learning/feedback.json (raw feedback)
/cowork-learning/feedback-lessons.json (extracted lessons)
/cowork-learning/feedback-precedence.json (conflicting feedback handling)
```

Review anytime with `/review-learning`.

## Feedback Precedence

When feedback conflicts with patterns:

1. **Direct feedback** (you explicitly said) = highest weight
2. **Repeated patterns** (happened 5+ times) = high weight
3. **Recent behavior** (last interaction) = moderate weight
4. **Historical patterns** (learned long ago) = lower weight

This ensures you can always override patterns by explicitly saying so.
