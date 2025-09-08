# AI-Automated Fraud Finance Monitoring using n8n and Gemini
![Fraud detection Dashboard](https://github.com/user-attachments/assets/7570ff5b-c30e-4bc2-b361-32f79beb382f)


## 📌 Table of Contents  
- [Overview](##📖 Overview) 
- [Business Problem](##🏦 Business Problem)   
- [Dataset](##📂 Dataset)  
- [Tools & Technologies](##🛠️ Tools & Technologies)  
- [Project Structure](##📁 Project Structure) 
- [Data Cleaning & Preparation](##🧹 Data Cleaning & Preparation ) 
- [Exploratory Data Analysis (EDA)](##🧹 Data Cleaning & Preparation)  
- [Research Questions & Key Findings](##❓ Research Questions & Key Findings)  
- [Dashboard](## 📊 Dashboard)
- [How to Run This Project](## ⚙️ How to Run This Project) 
- [Final Recommendations](## Final Recommendations)
- [Author & Contact](##👤 Author & Contact)

---

## 📖 Overview  
This project builds an **automated fraud finance monitoring system** for a mid-sized financial institution.  
The system integrates **n8n (workflow automation)**, **Supabase (database)**, **Quadratic**, **Google Sheets**, and **Looker Studio** to monitor customer activity, loans, and transactions in real time.  

The goal is to detect **suspicious behavior, default risk, and fraud patterns** early, while also improving business insights into customer and loan performance.  

---

## 🏦 Business Problem  
Financial institutions face increasing risks of:  
- Rising defaults from high-risk borrowers  
- Fraudulent loan applications and suspicious payment reversals  
- Inefficient loan portfolio management  

This project addresses these issues by:  
1. **Monitoring transactions in real-time** to detect red flags.  
2. **Identifying risky customers** with declining creditworthiness.  
3. **Improving decision-making** on loan products and underwriting.  

---

## 📂 Dataset  
- **Customers** → Demographics, credit score, annual income, region, acquisition date  
- **Loans** → Loan amount, term, purpose, interest rate, repayment status  
- **Transactions** → Payment history, payment delays, chargebacks, reversals  

Data is stored in **Supabase** and connected to **Looker Studio** dashboards.  
Sample CSVs are included in `/data/`.  

---

## 🛠️ Tools & Technologies  
- **n8n** → Automation & ETL pipelines  
- **Supabase** → PostgreSQL backend for customer, loan & transaction data  
- **Quadratic** → Spreadsheet-based data modeling  
- **Google Sheets** → Lightweight integration for real-time sync  
- **Looker Studio** → Dashboards, reporting & AI-generated summaries  
- **Python (optional)** → Data analysis, anomaly detection, and EDA  

---

## 📁 Project Structure  
fraud-finance-monitoring/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── n8n_flows/ # JSON exports of automation workflows
│
├── sql/ # Database schema or queries for Supabase
│ └── schema.sql
│
├── data/ # Sample CSVs
│ ├── customers.csv
│ ├── loans.csv
│ └── transactions.csv
│
├── notebooks/ # Jupyter notebooks for EDA
│ ├── exploratory_analysis.ipynb
│ └── fraud_detection.ipynb
│
├── dashboard/ # Looker Studio dashboard screenshots or links
│ └── fraud_dashboard.png


---

## 🧹 Data Cleaning & Preparation  
- Removed **negative or zero values** (income ≤ 0, loan amount ≤ 0).  
- Handled **outliers** in high-income/low-credit-score clusters.  
- Flagged **single-day sign-up spikes** (possible fraud).  
- Standardized column formats (dates, currencies, IDs).  

---

## 🔎 Exploratory Data Analysis (EDA)  
- **Demographics:** Majority of borrowers are 30–45 yrs; fastest growth in Pacific Northwest.  
- **Loans:** Default rate increased to 5.2% (from 3.5% earlier). 60-month terms = highest risk.  
- **Transactions:** Late payments up by 18%, average delay = 12 days. Payment reversals trending upward.  
- **Fraud Signals:** Nevada cohort showed suspicious sign-ups + payment chargebacks.  

---

## ❓ Research Questions & Key Findings  
1. **Which loan types are most profitable vs. risky?**  
   → Home Improvement loans = safest (1.8% default). Debt Consolidation = riskiest.  

2. **Are new customer cohorts riskier?**  
   → Yes. New borrowers’ credit scores dropped from 710 → 685.  

3. **Can fraud be linked to customer acquisition anomalies?**  
   → Yes. Nevada spike linked with chargebacks → possible fraud ring.  

4. **What behavioral patterns indicate distress?**  
   → Customers making multiple small payments instead of scheduled ones = high-risk indicator.  

---

## 📊 Dashboard  
Looker Studio Dashboard tracks:  
- **Customer Profiles** (demographics, credit score trends, geography)  
- **Loan Performance** (defaults, terms, profitability by type)  
- **Transaction Monitoring** (late payments, reversals, fraud signals)  
- **AI-Generated Insights** (Gemini AI summaries integrated in dashboard bottom section)  

---

## ⚙️ How to Run This Project  

### 1. Clone the repository  
git clone https://github.com/yourusername/fraud-finance-monitoring.git
cd fraud-finance-monitoring

2. (Optional) Install Python dependencies
pip install -r requirements.txt

3. Setup Supabase

Import /sql/schema.sql into your Supabase project.

Upload /data/*.csv as seed data.

4. Import n8n workflows

Import flows from /n8n_flows/ to automate data sync (Supabase ↔ Sheets).

5. Open Dashboard

Connect Looker Studio to Supabase/Sheets.

Import dashboard template from /dashboard/.

## Final Recommendations

Tighten underwriting criteria for borrowers <690 credit score & long-term loans.

Investigate fraud patterns (Nevada cohort, payment reversals).

Proactive customer retention: Offer deferrals/modifications to distressed customers.

Optimize loan marketing: Promote Home Improvement loans; review Business loan exposure.

System audit: Fix anomalies in loan pricing (e.g., abnormally low interest rates).

##👤 Author & Contact

Sandra Raj P
Data Analyst | Fraud Risk Monitoring Enthusiast

📧 Email: sandraraj36@gmail.com

🔗 LinkedIn: www.linkedin.com/in/sandrarajp


## 📁 Project Structure  
