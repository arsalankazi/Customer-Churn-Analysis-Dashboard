# Customer Churn Analysis Dashboard (Power BI)

An end-to-end Power BI project analyzing telecom customer churn. Built during the Power BI Internship at SaiKet Systems.

## Problem

Telecom companies lose revenue when customers leave. Acquiring new customers costs more than retaining existing ones. This project analyzes 7,043 customers to find out who is churning, why, and what can be done about it.

## Dataset

Telco Customer Churn dataset (public, originally from IBM). 7,043 rows, 21 columns. Key fields: gender, tenure, Contract, PaymentMethod, InternetService, MonthlyCharges, TotalCharges, Churn.

## Tools Used

Power BI Desktop, Power Query, DAX, Data Visualization.

## What I Did

**Level 1 – Data Connection:** Imported CSV into Power BI.

**Level 2 – Data Transformation:** Fixed TotalCharges (11 blanks replaced with 0, converted to Decimal). Set correct data types. Verified 100% valid, 0% error, 0% empty. Created 12-month tenure bins.

**Level 3 – Dashboard:** Built a single-page report with four parts: Churn Rate gauge, Demographics (pie/donut), Tenure distribution (column chart), and Churn Analysis (stacked charts by Contract, PaymentMethod, InternetService).

## DAX Measure

```dax
Churn Rate =
DIVIDE(
    CALCULATE(
        COUNTROWS(TelcoCustomerChurnDataset),
        TelcoCustomerChurnDataset[Churn] = "Yes"
    ),
    COUNTROWS(TelcoCustomerChurnDataset)
)

Key Insights
Overall churn is 26.54% (1,869 of 7,043). Month-to-month contracts churn at ~43%, one-year at ~11%, two-year at ~3%. Fiber optic churns at ~42%, DSL at ~19%, no internet at ~7%. Electronic check users churn at ~45%. New customers (0–12 months) churn at ~48%. Gender has almost no impact. Customers without partner/dependents churn more.

Recommendations
Offer discounts to move month-to-month customers to longer contracts.

Review Fiber optic pricing and service quality.

Run onboarding programs for first 3–6 months.

Encourage automatic payments over electronic check.

Repository Structure
data/ → TelcoCustomerChurnDataset.csv

powerbi/ → Level1DataConnection.pbix, Level2DataTransformation.pbix, Level3Dashboard.pbix

screenshots/ → dashboard.png

README.md