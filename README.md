# 🏦 Banking Analytics & Power BI Dashboard

A complete **Banking Analytics project** built using **Snowflake SQL and Microsoft Power BI**.  
The project models core banking operations such as customers, accounts, transactions, loans, loan payments, cards, branches, and employees, and converts the data into interactive business dashboards.

---

## 📌 Project Overview

This project demonstrates an end-to-end data analytics workflow:

**Snowflake Database → SQL Data Modeling → Data Analysis → Power BI → Interactive Banking Dashboard**

The SQL script creates a `BANK_DB` database with a `PUBLIC` schema and builds 10 related banking tables. The Power BI report contains an **Executive Dashboard**, **Customer Analytics**, **Loan & Card Analytics**, filters, KPI cards, charts, and a drill-through page.

---

## 🎯 Project Objectives

- Build a realistic banking database using SQL.
- Store and manage customer, account, transaction, loan, card, branch, and employee information.
- Analyze banking transactions and financial activity.
- Analyze customer demographics and locations.
- Monitor loan portfolio and outstanding loan amounts.
- Analyze loan payment performance.
- Analyze card types, networks, and status.
- Create an interactive Power BI dashboard for business decision-making.
- Practice SQL, data modeling, Power BI visuals, filters, and dashboard navigation.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| **Snowflake** | Cloud database and SQL data storage |
| **SQL** | Database creation, table design, relationships, and data analysis |
| **Microsoft Power BI** | Interactive dashboards and visualization |
| **DAX** | Measures and analytical calculations |
| **Power BI Drill-through** | Detailed record-level analysis |
| **Power BI Filters/Slicers** | Interactive dashboard filtering |

---

## 🗄️ Database Structure

The project contains the following 10 tables:

### 1. Customers
Stores customer information such as:

- Customer ID
- Name
- Date of Birth
- Gender
- Phone
- Email
- City
- State
- Occupation
- Customer Since
- Customer Status

### 2. Branches
Stores bank branch information:

- Branch ID
- Branch Name
- City
- State
- Branch Manager
- Opening Date

### 3. Account Types
Stores account categories and financial rules:

- Savings
- Current
- Salary
- Fixed Deposit
- Recurring Deposit
- Minimum Balance
- Interest Rate

### 4. Accounts
Stores customer account information:

- Account ID
- Customer ID
- Branch ID
- Account Type
- Account Number
- Opening Date
- Balance
- Account Status

### 5. Transaction Types
Defines transaction categories such as:

- Cash Deposit
- Cash Withdrawal
- Fund Transfer
- UPI Payment
- Salary Credit
- Bill Payment
- Interest Credit
- Loan EMI Debit

### 6. Transactions
Stores banking transaction activity:

- Transaction ID
- Account ID
- Transaction Type
- Transaction Date
- Amount
- Transaction Mode
- Merchant
- Reference Number
- Transaction Status
- Balance After Transaction

### 7. Loans
Stores loan portfolio information:

- Loan ID
- Customer ID
- Branch ID
- Loan Type
- Loan Amount
- Interest Rate
- Tenure
- Start Date
- End Date
- Loan Status
- Outstanding Amount

### 8. Loan Payments
Stores loan repayment information:

- Payment ID
- Loan ID
- Payment Date
- Payment Amount
- Principal Amount
- Interest Amount
- Payment Status

### 9. Cards
Stores debit and credit card information:

- Card ID
- Customer ID
- Account ID
- Card Type
- Card Network
- Issue Date
- Expiry Date
- Credit Limit
- Card Status

### 10. Employees
Stores employee information:

- Employee ID
- Branch ID
- Employee Name
- Job Title
- Hire Date
- Salary
- Employee Status

---

## 📊 Power BI Dashboard

The Power BI report is organized into an **Executive Dashboard** and a **Drill Through** page.

### 🏠 Executive Dashboard

The main dashboard provides a high-level view of banking performance.

#### KPI Cards

- Total Transactions
- Total Customers
- Total Accounts
- Transaction Amount
- Total Loans

#### Transaction Analytics

- Transaction Trend
- Transactions by Type
- Top 10 Merchants by Transaction Amount
- Branch Performance

#### Account & Customer Analytics

- Account Balance by Type
- Customer Distribution by City
- Customers by Gender
- Top 5 Occupations
- Customers by Age Group
- Customer Status
- Maximum Value by Occupation
- Customer Location

#### Loan & Card Analytics

- Loan Portfolio
- Loan Payment Status
- Card Network
- Loan Status
- Loan Type
- Outstanding Amount by Loan Type
- Total Cards
- Active Loans
- Total Payment Amount
- Card Type Percentage
- Cards by Card Status
- Total Cards by Card Network
- Payment Count by Loan Type and Payment Status
- Payment Amount & Loan Amount
- Total Loan by Year and Loan Status

---

## 🔎 Customer Analytics

The customer analysis section focuses on customer behavior and demographics.

### Key KPIs

- Total Customers
- Active Customers
- Inactive Customers
- Average Balance

### Visualizations

- Customers by Gender
- Top 5 Occupations
- Customers by City
- Age Group Analysis
- Customer Status
- Maximum by Occupation
- Customer Location

These visuals help identify customer segments, geographic distribution, occupation patterns, and customer activity.

---

## 💳 Loan & Card Analytics

The loan and card analysis section provides detailed financial insights.

### Loan KPIs

