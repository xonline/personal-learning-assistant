---
name: show-preferences
description: Display Poy's learned work preferences—communication style, risk tolerance, pace, output format, and tool preferences. Shows what the plugin has learned so far with confidence levels.
example: |
  User types: /show-preferences
  Assistant displays learned preference profile
---

# /show-preferences

Display the preference profile that has been learned from your work so far.

## What You Get

```
COMMUNICATION STYLE
├─ Brevity: Prefers concise responses (confidence: 87%)
├─ Code examples: Yes, usually needed (confidence: 92%)
├─ Explanation depth: Moderate detail (confidence: 75%)
└─ Tone: Technical, casual (confidence: 85%)

RISK TOLERANCE
├─ Verification level: Thorough before action (confidence: 88%)
├─ Ask before executing: Usually (confidence: 79%)
└─ Error recovery: Safe-first approach (confidence: 90%)

PACE
├─ Speed vs thoroughness: 7/10 (balanced) (confidence: 72%)
├─ Iteration preferred: Yes (confidence: 81%)
└─ Minimal back-and-forth: Appreciated (confidence: 76%)

OUTPUT FORMAT
├─ Prefers files: Yes (confidence: 89%)
├─ Prefers inline: Only for small results (confidence: 78%)
├─ Languages: Python, TypeScript, Bash (confidence: 93%)
└─ Markdown format: Structured (confidence: 84%)

TOOL PREFERENCES
├─ Most used: Read, Write, Bash (confidence: 95%)
├─ Avoided: Rarely uses X (confidence: 70%)
└─ Efficiency signals: Quick validation before proceeding (confidence: 81%)

OVERALL CONFIDENCE
├─ Communication: 85%
├─ Risk tolerance: 86%
├─ Pace: 76%
├─ Output format: 88%
└─ Tool preferences: 91%

Last updated: 2026-03-11 14:30:00
Next review suggested: In 1-2 weeks
```

## How to Read This

- **Higher confidence %** = This pattern has been observed multiple times, system is very sure
- **Lower confidence %** = Newer pattern, might change as more data collected
- **Communication Style** = How Poy wants information delivered
- **Risk Tolerance** = How cautious vs bold Poy prefers
- **Pace** = How fast/thorough Poy works
- **Output Format** = File vs inline, language preferences
- **Tool Preferences** = Which tools work best

## Use This To

- See what's been learned about your style
- Confirm the system is tracking right
- Understand why you're getting certain responses
- Get a summary before adjusting preferences

## If Something's Wrong

If any preference is inaccurate, just tell me (e.g., "Actually I prefer X" or "That's outdated"). The feedback will update the profile.
