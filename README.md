# 🏦 Bank Loan Application Dashboard

An advanced and interactive **Power BI dashboard** that delivers deep insights into bank loan applications, loan performance, and borrower behaviors. Combined with robust **SQL queries** for backend validation, this project helps identify trends, monitor KPIs, and make strategic decisions regarding loan issuance and repayment.

---

## 📌 Project Overview

This dashboard visualizes and analyzes bank loan data using a variety of KPIs such as:
- Total loan applications
- Funded & received amounts
- Interest rates & DTI (Debt-to-Income)
- Loan quality (Good vs Bad)
- Loan status performance

It allows interactive filtering and slicing for better understanding of patterns across demographics, time, and financial indicators.

---


## 🛠 Tools & Technologies Used

| Tool             | Purpose                                          |
|------------------|--------------------------------------------------|
| Power BI         | Dashboard creation, visual reports               |
| SQL              | Backend data extraction, testing, and validation |
| DAX              | KPI measures and logic                           |
| Power Query      | Data transformation                              |

---

## 🗂 Dashboard Pages

### 1️⃣ Landing Page – _Navigation & Overview_ ( [View Landing Page](https://github.com/Rohan-pokale/Power-Bi-Project5-Bank_Loan_Analysis_Dashboard/blob/main/Page1-Landing%20Page.PNG) )

**Purpose**: Acts as the starting page, giving users a visual summary of:
- What to expect (MTD, PMTD, MoM trends)
- Breakdown of good vs bad loans
- Navigation icons to Summary, Overview, and Detail pages

🎨 **Dark UI** with high visual clarity and icon-based navigation.

---

### 2️⃣ Summary Page – _Key Metrics & Loan Quality_ ( [View Summary Page](https://github.com/Rohan-pokale/Power-Bi-Project5-Bank_Loan_Analysis_Dashboard/blob/main/Page2-Summary%20Page.PNG) )

**Purpose**: High-level insights on loan volume and financial performance.

#### KPIs:
- Total Loan Applications
- Total Funded Amount
- Total Received Amount
- Average Interest Rate
- Average DTI

#### Breakdown:
- ✅ Good Loans: 86.2%, ~$370M funded
- ❌ Bad Loans: 13.8%, ~$65.5M funded
- 📋 Loan Status: Fully Paid, Charged Off, Current with respective amounts, rates, and DTI

---

### 3️⃣ Overview Page – _Trend and Demographics Analysis_ ( [View Overview Page](https://github.com/Rohan-pokale/Power-Bi-Project5-Bank_Loan_Analysis_Dashboard/blob/main/Page3-Overview%20Page.PNG) )

**Visual Components**:
- 📈 Monthly Trend Line
- 🗺 State-wise Choropleth Map
- 🍩 Loan Term Distribution (36 vs 60 months)
- 📊 Bar Charts:
  - By Employee Length
  - By Loan Purpose
  - By Home Ownership

**Filters**: State, Grade, Purpose, Loan Status, Term

📍 Insights:
- Seasonal trends in loan applications
- Loan risk by purpose and state
- Home ownership & employment length impacts

---

### 4️⃣ Details Page – _Record-Level Insights_ ( [View Details Page](https://github.com/Rohan-pokale/Power-Bi-Project5-Bank_Loan_Analysis_Dashboard/blob/main/Page4-Details%20Page.PNG) )

**Purpose**: Raw data view at individual loan level for auditing or export.

#### Fields:
- Loan ID, Issue Date, Purpose, Home Ownership
- Interest Rate, Installment, Funded/Received Amount
- Grade, DTI

🔍 Use for:
- Subset exports
- Audits
- Customer-specific drilldowns

---

## 🧪 SQL Integration – Backend Validation ( [View SQL Query Document](https://github.com/Rohan-pokale/Power-Bi-Project5-Bank_Loan_Analysis_Dashboard/blob/main/SQL%20Query%20Testing.docx) )

Used SQL extensively to validate dashboard KPIs, segments, and filters.

**SQL was used for:**
- ✅ Data extraction from tables
- ✅ Loan type, status, and amount aggregation
- ✅ Cross-checking Power BI visual values


## ❓ Problem Solved by the Dashboard

> "Loan departments often struggle to track performance, identify risky applicants, and monitor repayment trends—especially when data is spread across thousands of loan applications."

This Power BI Dashboard addresses multiple **business and data analysis challenges** in the banking and loan sector:

---

### 🔧 1. Lack of Centralized Insight into Loan Applications
- ✅ **Solution**: Aggregates all loan-related KPIs into one interactive view.
- 📊 Displays total applications, funded and received amounts, and borrower metrics.

---

### 🔧 2. Difficulty in Identifying Good vs Bad Loans
- ✅ **Solution**: Separates **Good Loans** (Fully Paid, Current) from **Bad Loans** (Charged Off).
- 📉 Enables risk profiling and early identification of default-prone loans.

---

### 🔧 3. No Trend Tracking or Monthly Monitoring
- ✅ **Solution**: Uses MTD, PMTD, and MoM KPIs to show performance trends.
- 📆 Helps analyze seasonal patterns and month-to-month changes in loan activity.

---

### 🔧 4. Poor Visibility into Regional and Demographic Behavior
- ✅ **Solution**: State-wise maps, charts by home ownership, employment length, and purpose.
- 📍 Identifies high-performing or high-risk demographics and regions.

---

### 🔧 5. Limited Ability to Audit or Review Individual Loans
- ✅ **Solution**: Detailed page with full record-level data such as Loan ID, Date, Rate, Amount, etc.
- 🕵️‍♂️ Supports deep dives, filtering, or exporting for external audits.

---

### 🔧 6. Gap Between Raw Data and Dashboard Insights
- ✅ **Solution**: SQL query logic used to validate and verify backend metrics.
- 🔒 Ensures data trust, transparency, and accuracy across KPIs.

---

## 💡 Business Impact

- 🎯 Improves **strategic decision-making** based on real-time insights.
- 🔍 Helps reduce **loan defaults** by identifying risky patterns early.
- 📈 Supports smarter and **data-driven lending** and recovery policies.

> _“With this dashboard, data isn't just numbers — it's actionable intelligence.”_


## 📊 Key Insights
✅ 86% of loans are Good Loans

🔁 Fully Paid loans dominate, indicating good recovery

⚠️ Purposes like Debt Consolidation show higher risk

🕒 Long loan terms and state-level data offer segmentation value


## 👤 About Me

**Rohan Devanand Pokale**  
🎓 B.Tech – Computer Science (Data Science)  
🏫 Vishwakarma Institute of Technology, Pune  
📧 developer.rohan06@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/rohan-pokale-a774b2308)  

> Passionate about data Analysis, visualization, and impactful analytics solutions.

