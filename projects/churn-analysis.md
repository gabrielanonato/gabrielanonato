---
layout: page
title: Customer Churn Prediction (Python + ML)
permalink: /projects/churn-analysis
---

![Churn Model](/assets/img/churn-model.png){: .project-hero }

**Goal:** Predict which customers are at risk of cancelling and why.  
**Dataset:** Telco Customer Churn (Kaggle) or similar.  
**Tools:** Python (pandas, scikit-learn), matplotlib, Jupyter.

### Problem & Metrics
- **Binary classification**: churn (yes/no)  
- Metrics: Accuracy, Precision/Recall, F1, ROC AUC

### Workflow
1. Cleaning and **encoding** of categoricals
2. Train/test split with **stratification**
3. Baseline with **Logistic Regression**
4. Compare with **Random Forest**
5. **Explainability**: feature importance / coefficients
6. Threshold tuning for business targets (e.g., Recall ≥ 0.75)

### Code Highlights (excerpt)
```python
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, roc_auc_score
# ...
pipe.fit(X_train, y_train)
pred = pipe.predict(X_test)
proba = pipe.predict_proba(X_test)[:,1]
print(classification_report(y_test, pred))
print("ROC AUC:", roc_auc_score(y_test, proba))
```

**Links:** [Notebook](<add-link>) · [Repo](<add-link>)
