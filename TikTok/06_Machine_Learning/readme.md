# 🤖 TikTok: Advanced Content Classification (Random Forest & XGBoost)

This project implements state-of-the-art ensemble learning to classify TikTok content into two distinct categories: **Claims** and **Opinions**. Using the **PACE** (Plan, Analyze, Construct, Execute) framework, this model provides platform moderators with a highly accurate tool for automated content auditing.

## 🎯 Project Objective
The goal is to develop a "Champion Model" that predicts whether a video presents a factual **claim** or a personal **opinion**. High-accuracy classification in this area is vital for prioritizing human moderation of potentially sensitive or misleading information.

---

## 🛠️ Technical Workflow (PACE)

### **1. Plan & Analyze**
* **Data Profile:** 19,382 unique TikTok videos.
* **Balance Check:** The dataset is perfectly balanced (~50% Claims, ~50% Opinions), requiring no resampling.
* **Feature Engineering:** * Created `text_length` to measure transcription complexity.
    * Utilized `CountVectorizer` to perform **N-Gram extraction** (2-3 word phrases), converting raw text into 15 high-impact numerical features like "media claim," "social media," and "point view."

### **2. Construct (Modeling & Hyperparameter Tuning)**
To find the best possible solution, two powerful architectures were compared using `GridSearchCV` with a focus on **Recall**:

* **Random Forest Classifier:** * Tuned `max_depth`, `max_features`, and `n_estimators`.
    * Achieved an exceptional Cross-Validation Recall of **0.995**.
* **XGBoost (Extreme Gradient Boosting):**
    * Optimized via `learning_rate` and `min_child_weight`.
    * Delivered high performance but slightly lower precision than Random Forest.

### **3. Execute (Evaluation)**
* **Champion Model:** Random Forest.
* **Validation Accuracy:** ~100% (with only 10 misclassifications out of 3,817 samples).
* **Test Performance:** Confirmed model stability on unseen data with near-perfect Confusion Matrix results.
* **Feature Importance:** Analysis revealed that **video engagement metrics** (views, likes, shares) are the strongest predictors of content type, far outweighing individual author status.

---

## 📈 Key Insights for Stakeholders
* **Engagement as a Proxy:** High-engagement videos are statistically more likely to be "Claims." This allows the platform to automatically flag high-reach content for closer factual scrutiny.
* **N-Gram Impact:** Phrases like "colleague discovered" or "internet forum" were significant indicators in the transcription text that helped the model distinguish opinions from claims.
* **Model Reliability:** Because the Random Forest model achieved near-perfect scores on the test set, it is recommended for deployment as a primary automated filter for content moderation pipelines.

---

## 🖼️ Visual Highlights
* **Feature Importance Bar Chart:** Visualizing the "Mean Decrease in Impurity" to show which metrics drive the model's decisions.
* **Confusion Matrix:** Demonstrating the minimal error rate between verified and unverified predictions.

---

## 💼 Availability for Hire (UAE / Singapore / GCC)
**Najeeb P.A** | Lead Scoring & Predictive Classification Specialist
[LinkedIn Profile] | najeebpa81@gmail.com | +65 91817634
