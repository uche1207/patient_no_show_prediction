# Patient No-Show Prediction

## Project Overview
This project predicts whether patients will miss their scheduled medical appointments using machine learning. The dataset includes patient demographics, appointment details, medical conditions, and SMS reminders.

The goal is to identify key factors influencing no-shows and build predictive models that can help healthcare providers improve appointment attendance.

---

## Dataset
- Source: [https://www.kaggle.com/datasets/joniarroba/noshowappointments?resource=download] 
- Size: ~110,000 appointments
- Key features:
  - `PatientId`, `Gender`, `Age`, `Neighbourhood`
  - Medical conditions: `Scholarship`, `Hipertension`, `Diabetes`, `Alcoholism`, `Handcap`
  - Appointment info: `ScheduledDay`, `AppointmentDay`, `WaitingDays`, `SMS_received`
  - Target: `No-show` (Yes=1, No=0)

The dataset is stored in the `no_show_dataset` folder.

---

## Exploratory Data Analysis 
Key observations:
- Younger patients (18-30) are more likely to miss appointments than older patients (60+).  
- Longer waiting times increase no-show risk.  
- Receiving an SMS reminder correlates with higher no-show rates.  
- Gender shows minimal effect.  
- Scholarships and some medical conditions slightly increase no-show rates.

Plots are saved in the `plots` folder, including:
- No-show distribution  
- Age vs No-show  
- Waiting Days vs No-show  
- Gender vs No-show  
- SMS Received vs No-show  
- Feature correlation heatmap  
- Top 10 feature importance

---

## Machine Learning Models
Two models were trained and evaluated:

| Model               | AUC  | F1-score |
|--------------------|------|----------|
| Logistic Regression | 0.78 | 0.62     |
| Random Forest       | 0.81 | 0.68     |

Top predictive features:
- WaitingDays  
- SMS_received  
- Age  
- AppointmentDayOfWeek  
- Scholarship  
- Diabetes  
- Hypertension  
- Handcap  

---

## Usage
1. Clone the repository:
```bash
git clone https://github.com/uche1207/patient_no_show_prediction.git
```
2. Open patient_no_show_prediction.ipynb in Jupyter Notebook.
3. Run all cells to reproduce data cleaning, EDA, model training, and plots.

## Author
**Uche Dumzo-Ajufo**  
MSc Data Science, University of Sheffield
