---
name: review-learning
description: Review all captured learning data—errors encountered, lessons learned, patterns identified, and feedback processed. Comprehensive view of what the system knows about your work.
example: |
  User types: /review-learning
  Assistant shows: errors, patterns, lessons, feedback summary
---

# /review-learning

Comprehensive review of everything the plugin has learned from your work.

## Four Learning Categories

### 1. ERRORS & LESSONS LEARNED

```
Recent errors (last 7 days):
├─ Error #1: Code syntax error in Python script
│  ├─ What happened: Missing colon in if statement
│  ├─ Root cause: Rushed implementation
│  ├─ What you wanted: Proper syntax validation before returning code
│  └─ Lesson: Run syntax check before returning code-based outputs
│
├─ Error #2: Output format mismatch
│  ├─ What happened: Inline code when you wanted file
│  ├─ Root cause: Ignored your stated preference
│  └─ Lesson: ALWAYS prefer files for complex outputs
│
└─ Error #3: Insufficient verification
   ├─ What happened: Tested once, missed edge case
   ├─ Root cause: Skipped thorough testing
   └─ Lesson: Poy prefers 3+ verification approaches before claiming success

LESSON LIBRARY:
├─ Always verify 3+ ways before claiming success (confidence: 95%)
├─ Prefer files over inline for complex outputs (confidence: 93%)
├─ Run syntax check before returning code (confidence: 88%)
└─ State confidence and show evidence (confidence: 82%)
```

### 2. PATTERNS OF SUCCESS

```
High-confidence patterns (what to do MORE of):

├─ Pattern: Using Bash for file operations
│  ├─ Success rate: 94% (17 of 18 successful)
│  ├─ Confidence: Very high
│  └─ Recommendation: Continue using Bash for file tasks
│
├─ Pattern: Brief explanations with code examples
│  ├─ Success rate: 91% (approved without changes)
│  ├─ Confidence: Very high
│  └─ Recommendation: This style consistently works
│
└─ Pattern: Checkpoint-based workflow
   ├─ Success rate: 88% (quick approvals, few iterations)
   ├─ Confidence: High
   └─ Recommendation: Keep using this approach

BEHAVIORAL PATTERNS:
├─ You iterate quickly (approve/modify/continue cycle)
├─ You prefer thorough verification before deployment
├─ You reuse successful approaches (tooling, patterns)
└─ You approve outputs when preferences are met
```

### 3. FEEDBACK SUMMARY

```
Feedback received (from commands and interactions):

├─ "Just do it" (stated 2 times)
│  └─ Means: Trust, confidence, low need for back-and-forth
│
├─ "Verify this first" (stated 1 time)
│  └─ Means: Validation important for this type of task
│
├─ "I like how you..." (stated 3 times)
│  └─ Preferences confirmed: concise style, code examples, file outputs
│
└─ Modification requests: 4
   └─ Most common: Format adjustment, adding verification steps

FEEDBACK PRECEDENCE:
├─ Explicit guidance: Highest weight (overrides patterns)
├─ Recent behavior: High weight (last week data)
├─ Repeated patterns: Medium weight (confirmed over time)
└─ Historical data: Lower weight (can be overridden)
```

### 4. CONFIDENCE SUMMARY

```
Overall learning confidence by category:

├─ Preferences: 85% confident in communication/style preferences
├─ Error patterns: 88% confident in what went wrong & lessons
├─ Success patterns: 89% confident in what works well
├─ Feedback: 92% confident in explicit guidance
└─ Tool preferences: 91% confident in your tool choices

DATA QUALITY:
├─ Total interactions analyzed: 247
├─ High-confidence patterns (>85%): 12
├─ Medium-confidence patterns (60-85%): 8
├─ Low-confidence patterns (<60%): 3 (need more data)
└─ Most recent learning: 2 hours ago
```

## How to Use This

- **Verify accuracy** — Is this what you actually prefer?
- **Spot gaps** — What's missing from the learning?
- **Provide updates** — "Actually I prefer X now" or "That's outdated"
- **Understand behavior** — Why you get certain types of responses
- **Plan improvements** — What patterns you want to change

## What to do if something's wrong

Just say it:
- "That's outdated, I prefer X now"
- "That error analysis is wrong because..."
- "Add this pattern to what you've learned"
- "Forget about pattern X"

Every correction improves the system.
