# 📞 Telecom Customer Churn Prediction  

### 📘 Overview  
This project focuses on developing a **machine learning model** to predict **customer churn** for a telecom company.  
The objective is to analyze customer behavior patterns, identify the factors leading to churn, and help telecom providers take proactive measures to retain customers.  

By leveraging data-driven insights, this model aims to **reduce customer attrition**, **improve retention strategies**, and **enhance customer lifetime value**.  

---

## ⚙️ Project Workflow  

1. **Data Loading**  
   - Imported and explored the telecom customer dataset.  
   - Checked data structure, data types, and summary statistics.  
   - Identified the presence of categorical and numerical features for further processing.  

2. **Data Cleaning**  
   - Converted the `TotalCharges` column from object to numeric type.  
   - Filled missing values in `TotalCharges` using **median imputation**.  
   - Verified data consistency and ensured no null or incorrect entries remained.  

3. **Exploratory Data Analysis (EDA)**  
   - Visualized the **churn distribution** to understand class imbalance.  
   - Used **countplots** to explore categorical features (e.g., Contract Type, Payment Method, Internet Service).  
   - Plotted **histograms and boxplots** for numerical features like tenure and monthly charges.  
   - Identified key churn indicators such as:  
     - Contract Type (Month-to-month customers churn more).  
     - Tenure (newer customers are more likely to churn).  
     - Payment Method (electronic check users have higher churn rates).  

4. **Feature Engineering**  
   - Created new derived features such as:  
     - **Monthly-to-Total Charges Ratio** – captures spending consistency.  
     - **Has Internet** – indicates customers with internet services.  
   - These engineered features helped improve model interpretability and accuracy.  

5. **Outlier Detection & Handling**  
   - Used boxplots to detect and analyze outliers in numerical variables.  
   - Outliers were kept in some cases where they carried useful information about high-spending customers.  

6. **Handling Class Imbalance**  
   - Detected an imbalance between churned and non-churned customers.  
   - Applied **SMOTE (Synthetic Minority Oversampling Technique)** to balance the dataset and improve recall for churn prediction.  

7. **Data Preprocessing**  
   - Scaled numerical features using **StandardScaler**.  
   - Encoded categorical features with **One-Hot Encoding**.  
   - Ensured transformations were fit on training data to prevent data leakage.  

8. **Model Building & Selection**  
   - Implemented multiple models for comparison:  
     - **Logistic Regression**  
     - **Random Forest Classifier**  
     - **XGBoost Classifier**  
   - Used **train-test split** for evaluation and applied cross-validation for reliable performance metrics.  

9. **Model Evaluation**  
   - Evaluated models using metrics:  
     - **Accuracy**  
     - **Precision**  
     - **Recall**  
     - **F1-Score**  
     - **ROC-AUC Curve**  
   - The **XGBoost Classifier** achieved the best balance between recall and precision, making it ideal for churn detection.  

---

## 📊 Key Findings  

- 📉 **Churn Rate:**  
  Roughly **26–30%** of customers were found to have churned.  

- 💡 **Top Churn Indicators:**  
  - **Month-to-month contracts** had the highest churn.  
  - **Electronic check payments** correlated strongly with churn.  
  - Customers with **shorter tenure** and **higher monthly charges** were more likely to leave.  

- 📈 **Feature Impact:**  
  - Longer tenure and automatic payment methods significantly reduced churn risk.  
  - Internet service type (fiber optic) influenced churn due to pricing differences.  

---

## 🧠 Insights & Business Impact  

- **Retention Strategy:**  
  - Offer loyalty rewards or discounts to month-to-month customers.  
  - Promote auto-payment options to reduce churn linked with payment method issues.  

- **Predictive Use:**  
  - Identify at-risk customers early and engage them with personalized offers.  
  - Enhance marketing ROI by targeting retention campaigns more efficiently.  

- **Operational Improvement:**  
  - Focus on improving fiber-optic service satisfaction to retain high-value customers.  

---

## 🧰 Tech Stack  

| Category | Tools / Libraries |
|-----------|------------------|
| Programming | Python |
| Data Handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn, XGBoost, imbalanced-learn (SMOTE) |
| Environment | Jupyter Notebook |

---

## ✅ Results & Conclusion  

The project successfully developed a **Telecom Churn Prediction Model** capable of identifying customers likely to cancel their subscriptions.  
Key outcomes include:  
- **High predictive accuracy** using ensemble learning (Random Forest & XGBoost).  
- Enhanced ability to retain customers using actionable insights derived from EDA.  
- Balanced model performance on both classes with **SMOTE resampling**.  

The results demonstrate the power of **data-driven churn management**, enabling telecom businesses to significantly reduce customer loss.  


