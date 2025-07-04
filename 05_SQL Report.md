# 🏦 Bank Loan Report – SQL Query Document

This file contains the complete SQL script used to generate a detailed analytical report from the `bank_loan_data` table. It includes business-critical KPIs and deep-dive breakdowns helpful for reporting and dashboarding purposes.
---
# A.	BANK LOAN REPORT | SUMMARY

## KPI’s

## Total Loan Applications:
```
sql
SELECT COUNT(id) AS Total_Applications FROM bank_loan_data

```
![image](https://github.com/user-attachments/assets/7b251654-621a-4b95-a876-e0aed7c265b0)

---

## MTD Loan Applications
```
sql
SELECT COUNT(id) AS Total_Applications FROM bank_loan_data
WHERE MONTH(issue_date) = 12;

```
![image](https://github.com/user-attachments/assets/a68769e6-00b4-4410-bb9b-8a6af333e3c8)

---

## PMTD Loan Applications
```
sql
SELECT COUNT(id) AS Total_Applications FROM bank_loan_data
WHERE MONTH(issue_date) = 11;
```
![image](https://github.com/user-attachments/assets/6a65f361-1af9-48c8-9cef-2bf0d0da6ddf)

---

## Total Funded Amount
```
sql
SELECT SUM(loan_amount) AS Total_Funded_Amount FROM bank_loan_data;
```
![image](https://github.com/user-attachments/assets/ae11b6f0-6e15-40cf-8aca-d74e9109b056)

---

## MTD Total Funded Amount
```
sql
SELECT SUM(loan_amount) AS Total_Funded_Amount FROM bank_loan_data
WHERE MONTH(issue_date) = 12;
```
![image](https://github.com/user-attachments/assets/41b65f9e-3aa7-495e-8243-a9ffd4cdfb39)

---
## PMTD Total Funded Amount
```
sql
SELECT SUM(loan_amount) AS Total_Funded_Amount FROM bank_loan_data
WHERE MONTH(issue_date) = 11
```
![image](https://github.com/user-attachments/assets/598ccb6a-11e7-4b82-9f0d-59072b555b2a)

---
## Total Amount Received
```
sql
SELECT SUM(total_payment) AS Total_Amount_Collected FROM bank_loan_data
```
![image](https://github.com/user-attachments/assets/d1a9caf6-deff-4c0d-b3b3-7a051c4561f2)

---
## MTD Total Amount Received
```
sql
SELECT SUM(total_payment) AS Total_Amount_Collected FROM bank_loan_data
WHERE MONTH(issue_date) = 12
```
![image](https://github.com/user-attachments/assets/fa63500c-28de-46da-8d60-b0c322cc06ba)

---
## PMTD Total Amount Received
```
sql
SELECT SUM(total_payment) AS Total_Amount_Collected FROM bank_loan_data
WHERE MONTH(issue_date) = 11
```
![image](https://github.com/user-attachments/assets/f2e63a15-1a71-4638-bfd3-855407a1fb35)

---
## Average Interest Rate
```
sql
SELECT AVG(int_rate)*100 AS Avg_Int_Rate FROM bank_loan_data
```
![image](https://github.com/user-attachments/assets/ba6e0505-4c2c-4d09-9af0-9085b190c53c)

---
## MTD Average Interest
```
sql
SELECT AVG(int_rate)*100 AS MTD_Avg_Int_Rate FROM bank_loan_data
WHERE MONTH(issue_date) = 12
```
![image](https://github.com/user-attachments/assets/df586063-62ca-4507-bf68-3a47f50871c0)

---
## PMTD Average Interest
```
sql
SELECT AVG(int_rate)*100 AS PMTD_Avg_Int_Rate FROM bank_loan_data
WHERE MONTH(issue_date) = 11
```
![image](https://github.com/user-attachments/assets/4ca62bec-0893-4544-9bd7-92a75c575b48)

---
## Avg DTI
```
sql
SELECT AVG(dti)*100 AS Avg_DTI FROM bank_loan_data
```
![image](https://github.com/user-attachments/assets/9a0e3b2e-b019-45bc-af36-a2307a5f7766)

---
## MTD Avg DTI
```
sql
SELECT AVG(dti)*100 AS MTD_Avg_DTI FROM bank_loan_data
WHERE MONTH(issue_date) = 12
```
![image](https://github.com/user-attachments/assets/24cffbe5-19d4-447b-bf69-fb221013cbbd)

---
## PMTD Avg DTI
```
sql
SELECT AVG(dti)*100 AS PMTD_Avg_DTI FROM bank_loan_data
WHERE MONTH(issue_date) = 11
```
![image](https://github.com/user-attachments/assets/3de98d3d-623e-413d-a8ee-caef2e706b6a)

---


# GOOD LOAN ISSUED


## Good Loan Percentage
```
sql
SELECT
    (COUNT(CASE WHEN loan_status = 'Fully Paid' OR loan_status = 'Current' THEN id END) * 100.0) / 
	COUNT(id) AS Good_Loan_Percentage
FROM bank_loan_data
```
![image](https://github.com/user-attachments/assets/b15bf89f-de8b-4343-b9fb-8e647e69d741)

---
## Good Loan Applications
```
sql
SELECT COUNT(id) AS Good_Loan_Applications FROM bank_loan_data
WHERE loan_status = 'Fully Paid' OR loan_status = 'Current'
```
![image](https://github.com/user-attachments/assets/f41b5736-3b1a-4519-9159-875e2ba0efe0)

---
## Good Loan Funded Amount
```
sql
SELECT SUM(loan_amount) AS Good_Loan_Funded_amount FROM bank_loan_data
WHERE loan_status = 'Fully Paid' OR loan_status = 'Current'
```
![image](https://github.com/user-attachments/assets/69ad4c8c-8754-4f66-8ab9-2fc2225897b0)

---
## Good Loan Amount Received
```
sql
SELECT SUM(total_payment) AS Good_Loan_amount_received FROM bank_loan_data
WHERE loan_status = 'Fully Paid' OR loan_status = 'Current'
```
![image](https://github.com/user-attachments/assets/58be7bdc-cb5e-430c-acc1-a8b50d135d0f)

---

# BAD LOAN ISSUED


## Bad Loan Percentage
```
sql
SELECT
    (COUNT(CASE WHEN loan_status = 'Charged Off' THEN id END) * 100.0) / 
	COUNT(id) AS Bad_Loan_Percentage
FROM bank_loan_data
```
![image](https://github.com/user-attachments/assets/c3b77314-f4d7-4369-991c-52cd14b850d0)

---
## Bad Loan Applications
```
sql
SELECT COUNT(id) AS Bad_Loan_Applications FROM bank_loan_data
WHERE loan_status = 'Charged Off'
```
![image](https://github.com/user-attachments/assets/0e058d75-99cd-4786-99c3-d23a7d689154)

---
## Bad Loan Funded Amount
```
sql
SELECT SUM(loan_amount) AS Bad_Loan_Funded_amount FROM bank_loan_data
WHERE loan_status = 'Charged Off'
```
![image](https://github.com/user-attachments/assets/ec32d188-5099-41bf-9c75-6687de9dd631)

---
## Bad Loan Amount Received
```
sql
SELECT SUM(total_payment) AS Bad_Loan_amount_received FROM bank_loan_data
WHERE loan_status = 'Charged Off'
```
![image](https://github.com/user-attachments/assets/71551f3d-0a9c-441e-80df-1e068d9e8e3a)

---
## LOAN STATUS
```
sql
SELECT
        loan_status,
        COUNT(id) AS LoanCount,
        SUM(total_payment) AS Total_Amount_Received,
        SUM(loan_amount) AS Total_Funded_Amount,
        AVG(int_rate * 100) AS Interest_Rate,
        AVG(dti * 100) AS DTI
    FROM
        bank_loan_data
    GROUP BY
        loan_status
```
![image](https://github.com/user-attachments/assets/ebec7fd8-efdd-45df-880d-0f724ed6dea8)

```
sql
SELECT 
	loan_status, 
	SUM(total_payment) AS MTD_Total_Amount_Received, 
	SUM(loan_amount) AS MTD_Total_Funded_Amount 
FROM bank_loan_data
WHERE MONTH(issue_date) = 12 
GROUP BY loan_status
```
![image](https://github.com/user-attachments/assets/f43b7e0d-a29e-41a4-9be3-29b99aec1d2b)

---

# B.	BANK LOAN REPORT | OVERVIEW

## MONTH
```
sql
SELECT 
	MONTH(issue_date) AS Month_Munber, 
	DATENAME(MONTH, issue_date) AS Month_name, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY MONTH(issue_date), DATENAME(MONTH, issue_date)
ORDER BY MONTH(issue_date)
```
![image](https://github.com/user-attachments/assets/100ddf6c-1639-4454-a89e-48e081756fa7)

---
## EMPLOYEE LENGTH
```
sql
SELECT 
	emp_length AS Employee_Length, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY emp_length
ORDER BY emp_length
```
![image](https://github.com/user-attachments/assets/843fb011-9f8c-446d-8d01-13907bc26f1c)

---
## PURPOSE
```
sql
SELECT 
	purpose AS PURPOSE, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY purpose
ORDER BY purpose
```
![image](https://github.com/user-attachments/assets/3a3b50b6-2ca7-4c6a-b961-e5842ce4b3d3)

---
## HOME OWNERSHIP
```
sql
SELECT 
	home_ownership AS Home_Ownership, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY home_ownership
ORDER BY home_ownership
```
![image](https://github.com/user-attachments/assets/ed196a49-3d17-4c1c-aed8-9ce19e204e8b)

---
## HOME OWNERSHIP
```
sql
SELECT 
	home_ownership AS Home_Ownership, 
	COUNT(id) AS Total_Loan_Applications,
	SUM(loan_amount) AS Total_Funded_Amount,
	SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY home_ownership
ORDER BY home_ownership
```
![image](https://github.com/user-attachments/assets/ed196a49-3d17-4c1c-aed8-9ce19e204e8b)

---

### 🔹 A. Bank Loan Report | Summary

This section provides **key performance indicators (KPIs)** including:

- 📌 **Loan Application Counts**
  - Total Applications
  - Month-To-Date (MTD)
  - Previous Month-To-Date (PMTD)

- 💰 **Funded Amounts**
  - Total Funded Amount
  - MTD and PMTD Funded Amount

- 💸 **Total Payments Received**
  - Total Amount Collected
  - MTD and PMTD Amount Collected

- 📈 **Interest Rate & DTI**
  - Average Interest Rate
  - Average DTI (Debt-to-Income Ratio)
  - MTD & PMTD stats for both

- ✅ **Good Loans**
  - Good Loan Percentage
  - Applications, Funded Amount, and Amount Received for loans marked as *Fully Paid* or *Current*

- ❌ **Bad Loans**
  - Bad Loan Percentage
  - Applications, Funded Amount, and Amount Received for loans marked as *Charged Off*

- 🔄 **Loan Status Summary**
  - Group-wise stats by `loan_status` including interest rate, DTI, funded amount, and payment amount

---

### 🔹 B. Bank Loan Report | Overview

This section contains **breakdown analysis** by different dimensions:

- 📅 **Month-wise Breakdown**
  - Number of loans, funded amount, and amount received by month

- 🗺 **State-wise Breakdown**
  - Grouped by `address_state`

- 🏁 **Term-wise Breakdown**
  - Grouped by `term` (loan duration)

- 👷 **Employee Length Breakdown**
  - Grouped by `emp_length`

- 🎯 **Purpose of Loan**
  - Grouped by `purpose` (e.g., credit card, home improvement)

- 🏠 **Home Ownership**
  - Grouped by `home_ownership` (e.g., RENT, OWN, MORTGAGE)

---
