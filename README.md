# Mental_Health_Treatment_Outcomes
A study used to identify the key behavioural, clinical, and treatment-related variables that predict improvement in mental health outcomes. The purpose is to help treatment providers understand which factors most strongly support recover.

# Predicting Treatment Outcomes in Mental Health Care

## 1. Project Overview

This project analyzes patient-level mental health treatment data to understand **which factors are most strongly associated with clinical improvement**.

Using a dataset of anonymized patients with common mental health diagnoses, I explore how variables such as **symptom severity, sleep quality, stress level, treatment adherence, and therapy type** relate to whether a patient’s condition **improves, remains unchanged, or deteriorates** over the course of treatment.

The goal is to:

- Identify key predictors of **treatment improvement**
- Build a simple, interpretable model to **estimate improvement likelihood**
- Translate findings into **practical recommendations** for mental health providers and digital health teams

---

## 2. Research Question

**Main Question**

> Which patient and treatment-related factors best predict whether a mental health patient will show clinical improvement?

**Sub-questions**

- Do patients with higher **treatment adherence** improve more often?
- How do **sleep quality**, **stress level**, and **mood score** relate to outcomes?
- Are certain **therapy types** associated with higher improvement rates?
- Does **initial symptom severity** hinder improvement, or can adherence and treatment duration compensate?

---

## 3. Data Description

**Source:** Internal CSV file: `mental_health_diagnosis_treatment_.csv`  
*(Note: This dataset is anonymized and synthetic / de-identified for analysis purposes.)*

Each row represents one patient’s treatment episode with the following example fields:

- **Demographics**
  - `Age`
  - `Gender`
  - `Diagnosis` (e.g., Major Depressive Disorder, Generalized Anxiety Disorder)

- **Clinical & Behavioral Variables**
  - `Symptom_Severity` (1–10)
  - `Mood_Score` (1–10)
  - `Sleep_Quality` (1–10)
  - `Stress_Level` (1–10)
  - `Physical_Activity` (hours per week)

- **Treatment Variables**
  - `Therapy_Type` (e.g., CBT, Psychodynamic, Group)
  - `Medication` (Yes/No or medication type)
  - `Treatment_Duration_Weeks`
  - `Adherence_Percentage` (0–100)
  - `Treatment_Progress` (1–10)

- **Outcome & AI-Supported Signals**
  - `AI_Emotional_State` (e.g., Calm, Anxious, Depressed, Stressed)
  - `Outcome` (Improved / No Change / Deteriorated)

For modeling, the outcome is binarized as:

- `1` = Improved  
- `0` = Not improved (No Change + Deteriorated)

---

## 4. Methods

### 4.1 Tools & Technologies

- **Languages:** Python (Pandas, NumPy, Scikit-learn, Matplotlib/Seaborn)  
- **Notebook Environment:** Jupyter Notebook  
- **Visualization / Dashboard (optional):** Power BI or Tableau  
- **Other:** Excel for quick checks and initial exploration

*(Update this section with the exact tools you end up using.)*

### 4.2 Analysis Steps

1. **Data Loading & Cleaning**
   - Load raw data from `data/raw/mental_health_diagnosis_treatment_.csv`
   - Handle missing values and outliers
   - Encode categorical variables (e.g., `Therapy_Type`, `Medication`, `AI_Emotional_State`)
   - Create binary outcome variable (`Improved` vs `Not Improved`)

2. **Exploratory Data Analysis (EDA)**
   - Distribution of key variables (age, symptom severity, stress level, etc.)
   - Breakdown of **Outcome** categories
   - Group comparisons:
     - Adherence vs Outcome
     - Sleep quality vs Outcome
     - Stress level vs Outcome
   - Outcome rates by:
     - Diagnosis
     - Therapy type
     - Medication usage

3. **Modeling**
   - Train-test split of the dataset
   - Baseline model: **Logistic Regression**
   - Optionally: Tree-based model (e.g., Random Forest) for feature importance
   - Evaluation metrics:
     - Accuracy
     - Precision / Recall
     - Confusion matrix
     - ROC-AUC (optional)

4. **Interpretation & Insights**
   - Identify which variables most strongly predict improvement
   - Translate model coefficients / feature importance into non-technical language
   - Discuss limitations (e.g., synthetic data, missing confounders)

---

## 5. Key Findings (To Be Updated)

> ⚠️ This section will be filled in after the analysis is complete.

Example structure:

- Patients with **adherence above X%** were **Y times more likely** to improve.
- **Sleep quality** and **stress level** showed strong relationships with outcome.
- Certain **therapy types** had noticeably higher improvement rates for specific diagnoses.
- The predictive model achieved **[X]% accuracy** and **[Y]% recall** on the test set.

---

## 6. Impact & Use Cases

This type of analysis can support:

- **Clinicians & Therapists**
  - Identify high-risk patients earlier (e.g., low adherence, high stress, poor sleep)
  - Adjust care plans or outreach frequency based on risk patterns

- **Digital Mental Health Products**
  - Personalize in-app recommendations (e.g., sleep hygiene, stress reduction)
  - Create “risk flags” for care teams based on behavioral trends

- **Program & Policy Teams**
  - Evaluate which modalities or combinations (therapy + medication + duration) yield better outcomes
  - Support data-driven resource allocation

---

## 7. Repository Structure

```text
.
├── data/
│   ├── raw/
│   │   └── mental_health_diagnosis_treatment_.csv
│   └── processed/
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_modeling.ipynb
│   └── 03_reporting.ipynb
├── src/
│   ├── __init__.py
│   ├── data_preparation.py
│   ├── eda_utils.py
│   └── modeling.py
├── reports/
│   ├── figures/
│   └── mental_health_outcomes_report.pdf
├── requirements.txt
└── README.md
