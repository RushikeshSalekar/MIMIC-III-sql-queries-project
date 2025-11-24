# MIMIC-III-sql-queries-project
Collection of SQL questions and solutions using the MIMIC-III clinical database.
🏥 MIMIC-III Clinical Data Analysis Using Microsoft SQL Server

SQL Healthcare Analytics Project – ICU Patient Insights

This project uses Microsoft SQL Server (MSSQL) to analyze the MIMIC-III clinical database, focusing on ICU patient demographics, diagnosis trends, vital signs, medications, mortality analysis, and readmission patterns.

📌 Project Objective

To extract meaningful healthcare insights from ICU patient data using SQL queries in MS SQL Server. The dataset mimics real-world clinical scenarios and helps build skills in:

✔ Medical Data Analytics
✔ Clinical Query Optimization
✔ Healthcare Reporting
✔ Decision Support Systems

🧠 About the MIMIC-III Dataset

The MIMIC-III ("Medical Information Mart for Intensive Care") dataset is a publicly available, de-identified clinical database consisting of over 61,000 ICU admissions collected between 2001–2012. It includes:

* Patient demographics
* Vital signs
* Lab tests
* Diagnoses (ICD-9 codes)
* Medications & procedures
* ICU stay details

🛠️ Technology Stack

| Component                          | Description                     |
| ---------------------------------- | ------------------------------- |
| Microsoft SQL Server               | Main database & query execution |
| MSSQL Management Studio (SSMS)     | SQL execution & debugging       |
| PhysioNet MIMIC-III Dataset        | Source data                     |
| T-SQL                              | Query language used             |

📂 Folder Structure

mimic-iii-sql-mssql-project/
│
├── queries/                     # All SQL scripts
│     ├── q01_patient_demographics.sql
│     ├── q02_unique_icu_patients.sql
│     ├── ...
│     └── q23_readmission_30_days.sql
│
├── questions.md                 # List of problems asked
├── README.md                   # Project documentation (this file)
└── notes.txt (optional)

🧾 SQL Questions Covered (Using MSSQL Syntax)

From the uploaded SQL project: 
✔ Patient demographics & first ICU admission age
✔ Count of unique ICU patients
✔ Sepsis-related admissions (ICD-9: 99591)
✔ Cardiovascular disease queries
✔ Top 5 diagnoses in ICU
✔ Avg. heart rate for age > 60
✔ First recorded blood pressure
✔ Oxygen saturation below 90%
✔ Medications for pneumonia (486)
✔ Antibiotics detection using `LIKE`
✔ ICU readmission within 48 hours
✔ In-hospital mortality rate for sepsis
✔ ICU mortality analysis
✔ Readmission within 30 days (with `DATEDIFF`)

🖥️ How to Run This Project in **Microsoft SQL Server**

✅ Step 1: Install Required Tools

| Software          | Purpose             |
| ----------------- | ------------------- |
| MS SQL Server     | Database engine     |
| SSMS              | SQL Query Execution |
| MIMIC-III Dataset | Import tables       |

📥 Step 2: Import Tables into SQL Server

Import all CSV files using:
SSMS → Database → Import Flat File → Browse → Finish

Make sure tables match your SQL queries:

* PATIENTS
* ADMISSIONS
* ICUSTAYS
* DIAGNOSES_ICD
* CHARTEVENTS
* LABEVENTS
* PRESCRIPTIONS
* D_ICD_DIAGNOSES
* D_ITEMS

🧪 Step 3: Run SQL Queries (`queries/` folder)

Example:

sql
-- Find Sepsis-related admissions (99591)
SELECT a.hadm_id, a.admittime, d.icd9_code
FROM ADMISSIONS a
JOIN DIAGNOSES_ICD d ON a.hadm_id = d.hadm_id
WHERE d.icd9_code = '99591';

📈 Future Enhancements

🔹 Build a Power BI Dashboard
🔹 Create Stored Procedures & Views
🔹 Use Python (PyODBC) for automation
🔹 Apply Machine Learning to predict ICU mortality

📬 Contact
👤 Rushikesh Salekar
📧 salekarrushikesh05@gmail.com

If you like this project, please ⭐star the repository—
it helps showcase SQL skills to recruiters! 🚀
