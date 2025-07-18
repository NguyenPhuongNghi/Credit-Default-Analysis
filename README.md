# Credit Default Analysis
Create a Power BI Dashboard to analyze the credit default risk of HOME CREDIT
## :one: Project Overview:
**:round_pushpin: The main purposes of this project are:**
- Understand key factors contributing to loan default risk
- Detect high-risk customer segments based on credit history and demographics
- Provide actionable insights for portfolio risk management
## :two: Dataset Description:
- **Company:** Home Credit (an international consumer finance company that provides personal loans and retail installment financing)
- **Time period:** Not Given
- **Dataset:** [Home Credit Default Risk on Kaggle](https://www.kaggle.com/competitions/home-credit-default-risk/overview)
<br> Although the Kaggle Dataset of Home Credit has a total of 8 tables, I only use 2 tables to analyze the credit default risk, including **application_train** (storing data about current loan application) and **bureau** (storing all credit history corresponding to each SK_ID_CURR) <br>
#### 1. application_train:
    - TARGET (= 1: clients defaulted on loans, = 0: clients paid on time)
    - Demographics:
      - Gender (CODE_GENDER)
      - Age (DAYS_BIRTH)
      - Income Level (AMT_INCOME_TOTAL)
      - Income Type (NAME_INCOME_TYPE)
      - Occupation (OCCUPATION_TYPE)
      - Contract Type (NAME_CONTRACT_TYPE)
      - Education (NAME_EDUCATION_TYPE)
      - Family Status (NAME_FAMILY_STATUS)
      - Housing Type (NAME_HOUSING_TYPE)
      - Region (REGION_RATING_CLIENT) <br>
        ...
#### 2. bureau:
    - Credit Status (CREDIT_ACTIVE)
    - Credit Types (CREDIT_TYPES)
    - Credit Outstanding Debt (AMT_CREDIT_SUM_LIMIT)
    <br>...

- **Data Modeling:**
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20230001.png?raw=true)
- **North-star Metric:** Default Rate
- **Main KPIs:** 
  - Loan Portfolio: 
    - Internal: Total Disbursement, Number of Loans, Avg Loan Amount, Average Credit Score, 
    - External: Avg Loans per Customer, Avg Active Loans per Customer, Avg Outstanding Debts per Customer
  - Default Risk: Default Rate, Internal Loan - Income Ratio, External Loan - Income Ratio, Loans-to-Goods Ratio, Bad Debt Rate
## :three: Tools used:
- Power BI (Power Query, DAX measures, Visuals)
## :four: Dashboard Structure:
:one: **Overall Loan Portfolio:** analyzes the distribution and characteristics of loan disbursement across different customer segments and financial metrics.
:two: **Internal Default Risk:** explores loan default patterns, risk indicators, and how default rate varies by credit profile and borrower demographics.
:three: **External Credit History:** analyzes how customers’ external credit behavior (number of active loans, avg outstanding debts, etc) affects their default risk.
- Each page has a INFO button to display the meaning of each KPI and a FILTER button to filter by demographics
- Illustration:
    + Info:
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223534.png?raw=true)
    + Filter:
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223634.png?raw=true)
## :five: Dashboard: [attached file]()
### :one: Overall Loan Portfolio: <br>
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223401.png?raw=true)

### :two: Internal Default Risk: <br>
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223833.png?raw=true)
### :three: External Credit History: <br>
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223931.png?raw=true)
### :six: Insights:
