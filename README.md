# Fraud Detection with Azure AutoML

## 🚀 Overview
Financial fraud costs billions annually. Traditional rule-based systems struggle to detect sophisticated fraud patterns, so I built an **AI-powered fraud detection system** using **Azure Machine Learning AutoML** to automate model selection and hyperparameter tuning.

This project demonstrates how **AutoML** can significantly improve fraud detection with minimal manual intervention.

---
## 📂 Repository Structure
```
fraud-detection-azure-automl/
│── 📂 images/               # Folder for images used in the README
│── 📂 src/                  # Source code for preprocessing, training, and deployment
│── 📂 models/               # Saved models and evaluation reports
│── README.md                # Project documentation (this file)

```

---
## 📊 Dataset

A synthetic financial transaction dataset was used, containing labeled fraud instances. Key features include:
- **Transaction Type** (e.g., online transfer, ATM withdrawal)
- **Transaction Amount**
- **Customer Account Info** (pre/post balances)
- **Recipient Account Info**
- **Behavioral Patterns**

---
## 🔧 Environment Setup
### 1️⃣ Clone the Repository
```bash
git clone https://github.com/yourusername/fraud-detection-azure-automl.git
cd fraud-detection-azure-automl
```

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Set Up Azure ML
1. Create an **Azure Machine Learning workspace**.
2. Upload the dataset to Azure.
3. Configure an **AutoML job** with these parameters:
   - **Task Type:** Classification
   - **Primary Metric:** AUC weighted
   - **Models Tested:** XGBoostClassifier, LightGBM, RandomForest
   - **Cross-validation:** 5-fold

---
## 🖼️ Adding Images to README
To include images in this README, **upload them to the** `images/` **folder** and use the following format:
```markdown
![Description](images/your-image.png)
```

Example:
```markdown
![ROC Curve](images/roc_curve.png)
```

---
## 📈 Results
### ✅ Best Model: **XGBoostClassifier** with MaxAbsScaler preprocessing
- **Accuracy:** 99.98%
- **AUC Weighted:** 0.99951
- **Precision Score:** 99.98%
- **Recall Score:** 99.98%
- **F1 Score Weighted:** 99.98%

![Model Performance](images/model_performance.png)

### 🔍 Key Features Contributing to Fraud Detection
1. **Transaction Amount relative to Account History**
2. **Balance Deltas (Pre/Post Transaction)**
3. **Transaction Type**
4. **Timing Patterns**

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

📌 **GitHub Repository**: [Insert GitHub Link]  
📌 **LinkedIn Post**: [Insert LinkedIn Post Link]  

#DataScience #MachineLearning #FraudDetection #Azure #AutoML #Banking

