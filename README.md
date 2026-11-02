# 🏥 Healthcare Data Analytics Case Study

> **From 55,500 raw hospital records to clear answers for hospital leadership.**

![Python](https://img.shields.io/badge/Python-pandas%20%7C%20NumPy%20%7C%20Matplotlib-3776AB)
![Records](https://img.shields.io/badge/Records-54%2C966-0e9aa7)
![Period](https://img.shields.io/badge/Period-May%202019%20to%20May%202024-0b2540)
![Output](https://img.shields.io/badge/Output-Executive%20Dashboard-success)

---

## 🎯 About the Project
This project analyses hospital admission records to answer **5 business questions** and **3 ad-hoc management questions**. The results are also presented in an interactive executive dashboard.

---

## 📊 Project at a Glance

| 🏷️ Metric | 📈 Value |
|---|---|
| Admission records (after cleaning) | **54,966** |
| Period covered | **May 2019 to May 2024 (61 months)** |
| Medical conditions | **6** |
| Insurance providers | **5** |
| Average patient age | **51.54 years** |
| Average billing per admission | **25,594.54** |
| Emergency admissions | **18,102 (32.9%)** |

---

## 🗂️ Project Structure
```
healthcare/
├── 📓 healthcare.ipynb                      analysis notebook
├── 📄 healthcare_dataset.csv                source data
├── 📊 healthcare_executive_dashboard.html   executive dashboard
└── 📘 README.md                             project guide
```

---

## 🧬 About the Data
- **Raw data:** 55,500 rows × 15 columns
- **Cleaned data:** 54,966 rows × 16 columns
- **One row = one admission record**, not a verified unique patient

| Group | Columns |
|---|---|
| 👤 Patient | Name, Age, Gender, Blood Type |
| 🩺 Clinical | Medical Condition, Medication, Test Results |
| 🏨 Hospital | Hospital, Doctor, Room Number, Admission Type |
| 📅 Dates | Date of Admission, Discharge Date, **Length_of_stay** *(added)* |
| 💰 Billing | Insurance Provider, Billing Amount |

---

## 🧹 Data Cleaning Journey
```
55,500 rows
   │  ✅ Checked missing values      → none found
   │  🗑️ Removed duplicate rows      → 534 removed
   ▼
54,966 rows
   │  ✏️ Standardised names          → trimmed, title case
   │  💲 Fixed negative billing      → replaced with the mean
   │  📅 Converted dates             → added Length_of_stay
   ▼
✨ Clean dataset ready for analysis
```

---

## ❓ Five Business Questions

### 1️⃣ Which medical condition affects the most patients? 🏆 Arthritis
```
Arthritis      ████████████████▊  9,218  (16.8%)
Diabetes       ████████████████▊  9,216  (16.8%)
Hypertension   ████████████████▌  9,151  (16.6%)
Obesity        ████████████████▌  9,146  (16.6%)
Cancer         ████████████████▌  9,140  (16.6%)
Asthma         ████████████████▍  9,095  (16.5%)
```
💡 All six conditions are within about 1.3% of each other, so demand is spread evenly.

### 2️⃣ How is patient age distributed? 🎂 Average age: 51.54 years
Ages range from **13 to 89**.

### 3️⃣ How has average treatment cost changed over time? 💰 Overall average: 25,594.54
Monthly averages were calculated for all 61 months. They run from **25,897.45 (May 2019)** to **25,464.90 (May 2024)**, with no sustained rise or fall in the months shown.

### 4️⃣ Is there a relationship between age and cost? 👴 Patients aged 60+: 25,563.59
This is almost identical to the overall average of 25,594.54, so there is no meaningful gap in averages.

### 5️⃣ Which insurance provider covers the most patients? 🏆 Cigna
```
Cigna              ████████████████████  11,139  (20.3%)
Medicare           ███████████████████▊  11,039  (20.1%)
UnitedHealthcare   ███████████████████▊  11,014  (20.0%)
Blue Cross         ███████████████████▋  10,952  (19.9%)
Aetna              ███████████████████▍  10,822  (19.7%)
```
💡 The insurer mix is balanced, so no single provider dominates.

---

## 🚨 Three Ad-Hoc Management Questions

### 🚑 1. Emergency Department Capacity Planning
How many emergency admissions occurred each month (all years combined)?
```
Jan  ███████████████████  1,547
Feb  ██████████████████   1,452   ⬇️ lowest
Mar  ███████████████████  1,528
Apr  ██████████████████   1,473
May  ███████████████████  1,533
Jun  ██████████████████   1,483
Jul  ████████████████████ 1,573   ⬆️ peak
Aug  ███████████████████  1,533
Sep  ███████████████████  1,500
Oct  ███████████████████  1,490
Nov  ██████████████████   1,462
Dec  ███████████████████  1,528
     (1 block is about 80 admissions)
```
**Total: 18,102 emergency admissions.**

### 💸 2. High-Cost Patient Groups
**5,497** admissions have billing above the 90th percentile, about 10% of all records. These are flagged for finance review.

### 🧪 3. Emergency Cases with Abnormal Results
**6,038** emergency admissions have abnormal test results. That is about one third of all emergency admissions, so they are the first to prioritise for clinical review.

---

## 🔑 Key Findings
- ⚖️ Patient volume is spread almost evenly across all six conditions and all five insurers.
- 📉 Average billing is stable over time and does not differ meaningfully for patients aged 60+.
- 🚑 About 1 in 3 admissions (32.9%) is an emergency, with a mild peak in July.
- 🔍 About 1 in 3 emergency admissions has an abnormal test result.

---

## ▶️ How to Run
1. 📥 Put `healthcare_dataset.csv` next to the notebook and update the file path in the loading cell.
2. 🛠️ Install the tools:
   ```bash
   pip install numpy pandas matplotlib jupyter
   ```
3. 📓 Open `healthcare.ipynb` in Jupyter and run all cells in order.
4. 📊 Open `healthcare_executive_dashboard.html` in any browser to see the dashboard.

---

## ⚠️ Limitations
- 💱 The currency is not specified.
- 💵 Billing amounts are billed amounts, not confirmed revenue or payments received.
- 👥 Counts are admission records, not unique patients.
- 🔗 The findings are descriptive and do not show causes.
- 🏢 The dataset has no department column, so there is no department-level analysis.

---

## 🧰 Tools Used
**Python** · **pandas** · **NumPy** · **Matplotlib** · **HTML / CSS / JavaScript** (dashboard)

---

<p align="center">Made with 📊 data and ☕ curiosity</p>
