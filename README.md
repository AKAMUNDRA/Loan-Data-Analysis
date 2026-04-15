# Loan-Data-Analysis
Interactive Power BI dashboard analyzing loan default rates by employment type, age group, and year — with insights on borrower risk and loan distribution patterns.

# 🏦 Loan Default Analytics — Power BI Project

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Records](https://img.shields.io/badge/Records-255%2C347-blue?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-Finance%20%7C%20Credit%20Risk-purple?style=for-the-badge)

> An end-to-end Power BI analytics solution built on 255K+ loan records — covering credit risk, borrower demographics, and financial performance metrics with automated data refresh via Power BI Service.

---

## 📸 Dashboard Preview

### Page 1 — Loan Default And Overview
![Loan Default Overview](https://github.com/AKAMUNDRA/Loan-Data-Analysis/blob/main/Loan%20Default.png)

### Page 2 — Applicant Demographics & Financial Profile
![Applicant Demographics](https://github.com/AKAMUNDRA/Loan-Data-Analysis/blob/main/Applicamt%20Demographic.png)

### Page 3 — Financial Risk Metrics
![Financial Risk Metrics](https://github.com/AKAMUNDRA/Loan-Data-Analysis/blob/main/Financial%20Risk%20Metrics.png)

---

## 🔧 End-to-End Technical Pipeline

```
SQL Server (Source)
      │
      ▼
On-Premises Data Gateway (Standard Mode)
      │  Keeps data secure while enabling cloud access
      ▼
Power BI Dataflow
      │  Centralized transformation layer (Power Query)
      │  Clean · Reusable · Scalable
      ▼
Power BI Desktop
      │  3-Page Interactive Report built with DAX & visuals
      ▼
Power BI Service (Published)
      │  Available anywhere, on any device
      ├──▶ Incremental Refresh (only new/changed rows loaded)
      └──▶ Scheduled Refresh (automated, zero manual intervention)
```

### Why This Architecture?

| Component | Purpose |
|---|---|
| **SQL Server** | Centralized, structured data source |
| **On-Premises Gateway** | Secure bridge between local SQL Server and Power BI cloud |
| **Power BI Dataflow** | Single transformation layer — reusable across multiple reports |
| **Incremental Refresh** | Avoids reprocessing 255K+ rows on every update — faster & smarter |
| **Scheduled Refresh** | Dashboard always live with zero manual intervention |

---

## 📊 Dashboard Pages

### Page 1 — Loan Default And Overview
High-level overview of loan distribution and default patterns.

| Visual | Insight |
|---|---|
| Loan Amount by Purpose | Home loans lead at 6,545M, followed closely by Business & Education |
| Average Income by Employment Type | Full-time earners average 82,890 vs 82,272 for Unemployed |
| Default Rate by Employment Type | Unemployed (3.39%) default nearly 44% more than Full-time (2.36%) |
| Average Loan Amount by Age Group | Adults hold the highest average at 127,901 |
| Default Rate by Year | Peaked at 11.75% in 2016, recovered to 11.60% by 2018 |

### Page 2 — Applicant Demographics & Financial Profile
Deep dive into borrower profiles across credit score, education, age, and marital status.

| Visual | Insight |
|---|---|
| Median Loan by Credit Score | Low credit score borrowers have slightly higher median loans (128,397) |
| Total Loan by Credit Bins | Medium credit score segment holds the highest total volume (4.6bn) |
| Loan by Mortgage & Dependents (Middle Age) | Dependents vs no dependents shows near-equal loan split (3.1bn each) |
| Average Loan by Age Group & Marital Status | Adults (Single 128.57K) hold the highest average amounts |
| Loan by Education | Near-equal distribution — Bachelor's, High School, Master's, PhD (~25% each) |

### Page 3 — Financial Risk Metrics
Tracks YoY changes in loan volume, defaults, and risk by income and credit segment.

| Visual | Insight |
|---|---|
| YoY Loan Amount Change | Surged to +1.73x in 2018 after a -1.08x dip in 2017 |
| YoY Default Loans Change | Highest growth in 2015 (+0.027), biggest drop in 2017 (-0.028) |
| YTD Loan by Credit Score & Marital Status | Medium & High credit segments dominate (~0.67bn each) |
| Loan by Income Bracket | High Income borrowers hold 21.732bn of total 32.577bn |
| Loan by Employment Type | Full-time (5.444bn), Part-time (5.438bn), Self-employed (5.428bn) — nearly equal |

---

## 🗂️ Dataset Information

| Field | Details |
|---|---|
| **File Name** | `Loan_default.csv` |
| **Total Records** | 255,347 rows |
| **Total Columns** | 19 columns |
| **Time Period** | 2013 – 2018 |
| **Domain** | Banking / Finance / Credit Risk |

### 📋 Column Descriptions

| Column | Data Type | Description |
|---|---|---|
| `LoanID` | String | Unique identifier for each loan |
| `Age` | Integer | Age of the borrower |
| `Income` | Float | Annual income of the borrower |
| `LoanAmount` | Float | Total sanctioned loan amount |
| `CreditScore` | Integer | Borrower's credit score |
| `MonthsEmployed` | Integer | Duration of current employment in months |
| `NumCreditLines` | Integer | Number of active credit lines |
| `InterestRate` | Float | Annual interest rate on the loan (%) |
| `LoanTerm` | Integer | Loan repayment duration (months) |
| `DTIRatio` | Float | Debt-to-Income ratio |
| `Education` | String | Education level (High School / Bachelor's / Master's / PhD) |
| `EmploymentType` | String | Employment status (Full-time / Part-time / Self-employed / Unemployed) |
| `MaritalStatus` | String | Marital status (Single / Married / Divorced) |
| `HasMortgage` | Boolean | Whether borrower has an active mortgage (Yes/No) |
| `HasDependents` | Boolean | Whether borrower has dependents (Yes/No) |
| `LoanPurpose` | String | Loan purpose (Home / Business / Education / Auto / Other) |
| `HasCoSigner` | Boolean | Whether a co-signer is present (Yes/No) |
| `Default` | Integer | Default status — 1 = Defaulted, 0 = Not Defaulted |
| `Loan Date` | Date | Date of loan issuance (DD/MM/YYYY) |

---

## 🔍 Key Insights

- 📌 **Default rates peaked at 11.75% in 2016** — likely linked to macroeconomic conditions of the time
- 📌 **Unemployed borrowers default at 3.39%** vs 2.36% for Full-time — nearly 44% higher risk
- 📌 **Home loans lead all categories** at 6,545M in total disbursed amount
- 📌 **High Income borrowers account for 66.7% of total loans** — 21.7bn out of 32.6bn
- 📌 **Education level does NOT skew credit access** — all four education levels hold ~25% each
- 📌 **2018 saw the strongest YoY loan growth at +1.73x** — indicating strong market recovery
- 📌 **Medium credit score borrowers take the most total loans** (4.6bn), not high-score borrowers

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| **SQL Server** | Data source and storage |
| **On-Premises Data Gateway** | Secure cloud connection for SQL Server |
| **Power BI Dataflow** | Centralized data transformation layer |
| **Power BI Desktop** | Report and dashboard development |
| **Power Query (M Language)** | Data shaping and feature engineering |
| **DAX** | Measures — YoY Growth, YTD, Default Rate %, Credit Score Bins |
| **Power BI Service** | Publishing, access management, and automation |

---

## 📁 Repository Structure

```
📦 loan-default-analytics
 ┣ 📂 dataset
 ┃ ┗ 📄 Loan_default.csv                  # Raw dataset (255K records, 19 columns)
 ┣ 📂 dashboard
 ┃ ┗ 📄 Loan_Default_Analytics.pbix        # Power BI report file
 ┣ 📂 screenshots
 ┃ ┣ 🖼️ Loan_Default.png                  # Page 1 — Loan Default & Overview
 ┃ ┣ 🖼️ Loan_D.png                        # Page 2 — Demographics & Financial Profile
 ┃ ┗ 🖼️ L1.png                            # Page 3 — Financial Risk Metrics
 ┗ 📄 README.md
```

---

## 🚀 How to Use

### Option 1 — Explore the Dataset
```bash
https://github.com/AKAMUNDRA/Loan-Data-Analysis/blob/main/Loan_default.zip
```

### Option 2 — Open in Power BI Desktop
1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
2. Open ``
3. Explore all 3 interactive report pages

### Option 3 — Replicate the Full Pipeline
1. Load `Loan_default.csv` into **SQL Server**
2. Install and configure an **On-Premises Data Gateway** (Standard Mode)
3. Create a **Power BI Dataflow** in Power BI Service connected to your SQL source
4. Connect **Power BI Desktop** to the dataflow and build your report
5. **Publish** to Power BI Service
6. Set up **Incremental Refresh** policies (RangeStart / RangeEnd parameters)
7. Configure a **Scheduled Refresh** in dataset settings

---

## 💡 Use Cases

- 🏦 **Banks & NBFCs** — Understand credit risk and borrower behavior
- 📊 **Data Analysts** — Practice building an end-to-end Power BI solution
- 🎓 **Students** — Learn DAX, Dataflows, Gateway, and incremental refresh
- 🔬 **Researchers** — Analyze default patterns across socio-economic segments

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repository
2. Create your branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 👤 Author

**Your Name**
- 🔗 LinkedIn: [your-linkedin](https://linkedin.com/in/your-profile)
- 🐙 GitHub: [@your-username](https://github.com/your-username)

---

⭐ **If this project helped you, please consider giving it a star!** ⭐

