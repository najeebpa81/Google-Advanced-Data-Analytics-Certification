# Phase 4: Statistical Tests

**Statistical analysis to inform modeling decisions.**

This notebook applies inferential statistics and hypothesis testing to validate key EDA findings.

### Key Tests & Results
- **Two-sample t-test** on `video_view_count` by `verified_status`:
  - Statistically significant difference (p < 0.001).
  - Unverified accounts have higher average views, suggesting behavioral differences (e.g., clickbait or bot activity).
- Additional tests can be extended to engagement metrics vs. `claim_status` and chi-square for `author_ban_status`.

### Insights
- Confirmed significant differences in engagement between account types.
- Supports EDA conclusions: engagement and author risk are strong predictors of claim status.
- Outliers retained as they represent real viral behavior.

### Next Steps
Findings guide feature selection and baseline modeling (logistic regression) in subsequent phases.

→ Previous: EDA & Visualization in `../03_EDA_and_Visualization/`  
→ Next: Regression Modeling in `05_Regression_Modeling/`

*Google Advanced Data Analytics Professional Certificate – TikTok Project*

