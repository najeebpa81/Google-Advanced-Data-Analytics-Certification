# Phase 3: Exploratory Data Analysis & Visualization

**Title**: EDA findings and Tableau visuals for stakeholder communication

This notebook and accompanying Tableau dashboard present the exploratory data analysis for the TikTok claims classification project.

### Key EDA Findings
- **Engagement metrics** (`video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, `video_comment_count`) are the strongest differentiators:
  - Claim videos receive dramatically higher engagement (~100× median views, substantial differences in likes, shares, downloads, and comments).
  - Viral/high-engagement content is almost exclusively claim videos.
  - Opinion videos cluster at low engagement levels.
- **Engineered ratios** (e.g., `likes_per_view`, `shares_per_view`) confirm higher engagement intensity for claims even after normalizing for views.
- **Author ban status**: Strong signal — ~28% of claim videos come from banned/under-review authors vs. only ~7% of opinion videos.
- **Weak/non-predictive features**:
  - `video_duration_sec`: Nearly identical distributions (platform-driven).
  - `verified_status`: Minimal difference (most videos non-verified).

Outliers in engagement metrics (12–20%) represent real viral behavior and should be retained.

### Deliverables
- **`EDA.ipynb`**: Full Python analysis with systematic visualizations (overall + stratified by `claim_status`) for all key variables, outlier detection, and modeling recommendations.
- **`tableau_dashboard.twbx`**: Interactive executive dashboard summarizing insights for non-technical stakeholders:
  - KPI cards (total videos, % claims/opinions, median views).
  - Boxplots and histograms showing dramatic engagement separation.
  - Stacked bar for author ban status risk.
  - Clean, intuitive layout focused on moderation prioritization.

### Implications
Claim videos drive significantly higher visibility, interaction, and risk (banned/under-review authors). These patterns suggest algorithmic amplification of controversial content and provide clear signals for automated classification.

Findings directly inform hypothesis testing, feature selection, and modeling in subsequent phases.

→ Previous: Data preparation in `../02_Data_Understanding_and_Preparation/`  
→ Next: Statistical testing in `04_Statistical_Tests/`

*Google Advanced Data Analytics Professional Certificate – TikTok Project*

