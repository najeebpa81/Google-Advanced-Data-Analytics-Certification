# Phase 2: Data Understanding and Preparation

This notebook covers initial data loading, inspection, and understanding of the TikTok claims classification dataset.

**Key Activities**:
- Load and examine dataset structure (`head()`, `info()`, `describe()`).
- Identify data types, missing values, and potential outliers.
- Explore target variable distribution (`claim_status`).
- Investigate key predictors:
  - Dramatic differences in engagement (views ~100x higher for claims).
  - Strong association with `author_ban_status`.
- Feature engineering: Create engagement ratios (likes/shares/comments per view) to normalize for view volume.

**Major Insights**:
- Near-balanced classes (~50.7% claims).
- `video_view_count` and `author_ban_status` show strongest separation between claims and opinions.
- Engineered ratios reveal higher engagement intensity for claim videos.

These findings inform subsequent EDA, hypothesis testing, and modeling phases.

→ Next: Deeper EDA and visualizations in `03_EDA_and_Visualization/`

*Google Advanced Data Analytics Certificate – TikTok Project*

