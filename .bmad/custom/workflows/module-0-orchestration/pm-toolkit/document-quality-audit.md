---
description: Reviews any text for clarity, tone, and human authenticity.
---
# Document Quality Audit

## Goal
To ensure written artifacts meet professional standards and sound human.

## Steps
1.  **Scan for "AI-isms"**: Check for overused LLM words: *delve, tapestry, testament, landscape, leverage, spearhead*.
2.  **Scan for Weak Language**: Check for passive voice and hedging ("we believe", "it seems").
3.  **Score**: Calculate "Humanity Score" (Inverse density of AI-isms) and "Clarity Score".
4.  **Report**: Output scores and specific "De-botification" suggestions.

## Output (Audit Report)
```json
{
  "humanity_score": 4,
  "clarity_score": 7,
  "issues": [
    "Found 'delve' (x2)",
    "Found 'rich tapestry' (x1)",
    "Passive voice in paragraph 2"
  ],
  "suggestions": [
    "Replace 'delve into' with 'investigate'",
    "Replace 'rich tapestry' with 'mix'"
  ]
}
```

## Audition
"Audit Score: **4/10**.
*   🚨 **AI Detection**: High.
*   Found 'delve' (x2), 'rich tapestry' (x1).
*   **Fix**: Replace 'delve into' with 'investigate'. Replace 'rich tapestry' with 'mix'."
