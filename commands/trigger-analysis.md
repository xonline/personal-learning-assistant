---
name: trigger-analysis
description: Manually trigger improvement analysis. Analyze all captured learning data, identify improvement opportunities, and generate recommendations. Run this anytime to see what could be improved.
example: |
  User types: /trigger-analysis
  Assistant analyzes all learning data and generates improvement recommendations
---

# /trigger-analysis

Manually trigger a comprehensive analysis of all learning data. Get recommendations on what could be improved based on everything learned so far.

## What This Does

This command runs an analysis across all learning data:

```
ANALYSIS PROCESS:

1. PREFERENCE CONSISTENCY CHECK
   ├─ Verify all preferences are consistent
   ├─ Identify conflicting preferences (if any)
   └─ Flag patterns that contradict stated preferences

2. ERROR PATTERN ANALYSIS
   ├─ Find most common error types
   ├─ Identify root causes that appear repeatedly
   ├─ Surface lessons that could prevent future errors
   └─ Rank errors by impact and frequency

3. SUCCESS PATTERN ANALYSIS
   ├─ Identify highest-confidence success patterns
   ├─ Find approaches that consistently work
   ├─ Surface tools/methods you always use
   └─ Recommend patterns to use more often

4. FEEDBACK vs BEHAVIOR ANALYSIS
   ├─ Check if behavior matches stated preferences
   ├─ Identify gaps between what you say and do
   ├─ Surface unstated patterns (implicit preferences)
   └─ Flag feedback that contradicts patterns

5. CONFIDENCE ASSESSMENT
   ├─ Overall confidence in learned model
   ├─ Areas with high confidence (stable patterns)
   ├─ Areas with low confidence (need more data)
   └─ Recommendations for which data is most valuable

6. RECOMMENDATION GENERATION
   ├─ What you could do more of (working well)
   ├─ What to avoid or change (not working)
   ├─ Patterns worth strengthening
   └─ Preferences worth clarifying
```

## Example Output

```
IMPROVEMENT ANALYSIS - Generated 2026-03-11 15:45:00

HIGH-CONFIDENCE RECOMMENDATIONS:
✅ KEEP DOING: Use Bash for file operations (94% success rate)
✅ KEEP DOING: Provide code examples with explanations (91% approval rate)
✅ KEEP DOING: Use checkpoint-based approach (88% efficiency)

IMPROVEMENT OPPORTUNITIES:
⚠️  EDGE CASE TESTING: 3 errors due to insufficient edge case testing
   └─ Solution: Always test at least 3 edge cases before returning
⚠️  FORMAT CONSISTENCY: 2 errors from format mismatches
   └─ Solution: Verify output format preference before generating

PATTERN CLARIFICATION NEEDED:
❓ Risk tolerance seems to vary (sometimes cautious, sometimes bold)
   └─ Ask: Does risk level depend on task type?
❓ Iteration preference unclear for certain tasks
   └─ Ask: Do you always prefer iteration or depends on situation?

CONFIDENCE REPORT:
├─ Overall model confidence: 82% (good)
├─ Preferences: 85% (high)
├─ Patterns: 88% (very high)
├─ Recommendations: 79% (moderate)
└─ Areas needing more data: Peer review preferences, deployment safety

NEXT STEPS:
1. Review recommendations above
2. Clarify uncertain patterns: "Risk tolerance depends on X"
3. After 10-20 more interactions: Re-run analysis for updated model
```

## When to Use This

- **Anytime** — Get recommendations on what could improve
- **After major work** — See if patterns changed based on recent work
- **When unsure** — Get clarity on what the system thinks you prefer
- **Before important work** — Verify system understands your preferences
- **Troubleshooting** — Figure out why you're not getting expected behavior

## What Happens After

The analysis is presented for your review. You can:

- ✅ Acknowledge recommendations ("Yes, keep doing more of X")
- ✅ Correct misunderstandings ("Actually I prefer Y not X")
- ✅ Clarify patterns ("That pattern only applies to Z situations")
- ✅ Ignore recommendations ("That's fine, don't worry about it")

No changes are automatic. You review and decide.

## Frequency

- **First run** — Recommended after 20-30 interactions
- **Regular runs** — Once a week or after major work
- **As needed** — Anytime you want recommendations

The system learns better with more data, so early analyses have lower confidence than later ones.
