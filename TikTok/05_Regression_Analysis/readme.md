# 📱 TikTok: Predictive User Verification via Logistic Regression

This project utilizes **Logistic Regression** to determine the likelihood of a TikTok user being "Verified." By analyzing video metadata and engagement metrics, the model identifies the key markers that distinguish verified creators from the general user base.

## 🎯 Project Goal
To build and evaluate a regression model that predicts `verified_status`. This provides insight into how platform engagement (views, shares, comments) and content type (claims vs. opinions) correlate with account verification.

---

## 🛠️ The PACE Workflow

### **Part 1: Plan (Imports & Loading)**
* **Environment:** Python (Pandas, Scikit-Learn, Seaborn).
* **Data:** `tiktok_dataset.csv` containing 41,000+ records.

### **Part 2: Analyze (EDA & Assumptions)**
* **Missing Data:** Identified and dropped 298 rows with null values in `claim_status` and engagement metrics.
* **Outlier Management:** Applied IQR-based capping to `video_like_count` and `video_comment_count` to prevent regression bias.
* **Class Imbalance:** Discovered that only **6.3%** of the data represented verified users. 
* **Resampling:** Executed **Minority Upsampling** to create a balanced dataset (17,884 samples per class), ensuring the model doesn't favor the majority class.
* **Multicollinearity:** Heatmap analysis revealed a high correlation (0.86) between views and likes. `video_like_count` was removed to satisfy the logistic regression assumption of no severe multicollinearity.



### **Part 3: Construct (Model Building)**
* **Feature Engineering:** * Created `text_length` from transcriptions.
    * Applied `OneHotEncoding` to `claim_status` and `author_ban_status`.
* **Data Split:** 75% Training / 25% Testing.
* **Model:** Logistic Regression with a `max_iter=800` to ensure model convergence.

### **Part 4: Execute (Evaluation & Interpretation)**
* **Performance Metrics:**
    * **Precision:** 61% (Overall)
    * **Recall:** 84% (High sensitivity for identifying unverified accounts).
    * **Accuracy:** 65%
* **Coefficient Analysis:**
    * **Claim Status:** Videos labeled as "Opinions" (rather than "Claims") significantly increase the log-odds of a user being verified.
    * **Engagement:** Share counts and comment counts show positive coefficients, while total view counts had a negligible impact once other factors were considered.

---

## 📊 Business Conclusion
The model demonstrates that while engagement metrics matter, **content categorization** (`claim_status`) and **account standing** (`author_ban_status`) are the most powerful predictors of verification. With a recall of 84%, this model serves as an effective first-pass filter for identifying potential verification candidates or auditing account authenticity at scale.

---

## 💼 Availability for Hire (UAE / Singapore / GCC)
**Najeeb P.A** | Lead Scoring & Predictive Classification Specialist
| najeebpa81@gmail.com | +65 91817634
