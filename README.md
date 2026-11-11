# Patient No-Show Prediction

## Project Overview

This project predicts whether patients will miss their scheduled medical appointments using machine learning. The analysis uses patient demographics, appointment details, medical conditions and SMS reminder information to identify factors associated with missed appointments.

The project covers data preprocessing, exploratory data analysis (EDA), feature engineering, predictive modelling and model evaluation using Logistic Regression and Random Forest.

The goal is to identify key factors influencing appointment attendance and develop predictive models to support healthcare providers in reducing missed appointments.

## Project Structure

```text
patient_no_show_prediction/
│
├── 01_data/
│   └── [patient appointment dataset]
│
├── 02_notebooks/
│   └── patient_no_show_prediction.ipynb
│
├── 03_plots/
│   └── [generated visualisations]
│
└── README.md
```

### Directory Overview

| Directory / File | Description |
|------------------|-------------|
| `01_data/` | Contains the patient appointment dataset used for analysis and modelling. |
| `02_notebooks/` | Jupyter notebook containing data preprocessing, EDA, feature engineering, model training and evaluation. |
| `03_plots/` | Visualisations generated during exploratory analysis and model evaluation. |
| `README.md` | Project documentation, methodology and results. |

## Dataset

- **Source:** [Medical Appointment No Shows, Kaggle](https://www.kaggle.com/datasets/joniarroba/noshowappointments)
- **Size:** Approximately 110,000 appointments
- **Location:** `01_data/`

### Key Features

| Category | Features |
|----------|----------|
| Patient Demographics | `PatientId`, `Gender`, `Age`, `Neighbourhood` |
| Medical and Social Factors | `Scholarship`, `Hipertension`, `Diabetes`, `Alcoholism`, `Handcap` |
| Appointment Information | `ScheduledDay`, `AppointmentDay`, `WaitingDays`, `SMS_received` |
| Target Variable | `No-show` |

The target variable indicates whether a patient missed their scheduled appointment:

- **1:** Patient did not attend.
- **0:** Patient attended.

## Methodology

### 1. Data Loading and Inspection
- Load the patient appointment dataset using pandas.
- Examine dataset dimensions, feature types and missing values.
- Identify data quality issues before preprocessing.

### 2. Data Cleaning and Preprocessing
- Prepare demographic and medical features for analysis.
- Convert appointment dates into appropriate datetime formats.
- Process categorical variables for machine learning.
- Handle invalid or inconsistent records.

### 3. Feature Engineering
- Calculate `WaitingDays` from appointment scheduling and attendance dates.
- Extract `AppointmentDayOfWeek` from appointment dates.
- Prepare numerical and categorical features for predictive modelling.

### 4. Exploratory Data Analysis (EDA)
- Examine the distribution of appointment attendance.
- Investigate relationships between patient age and no-show rates.
- Analyse the influence of waiting times on attendance.
- Explore associations between SMS reminders and missed appointments.
- Compare attendance patterns across gender, medical conditions and scholarship status.
- Generate correlation heatmaps and feature importance plots.

Visualisations are stored in `03_plots/`.

### 5. Machine Learning Models

Two classification algorithms were trained and evaluated:

- **Logistic Regression:** A baseline classification algorithm used to estimate the probability of patients missing appointments.
- **Random Forest Classifier:** An ensemble learning algorithm that combines multiple decision trees to model complex relationships between patient characteristics and appointment attendance.

### 6. Model Evaluation

Model performance was assessed using:

- ROC-AUC score
- F1-score
- Feature importance analysis

## Results

### Model Performance

| Model | ROC-AUC | F1-score |
|-------|---------|----------|
| Logistic Regression | 0.78 | 0.62 |
| Random Forest | **0.81** | **0.68** |

Random Forest achieved the strongest predictive performance, outperforming Logistic Regression in both ROC-AUC and F1-score.

### Key Predictive Features

The following features were identified as important predictors of missed appointments:

- `WaitingDays`
- `SMS_received`
- `Age`
- `AppointmentDayOfWeek`
- `Scholarship`
- `Diabetes`
- `Hipertension`
- `Handcap`

### Exploratory Data Analysis Findings

- **Age:** Younger patients aged 18–30 showed higher no-show rates compared with older patients aged 60 and above.
- **Waiting Times:** Longer intervals between scheduling and appointment dates were associated with increased no-show rates.
- **SMS Reminders:** Patients receiving SMS reminders showed higher observed no-show rates. This association does not establish that reminders cause missed appointments.
- **Gender:** Gender exhibited a relatively small association with appointment attendance.
- **Medical and Social Factors:** Scholarship status and certain medical conditions showed associations with missed appointments.

### Generated Visualisations

The `03_plots/` directory contains visualisations covering:

- No-show distribution
- Age vs No-show
- Waiting Days vs No-show
- Gender vs No-show
- SMS Received vs No-show
- Feature correlation heatmap
- Top 10 feature importance

## Installation and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/uche1207/patient_no_show_prediction.git
cd patient_no_show_prediction
```

### 2. Install Dependencies

Install the main Python libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3. Run the Notebook

Launch Jupyter Notebook from the repository root:

```bash
jupyter notebook
```

Navigate to:

```text
02_notebooks/patient_no_show_prediction.ipynb
```

Run the notebook cells sequentially to reproduce data preprocessing, exploratory analysis, feature engineering, model training and evaluation.

**Note:** Ensure dataset loading and plot-saving paths match the new directory structure.

## Limitations

- **Class Imbalance:** Missed appointments represent a minority of observations, potentially affecting predictive performance.
- **Observational Data:** Associations between features and missed appointments do not establish causal relationships.
- **Generalisation:** Model performance on the available dataset does not guarantee similar performance across other healthcare systems or patient populations.
- **Further Validation:** Additional evaluation, including precision, recall, calibration and external validation, would strengthen the assessment of model reliability.

This project is intended for educational and research purposes. Model predictions should not be used as the sole basis for healthcare decisions.

## Author

**Uche Dumzo-Ajufo**

MSc Data Science, University of Sheffield

[GitHub](https://github.com/uche1207)