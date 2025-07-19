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
1️⃣ **Overall Loan Portfolio:** analyzes the distribution and characteristics of loan disbursement across different customer segments and financial metrics.
<br>2️⃣ **Internal Default Risk:** explores loan default patterns, risk indicators, and how default rate varies by credit profile and borrower demographics.
<br>3️⃣ **External Credit History:** analyzes how customers’ external credit behavior (number of active loans, avg outstanding debts, etc) affects their default risk.
- Each page has a INFO button to display the meaning of each KPI and a FILTER button to filter by demographics
- Illustration:
    + Info:
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223534.png?raw=true)
    + Filter:
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223634.png?raw=true)
## :five: Dashboard: [attached file]()
### :one: Overall Loan Portfolio: <br>
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223401.png?raw=true)
#### 1. By Income Level:
- Highest disbursement in the 163K–225K income group (~52B), followed by 100K–135K.
- Mid-income segments also has the highest number of loans 
--> Mid-income segments are the primary target for lending. They might be the most responsive or least risky in this strategy.
- Although the high-income segment (above 225K) has lower total disbursement and lower number of loans, its average loan amount (883K) is significantly higer than other segments, suggesting higher borrowing capacity.
- Average Credit Score of the high-income segment is also the highest (0.536) and its default rate is the lowest 6.52%, indicating stronger creditworthiness
<br>➡️ This suggest that High-income Segment is a low-risk, high-value segment.
<br>➡️ Strategic focus on expanding outreach, offering premium products, or increasing approval rates in this group could boost portfolio quality and margin performance.  

#### 2. By External Outstanding Debt Level:
- Customer Segment with the highest Outstanding Debt Level has the the highest total disbursement (~26,5B), the highest average loan amount, the highest avg credit score but th- e lowest default rate
➡️ This is understandable because Customers who have high External Outstanding Debt are nornally those with upper-middle and high income level, and good credit score

#### 3. By Internal Loan - Income Ratio:
- Customers with a ratio >5.7 receive the most loans (~64.6B) and its average loan amount is also the highest (~1M). However, this group has the highest avg credit score (0.528) and the lowest default rate (7.24%), indicating strong creditworthiness
- Group with the lowest ratio is also monitored effectively, shown by its relatively low default rate (7.31%), while the figures for groups with middle-level ratios are higher (~8.5% on average)

#### 4. By Average Credit Score:
- Customer Segments with mid-level Average Credit Score (0.4-->0.7) have the highest total disbursement, and the highest number of loans
- There is a positive correlation between Average Credit Score and Avg Loan Amount, suggesting that the loan disbursement policy appropriately adjusts loan size based on borrowers’ creditworthiness.
<br> ➡️ The company appears to apply a risk-based pricing or approval approach, granting larger loans to more creditworthy customers.
- By contrast, there is a negative correlation between Average Credit Score and Default Rate. Specifically, applicants in the lowest credit score buckets (e.g., (0,0.1] and (0.1,0.2]) exhibit exceptionally high default rates (31.71% and 26.54% respectively), despite small loan volumes.
<br>➡️ To minimize risk exposure, loan approval processes should include stricter eligibility criteria or additional scrutiny for applicants with very low credit scores.

#### 4. By Demographics:
| Demographics            | Conclusion        | Dominant Segment    |
|-------------------------|-------------------|---------------------|
|Gender| - **Female** borrowers represent a more reliable segment in terms of creditworthiness and portfolio quality. Specifically, they contribute the most to disbursement volume with a higher credit score (0.519) and lower default rate (7%).<br>- **Male** borrowers, while receiving larger average loans, pose higher risk, reflected in their higher default rate (10.14%).  | Female|
|Age|- **Middle Age Groups (36-45,46-55)** have the highest total disbursement and the highest average loan amount, while **65+ and (18-25) Age Groups** have the lowest figures, likely due to their financial limits  <br>- There's a negative correlation between age and default rate ➡️ Younger age groups, especially under 35, pose higher credit risk and should be more tightly assessed in lending policies.  | Middle Age (36-55)|
|Income Level|   |   |
|Income Type| Giá trị 2.2  | 
|Occupation| Giá trị 2.2  | 
|Contract Type| Giá trị 2.2  | 
|Education| Giá trị 2.2  | 
|Family Status| Giá trị 2.2  | 
|Housing Type| Giá trị 2.2  | 
|Region| Giá trị 2.2  | 

➡️ The target loan portfolio is primarily composed of female customers aged 36–55


### :two: Internal Default Risk: <br>
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223833.png?raw=true)
### :three: External Credit History: <br>
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223931.png?raw=true)
### :six: Insights:
