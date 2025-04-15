# Fraud Detection with Azure AutoML

## 🚀 Overview
Financial fraud costs billions annually. Traditional rule-based systems struggle to detect sophisticated fraud patterns, so I built an **AI-powered fraud detection system** using **Azure Machine Learning AutoML** to automate model selection and hyperparameter tuning.

This project demonstrates how **AutoML** can significantly improve fraud detection with minimal manual intervention.

---
## 📂 Repository Structure
```
fraud-detection-azure-automl/
│── 📂 images/               # Folder for images used in the README
│── 📂 model/               # Saved model
│── 📂 src/                  # Source code for preprocessing & training
│── README.md                # Project documentation (this file)

```

---
## 📊 Dataset

There is a lack of public available datasets on financial services and specially in the emerging mobile money transactions domain. Financial datasets are important to many researchers and in particular to us performing research in the domain of fraud detection. Part of the problem is the intrinsically private nature of financial transactions, that leads to no publicly available datasets.

I utilized a synthetic dataset generated using the simulator called PaySim as an approach to such a problem. PaySim uses aggregated data from the private dataset to generate a synthetic dataset that resembles the normal operation of transactions and injects malicious behaviour to later evaluate the performance of fraud detection methods.

Content
PaySim simulates mobile money transactions based on a sample of real transactions extracted from one month of financial logs from a mobile money service implemented in an African country. The original logs were provided by a multinational company, who is the provider of the mobile financial service which is currently running in more than 14 countries all around the world.

Source : https://www.kaggle.com/datasets/ealaxi/paysim1

Key features include:
- **Transaction Type** (e.g., online transfer, ATM withdrawal)
- **Transaction Amount**
- **Customer Account Info** (pre/post balances)
- **Recipient Account Info**

![Datascource](images/Screenshot%20(7).png)


---

### 3️⃣ Set Up Azure ML
1. Create an **Azure Machine Learning workspace**.
2. Upload the dataset to Azure.
3. Configure an **AutoML job** with these parameters:
   - **Task Type:** Classification
   - **Primary Metric:** AUC weighted
   - **Models Tested:** XGBoostClassifier, LightGBM, RandomForest
   - **Cross-validation:** 5-fold

![Azure ML Config](images/Screenshot%20(8).png)

---
## 📈 Results
### ✅ Best Model: **XGBoostClassifier** with MaxAbsScaler preprocessing
- **Accuracy:** 99.98%
- **AUC Weighted:** 0.99951
- **Precision Score:** 99.98%
- **Recall Score:** 99.98%
- **F1 Score Weighted:** 99.98%

![Metrics](images/Screenshot%20(13).png)

### 🔍 Key Features Contributing to Fraud Detection
1. **Transaction Amount relative to Account History**
2. **Balance Deltas (Pre/Post Transaction)**
3. **Transaction Type**
4. **Timing Patterns**

![Feature Engineering](images/Screenshot%20(14).png)
---
## 🚀 Deployment
The model is deployed as a **real-time Azure ML endpoint**, allowing:
- **Live fraud detection before transactions are completed**
- **Integration with existing fraud risk workflows**
- **Continuous model monitoring for concept drift**

---
## 🔥 Lessons Learned
✅ **Start Small**: AutoML jobs can be resource-intensive. Set **strict timeouts and trial limits**.  
✅ **Monitor Costs**: Running models for too long can significantly increase cloud bills.  
✅ **Feature Engineering Matters**: Even with AutoML, feature selection and preprocessing **significantly impact model performance**.  

---
## 🎯 Next Steps
1. **Implement time-based validation** to prevent data leakage.
2. **Integrate explainability tools** (SHAP, LIME) to interpret fraud predictions.
3. **Develop a model retraining pipeline** to adapt to evolving fraud tactics.

---
## 💬 Let's Connect!
I’d love to collaborate with others working on **fraud detection, fintech, and AI in banking**. Feel free to reach out or fork the repo to improve it!



#DataScience #MachineLearning #FraudDetection #Azure #AutoML #Banking

