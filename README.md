# 📊 Credit Card Fraud Detection – Data Analysis Project

## 📌 Overview
This project focuses on analyzing credit card transaction data to identify fraud patterns, detect anomalies, and generate business insights using Python in Jupyter Notebook.

The main objective of this project is to understand:
- how fraud transactions behave,
- when fraud is more likely to occur,
- and how simple rule-based risk segmentation can support fraud monitoring in fintech systems.

---

## 📁 Dataset
- **Source:** Kaggle - Credit Card Fraud Detection Dataset
- **Total Records:** 284,807 transactions
- **Total Features:** 31 columns

### Important Columns
- `Time` → Time elapsed between each transaction and the first transaction in the dataset
- `Amount` → Transaction amount
- `V1` to `V28` → Anonymized features
- `Class` → Target variable
  - `0` = Non-Fraud
  - `1` = Fraud

---

## 🛠️ Tools & Technologies
- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

---

## 🔍 Project Workflow

### 1. Data Understanding
- Loaded dataset using Pandas
- Checked shape, columns, and data types
- Verified missing values
- Reviewed dataset structure

### 2. Data Cleaning
- Confirmed there were no missing values
- Checked and handled duplicates
- Prepared data for analysis

### 3. Fraud Distribution Analysis
- Analyzed the distribution of fraud and non-fraud transactions
- Found that fraud transactions are extremely rare

**Insight:**  
The dataset is highly imbalanced, with only **0.17%** fraudulent transactions.

### 4. Transaction Amount Analysis
- Compared transaction amounts for fraud vs non-fraud cases
- Used descriptive statistics and boxplots

**Insight:**  
Fraud transactions show mixed behavior—many are small, but some high-value outliers increase the average fraud amount.

### 5. Time-Based Analysis
- Converted the `Time` column into hourly buckets
- Analyzed overall transaction activity by hour

**Insight:**  
Most transactions occur during daytime and evening hours, while early morning activity is relatively low.

### 6. Fraud Pattern by Hour
- Analyzed fraud counts across hours of the day
- Identified irregular spikes in fraud activity

**Insight:**  
Fraud transactions are not evenly distributed and show time-based spikes.

### 7. Fraud Rate by Hour
- Calculated hourly fraud rate using:
  
  `Fraud Rate = Fraud Transactions / Total Transactions`

**Insight:**  
Fraud rate is highest during **2 AM to 4 AM**, making these hours high-risk periods.

### 8. Risk Segmentation
Created a simple rule-based risk classification:
- **High Risk (Time):** Transactions between 2 AM and 4 AM
- **High Risk (Amount):** Transactions with amount greater than 200
- **Normal:** All remaining transactions

### 9. Risk vs Fraud Comparison
Compared fraud counts across risk categories.

| Risk Level | Non-Fraud | Fraud | Fraud Rate |
|------------|----------:|------:|-----------:|
| High Risk (Amount) | 28179 | 78 | ~0.27% |
| High Risk (Time) | 8932 | 97 | ~1.08% |
| Normal | 247204 | 317 | ~0.12% |

**Insight:**  
Time-based risk segmentation is more effective than amount-based risk segmentation for identifying fraud-prone transactions.

---

## 📊 Key Insights
- Fraud transactions are extremely rare (**~0.17%**)
- Fraud shows both low-value and high-value patterns
- Peak transaction volume occurs during daytime and evening
- Fraud spikes appear at specific times rather than being evenly distributed
- Fraud rate is highest during **2–4 AM**
- Time-based segmentation performs better than amount-only segmentation

---

## 💡 Business Recommendations
- Increase monitoring during **2 AM to 4 AM**
- Apply stricter review rules for transactions during high-risk hours
- Flag high-value transactions for additional verification
- Combine **time-based** and **amount-based** rules for stronger fraud monitoring
- Introduce time-based risk scoring in fraud detection workflows

---

## 📌 Conclusion
This project demonstrates how exploratory data analysis can uncover meaningful fraud behavior patterns in financial transaction data. The analysis shows that fraud is rare but not random. By identifying high-risk hours and building simple rule-based segmentation, this project provides actionable insights that can support fraud monitoring and decision-making in fintech environments.


## 🚀 Future Improvements
- Build an interactive dashboard using Power BI or Tableau
- Apply machine learning models for fraud prediction
- Create a real-time fraud monitoring pipeline
- Add more advanced anomaly detection techniques

---

## 📂 Project Structure
```bash
Credit-Card-Fraud-Analysis/
│
├── data/
│   └── creditcard.csv
│
├── notebooks/
│   └── fraud_analysis.ipynb
│
├── images/
│   └── charts.png
│
└── README.md
