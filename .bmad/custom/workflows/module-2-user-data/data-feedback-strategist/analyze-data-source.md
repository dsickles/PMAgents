---
description: Ingests quantitative (CSV) or qualitative (text) data to extract trends, sentiment, or feature requests.
---
# Analyze Data Source

## Goal
Ingests quantitative (CSV) or qualitative (text) data to extract trends, sentiment, or feature requests.

## Configuration
- **Inputs**: `Data Source` (Paste text or file path), `Focus Question` (Optional).
- **Context Needed**: None (Pure analysis).

## Steps
1.  **Detect Type**: Is this numbers (CSV) or words (Feedback)?
2.  **Process**:
    -   *If Text*: Cluster by topic, analyze sentiment per topic.
    -   *If Numbers*: Calculate mean/median, identify outliers, look for trends.
3.  **Synthesize**: Answer the "So What?" – what action should be taken?

## Output Template
```markdown
### 🔬 Data Analysis: [Source Name]
**Summary**: Analyzed 500 rows of feedback. Primary sentiment: **Negative (60%)**.

#### 📉 Key Patterns
1.  **Performance (45% of mentions)**: Users report slow load times on the dashboard.
    *   *Quote*: "It takes forever to load my reports."
2.  **Navigation (20% of mentions)**: Users are confused by the new sidebar.

#### 💡 Recommendation
Prioritize performance optimization for the Reporting Dashboard (Sprint P0).
```
