# Data Dictionary

This document describes the main variables used in the Credit Risk Intelligence project.

The complete original data dictionary is provided by the dataset source. This file documents the variables selected for the analysis.

## application_train.csv

| Column | Description | Business Use |
|---|---|---|
| `SK_ID_CURR` | Unique client identifier | Join key across tables |
| `TARGET` | Payment difficulty indicator | Default / delinquency target |
| `AMT_INCOME_TOTAL` | Client annual income | Income-based risk segmentation |
| `AMT_CREDIT` | Credit amount requested | Credit exposure analysis |
| `AMT_ANNUITY` | Loan annuity amount | Financial commitment analysis |
| `AMT_GOODS_PRICE` | Price of goods financed | Loan context analysis |
| `DAYS_BIRTH` | Client age in days | Customer profile analysis |
| `DAYS_EMPLOYED` | Employment duration in days | Employment stability analysis |
| `NAME_INCOME_TYPE` | Client income category | Risk segmentation |
| `NAME_EDUCATION_TYPE` | Client education level | Descriptive profile analysis |
| `NAME_FAMILY_STATUS` | Client family status | Descriptive profile analysis |
| `NAME_HOUSING_TYPE` | Client housing type | Descriptive profile analysis |
| `CNT_CHILDREN` | Number of children | Household profile analysis |
| `CNT_FAM_MEMBERS` | Number of family members | Household profile analysis |

## previous_application.csv

| Column | Description | Business Use |
|---|---|---|
| `SK_ID_PREV` | Unique previous application identifier | Previous application identification |
| `SK_ID_CURR` | Unique client identifier | Join key with client table |
| `NAME_CONTRACT_STATUS` | Previous application status | Approval and rejection analysis |
| `AMT_APPLICATION` | Amount requested in previous application | Credit demand analysis |
| `AMT_CREDIT` | Amount granted in previous application | Historical credit exposure |
| `AMT_ANNUITY` | Previous loan annuity | Payment commitment analysis |
| `CNT_PAYMENT` | Number of installments | Loan term analysis |
| `DAYS_DECISION` | Days before current application when decision was made | Historical recency analysis |

## installments_payments.csv

| Column | Description | Business Use |
|---|---|---|
| `SK_ID_PREV` | Previous credit identifier | Join key with previous applications |
| `SK_ID_CURR` | Unique client identifier | Join key with client table |
| `NUM_INSTALMENT_VERSION` | Installment plan version | Payment-plan context |
| `NUM_INSTALMENT_NUMBER` | Installment sequence number | Payment-history context |
| `DAYS_INSTALMENT` | Scheduled payment date in days | Due-date reference |
| `DAYS_ENTRY_PAYMENT` | Actual payment date in days | Payment-date reference |
| `AMT_INSTALMENT` | Amount due for the installment | Amount due analysis |
| `AMT_PAYMENT` | Amount paid for the installment | Payment behavior analysis |

## Project Definitions

- `TARGET = 1`: Client with payment difficulties.
- `TARGET = 0`: Client without payment difficulties.
- The original dataset uses anonymized variables and relative dates.
- Derived variables and transformation rules will be documented in the Silver layer.
