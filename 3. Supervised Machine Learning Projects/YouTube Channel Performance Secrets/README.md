# 🎥 YouTube Channel Performance Secrets  

### 📘 Overview  
This project explores **the hidden patterns behind successful YouTube channels** through data analysis and machine learning.  
It identifies **key performance drivers** such as video timing, length, engagement, and category — and uses predictive modeling to forecast metrics like **revenue, engagement, and growth potential**.  

The project applies multiple regression models and identifies **Gradient Boosting Regressor** as the best-performing model with an **R² score of 0.97**, demonstrating excellent predictive capability.  

---

## ⚙️ Project Workflow  

### 1️⃣ Objective Definition  
- Understand what makes certain YouTube videos and channels perform better than others.  
- Analyze metrics like views, likes, comments, and engagement rate.  
- Develop a predictive model to forecast video performance and revenue.  

---

### 2️⃣ Data Loading  
- Dataset: `youtube_channel_real_performance_analytics.csv`.  
- Imported using **Pandas** and validated for missing or inconsistent entries.  
- Previewed columns:  
  `Views`, `Likes`, `Comments`, `Subscribers`, `Revenue`, `Video Duration`, `Upload Time`, etc.  

---

### 3️⃣ Data Cleaning & Preprocessing  
- Handled missing values and duplicates.  
- Converted `Upload Time` into **datetime format**.  
- Extracted **temporal features** like `Year`, `Month`, `Day`, and `Hour`.  
- Calculated **Engagement Rate**:  
  (Likes + Comments) / Views  
- Calculated **Revenue per 1000 Views (RPM)**:  
  Revenue / (Views / 1000)  
- Normalized numerical data for model efficiency.  

---

### 4️⃣ Exploratory Data Analysis (EDA)  
Performed comprehensive EDA to uncover relationships between features and outcomes:  

- **Correlation Analysis:** Strong relationship between `Views`, `Likes`, and `Revenue`.  
- **Time-Based Patterns:**  
  - Videos uploaded on **evenings and weekends** performed best.  
  - Higher engagement observed for uploads during **prime viewing hours (5–9 PM)**.  
- **Category Trends:**  
  - *Technology* and *Lifestyle* channels had the highest engagement.  
- **Duration Insight:**  
  - Videos between **8–12 minutes** achieved the best retention and monetization.  

Visualizations included pairplots, heatmaps, bar charts, and line graphs (Matplotlib & Seaborn).  

---

### 5️⃣ Feature Engineering  
Created derived features for improved model understanding:  
- `Engagement Rate`, `RPM`, `Upload Hour`, and `Upload Day`.  
- Encoded categorical data such as **Channel Category** for numerical modeling.  
- Split dataset into **Training (80%)** and **Testing (20%)**.  

---

### 6️⃣ Model Development  
Implemented and compared multiple machine learning models for **performance prediction**:  

| Model | Description |
|--------|-------------|
| **Linear Regression** | Simple baseline model to establish a reference. |
| **K-Nearest Neighbors (KNN)** | Captures local relationships between engagement and revenue. |
| **Support Vector Machine (SVM)** | Learns non-linear boundaries in feature space. |
| **Random Forest Regressor** | Ensemble model that reduces overfitting and captures feature interactions. |
| **Gradient Boosting Regressor** | Sequential model that minimizes residual errors — the top performer. |

---

### 7️⃣ Model Evaluation  

| Model | R² Score | RMSE | MAE | Remarks |
|--------|----------|------|-----|----------|
| Linear Regression | 0.84 | Moderate | Moderate | Basic model for comparison |
| KNN | 0.88 | Lower | Better | Performs well on smaller datasets |
| SVM | 0.90 | Low | Good | Handles non-linearity effectively |
| Random Forest | 0.94 | Lower | Lower | Strong ensemble learner |
| **Gradient Boosting** | **0.97** | **Lowest** | **Lowest** | 🚀 Best-performing model |

✅ **Best Model:** Gradient Boosting Regressor  
It achieved an **R² of 0.97**, indicating excellent predictive accuracy and robustness in modeling complex relationships.  

---

### 8️⃣ Findings & Insights  

| Category | Key Findings |
|-----------|--------------|
| **Timing** | Evening uploads (5–9 PM) and weekends drive higher engagement. |
| **Video Length** | 8–12 minutes yields best viewer retention and monetization. |
| **Engagement** | Likes and comments are strong predictors of revenue. |
| **Subscribers** | Consistent upload frequency improves growth. |
| **Revenue Drivers** | Engagement Rate and Duration are key influencing features. |

---

## 🧠 Business & Strategic Insights  

- **For Creators:** Optimize upload timing and maintain consistency.  
- **For Marketing Teams:** Invest in categories and durations that sustain engagement.  
- **For YouTube Analytics:** Use model insights to improve content recommendations.  
- **For Revenue Strategy:** Focus on boosting engagement rather than only views.  

---

## 🧰 Tech Stack  

| Category | Tools / Libraries |
|-----------|------------------|
| Programming | Python |
| Data Handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Models Implemented | Linear Regression, KNN, SVM, Random Forest, Gradient Boosting |
| Environment | Jupyter Notebook |

---

## ✅ Results & Conclusion  

This project successfully built a **data-driven YouTube analytics system** capable of identifying and predicting performance drivers.  

**Key Achievements:**  
- Performed complete data cleaning, exploration, and feature engineering.  
- Implemented and compared five ML models for predictive accuracy.  
- Achieved **R² = 0.97** with the **Gradient Boosting Regressor**.  
- Delivered actionable insights into **engagement, monetization, and content optimization**.  

**Conclusion:**  
Gradient Boosting proved to be the most reliable and accurate approach for predicting YouTube channel success metrics, enabling creators and marketers to make smarter, data-backed decisions.  

---

