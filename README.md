## 📌 Final Model Selection – Customer Churn Prediction

### 🎯 Objective

The goal of this project was to build a machine learning model capable of accurately predicting customer churn while balancing the trade-off between identifying churners (recall) and minimizing false alarms (precision).

---

### ⚙️ Models Evaluated

Three models were developed and evaluated:

* Logistic Regression (baseline model)
* Random Forest Classifier
* XGBoost Classifier

---

### 📊 Model Performance Comparison

| Model               | ROC-AUC   | Recall (Churn) | Precision (Churn) | Accuracy |
| ------------------- | --------- | -------------- | ----------------- | -------- |
| Logistic Regression | ~0.75     | Moderate       | Low               | 0.74     |
| Random Forest       | **0.886** | 0.63           | **1.00**          | 0.95     |
| XGBoost             | 0.871     | **0.73**       | 0.93              | 0.95     |

---

### 🧠 Model Behavior Insights

* **Logistic Regression** served as a baseline but underperformed in capturing complex patterns in the data.

* **Random Forest** achieved the highest ROC-AUC and perfect precision, meaning it was extremely conservative in predicting churn. However, it failed to identify a significant portion of actual churners (lower recall).

* **XGBoost** provided the best balance between precision and recall, successfully identifying more churners while maintaining high accuracy and strong precision.

---

### 🏆 Final Model Selection: XGBoost

XGBoost was selected as the final model due to its balanced performance:

* High recall (73%) → captures more at-risk customers
* Strong precision (93%) → minimizes unnecessary interventions
* Robust ROC-AUC (0.87) → strong overall predictive power

This makes it the most suitable model for real-world business applications where both customer retention and operational efficiency are important.

---

### 🔍 Feature Importance Insights

Feature importance and SHAP analysis revealed the key drivers of churn:

* **International plan** and **customer service calls** were the strongest predictors
* High **total day minutes/charges** significantly increased churn likelihood
* **International usage (calls & minutes)** also contributed to churn risk
* Customers with fewer service interactions or lower usage were less likely to churn
<img width="1110" height="691" alt="Screenshot 2026-04-17 094210" src="https://github.com/user-attachments/assets/a068df85-8f16-456e-98ee-4ecedf019da8" />

---

### 📈 Explainability (SHAP Insights)

SHAP analysis provided both global and individual-level explanations:

* High values of customer service calls and usage metrics pushed predictions toward churn
* Certain features (e.g., absence of international plan or lower usage) reduced churn probability
* The model is interpretable and suitable for business decision-making
<img width="811" height="773" alt="Screenshot 2026-04-17 100227" src="https://github.com/user-attachments/assets/992819dc-08fe-436d-9125-71bc15a84afd" />
<img width="1109" height="755" alt="Screenshot 2026-04-17 100154" src="https://github.com/user-attachments/assets/03a88f47-ae54-4f83-b2f2-c0dca1a5e264" />

---

### 💼 Business Impact

The final model enables:

* Early identification of high-risk customers
* Targeted retention strategies (e.g., improved support, pricing adjustments)
* Reduction in revenue loss due to churn

---

### ✅ Conclusion

XGBoost was selected as the final model due to its superior balance between identifying churners and maintaining prediction reliability. Combined with SHAP explainability, the model not only performs well but also provides actionable insights into customer behavior.

---
