# 🛡️ Predicting Eligibility for NSAP Schemes using Machine Learning

## 📌 Problem Statement

The **National Social Assistance Program (NSAP)** is a crucial social security initiative by the Government of India that aims to provide financial aid to:

- Elderly individuals
- Widows
- Persons with disabilities  

...belonging to **Below Poverty Line (BPL)** households.

Each beneficiary must be mapped to one of several **NSAP sub-schemes**, each having specific eligibility criteria. The existing manual process of verification and scheme assignment is time-consuming and susceptible to human error, often delaying aid delivery to the most vulnerable populations.

## 🎯 Objective

To design, build, and evaluate a **multi-class classification machine learning model** that can **accurately predict** the most suitable NSAP scheme for an applicant based on their **demographic** and **socio-economic** data. The model will assist government agencies in efficiently categorizing applicants and ensuring timely benefit distribution.

---

## 🧠 Solution Approach

### ✅ Key Steps Followed:

1. **Data Preprocessing**
   - Loaded district-wise pension scheme dataset from AI Kosh.
   - Handled missing values and outliers.
   - Encoded categorical features using Label Encoding and One-Hot Encoding.
   - Scaled numerical features using `StandardScaler`.

2. **Exploratory Data Analysis (EDA)**
   - Performed distribution analysis and correlation studies.
   - Visualized:
     - Age & Gender distributions
     - Scheme-wise counts
     - Feature correlations using heatmaps and pairplots

3. **Feature Engineering**
   - Selected relevant features like:
     - Gender
     - Disability Type
     - Marital Status
     - Annual Income
     - Region

4. **Model Building & Evaluation**
   - Created an **Ensemble Model** using:
     - ✅ **Random Forest Classifier**
     - ✅ **XGBoost Classifier**
     - Combined using **Hard Voting Classifier** for robust prediction
   - Ensemble model significantly improved overall performance and generalization.
   - Performed cross-validation and hyperparameter tuning to optimize base learners.
   - Evaluated the ensemble and individual models using:
     - Accuracy
     - Precision, Recall, F1-Score
     - Confusion Matrix
     - Classification Report

5. **Prediction Interface**
   - Built a small prediction interface in the notebook.
   - Accepts new applicant data and returns the predicted eligible NSAP scheme.

6. **Deployment Strategy**
   - Developed using **IBM Watson Studio** as per challenge guidelines.
   - Stored model on **IBM Cloud Object Storage**.

---

## 🧰 Technology Stack

| Tool / Platform       | Usage                          |
|------------------------|--------------------------------|
| **Python**             | Core ML & preprocessing        |
| **Pandas, NumPy**      | Data cleaning & manipulation   |
| **Matplotlib, Seaborn**| Visualizations & EDA           |
| **Scikit-learn**       | ML models and evaluation       |
| **IBM Watson Studio**  | Model training & deployment    |
| **IBM Cloud Lite**     | Hosting and storage            |

---

## 📊 Visualizations

The following visualizations were generated for better data understanding:

- 📈 **Scheme Distribution** (bar chart)
- 🧑‍🤝‍🧑 **Gender and Age Groups** (pie chart)
- 🔥 **Feature Correlation Heatmap**
- 🟩 **Confusion Matrix**
- 🧾 **Classification Report Table**

---

## 📈 Model Performance

- **Best Model**: Ensemble Classifier (Random Forest + XGBoost with Hard Voting)
- **Test Accuracy**: ~96%
- **Precision & Recall**: High and balanced across all NSAP scheme classes
- **Prediction Time**: Optimized for fast inference, suitable for real-time deployment

---

## 🧾 Dataset Description

- **Source**: [AI Kosh Dataset](https://aikosh.indiaai.gov.in/web/datasets/details/district_wise_pension_data_under_the_national_social_assistance_programme_nsap_1.html)
- **Format**: CSV
- **Size**: District-level entries with 10+ demographic fields
- **Target Classes (Schemes)**:
  - IGNOAPS: Old Age Pension
  - IGNWPS: Widow Pension
  - IGNDPS: Disability Pension

---

## 🧪 Folder Structure
📦NSAP-scheme-eligibility-model/
┣ 📄 README.md
┣ 📄 NSAP_Model.ipynb
┣ 📄 Social Welfare Schemes.csv

---

## 🚀 Future Enhancements

- Integrate model with a **chatbot UI** to simplify eligibility screening.
- Enable **multi-lingual support** for state-level applications.
- Add **real-time data validation** using Aadhaar, Ration Card APIs.
- Explore **Deep Learning (TabNet, AutoGluon)** for automatic feature selection and model boosting.