- Total Loans
- Total Loan Amount
- Outstanding Loan Amount
- Active Loans
- Total Payment Amount

### Card KPI

- Total Cards

### Visualizations

- Payment Amount & Loan Amount
- Card Type Percentage
- Cards by Card Status
- Total Loan by Year and Loan Status
- Total Cards by Card Network
- Loan by Status
- Total Loan by Loan Type
- Payment Count by Loan Type & Payment Status
- Outstanding Amount by Loan Type

---

## 🎛️ Interactive Features

The dashboard includes:

- Slicers
- Filters
- KPI cards
- Interactive charts
- Dashboard navigation buttons
- Customer analytics navigation
- Loan & card analytics navigation
- Drill-through functionality
- Interactive cross-filtering

The report also includes a dedicated **Drill Through** page for detailed analysis.

---

## 🏗️ Data Model

The database follows a relational structure with primary and foreign key relationships.

### Main relationships

```text
Customers
   │
   ├── Accounts
   │      ├── Transactions
   │      └── Cards
   │
   └── Loans
          └── Loan Payments

Branches
   ├── Accounts
   ├── Loans
   └── Employees

Account Types
   └── Accounts

Transaction Types
   └── Transactions
```

This structure allows banking data to be analyzed across customers, branches, accounts, transactions, loans, payments, and cards.

---

## 🚀 How to Run the SQL Project

### Step 1 — Open Snowflake

Log in to your Snowflake account and open a SQL Worksheet.

### Step 2 — Open `bank.sql`

Upload or copy the `bank.sql` script into the Snowflake worksheet.

### Step 3 — Select the Required Warehouse

The script uses:

```sql
USE WAREHOUSE COMPUTE_WH;
```

If your warehouse has a different name, replace `COMPUTE_WH` with your warehouse name.

### Step 4 — Run the Complete Script

Run the complete script using **Run All**.

The script creates:

```text
BANK_DB
└── PUBLIC
    ├── customers
    ├── branches
    ├── account_types
    ├── accounts
    ├── transaction_types
    ├── transactions
    ├── loans
    ├── loan_payments
    ├── cards
    └── employees
```

### Step 5 — Verify the Data

The SQL script includes a row-count verification query for all 10 tables.

---

## 📈 Power BI Setup

1. Open `BANK_REPORT.pbix` using Power BI Desktop.
2. Configure the required Snowflake connection if prompted.
3. Refresh the data.
4. Verify the data model and relationships.
5. Check the KPI cards and visualizations.
6. Use the slicers and filters to interact with the dashboard.
7. Test the drill-through page from the relevant visual.

> **Note:** The `.pbix` file is a Power BI Desktop file. GitHub can store the file, but it does not render the interactive Power BI report directly in the repository page.

---

## 📁 Project Files

```text
Banking-Analytics/
│
├── bank.sql
├── BANK_REPORT.pbix
└── README.md
```

### `bank.sql`

Contains:

- Snowflake database setup
- Schema setup
- Table creation
- Primary keys
- Foreign keys
- Banking sample data
- Data verification query

### `BANK_REPORT.pbix`

Contains the Power BI dashboard and interactive analytics report.

---

## 💡 Business Questions Answered

This project can be used to answer questions such as:

- How many customers are active?
- How many accounts exist?
- What is the total transaction amount?
- Which transaction types are most common?
- Which merchants have the highest transaction amounts?
- Which branches perform best?
- Which account type has the highest balance?
- Which cities have the most customers?
- What are the major customer occupation groups?
- What is the age-group distribution of customers?
- How large is the total loan portfolio?
- How much loan amount is outstanding?
- Which loan types have the highest outstanding amount?
- What is the loan payment status distribution?
- Which card networks are most commonly used?
- What is the distribution of debit and credit cards?
- How does loan activity change over time?

---

## 🔐 Data Note

The SQL file contains generated/sample banking data for analytics and demonstration purposes.

**Do not use real customer personal, financial, card, or banking information in a public GitHub repository.**

If publishing this project publicly, review the dataset and remove any sensitive or personally identifiable information before making the repository public.

---

## 🎓 Skills Demonstrated

### SQL

- Database creation
- Schema creation
- Table creation
- Primary keys
- Foreign keys
- Relational data modeling
- Data insertion
- Data validation
- Aggregation
- Joins
- Analytical queries

### Power BI

- Data connection
- Data modeling
- DAX measures
- KPI cards
- Slicers
- Filters
- Bar charts
- Column charts
- Line charts
- Donut charts
- Treemaps
- Combo charts
- Tables
- Drill-through
- Dashboard navigation

### Data Analytics

- Customer segmentation
- Transaction analysis
- Branch performance
- Loan portfolio analysis
- Payment analysis
- Card analysis
- Geographic analysis
- Trend analysis

---

## 🏆 Project Highlights

- End-to-end banking analytics solution
- Snowflake-based relational database
- 10 connected banking tables
- Large sample dataset
- Interactive Power BI dashboard
- Customer analytics
- Loan and card analytics
- KPI-driven reporting
- Drill-through analysis
- Business-focused visualizations

---

## 👨‍💻 Author

**Pranesh S**

Software Developer | MERN Stack Developer | Data Analyst

**Skills:** SQL | Snowflake | Power BI | DAX | Data Analytics | Python | MERN Stack

---

## ⭐ If You Like This Project

If this project helps you understand banking analytics, SQL, Snowflake, or Power BI, consider giving the repository a ⭐ star.

