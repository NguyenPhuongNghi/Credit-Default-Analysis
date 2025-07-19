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
## :five: Dashboard: [attached file](https://drive.google.com/file/d/1xjdhMy81GvCq0IQm3Wse2YTd0iHleKGX/view?usp=sharing)
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
- Customer Segment with the highest Outstanding Debt Level has the the highest total disbursement (~26,5B), the highest average loan amount, the highest avg credit score but the lowest default rate
<br>➡️ This is understandable because Customers who have high External Outstanding Debt are nornally those with upper-middle and high income level, and good credit score

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
|Age|- **Middle Age Groups (36-45,46-55)** have the highest total disbursement and the highest average loan amount, while **65+ and (18-25) Age Groups** have the lowest figures, likely due to their financial limits  <br>- There's a negative correlation between age and default rate <br> ➡️ Younger age groups, especially under 35, pose higher credit risk and should be more tightly assessed in lending policies.  | Middle Age (36-55)|
|Income Level|- The **(163K, 225K]** income group accounts for the highest Total Disbursement (~52,5B), followed by the **(99K, 135K]** group. The number of loans is also the highest in these two graphs <br>- There is a clear positive correlation between income level and average loan amount, and a general trend of lower default rates for higher income levels.  |  (163K, 225K] |
|Income Type| - **Working Group** has the highest total disbursement (~91M) and the highest number of loans (~158K), followed by **Commercial Associate and Pensioner** <br>- In terms of Avg Loan Amount, **Businessman** leads with ~1,23M, followed by **Maternity leave** (~750k) and **Unemployed** (~746k). However, Unemployed and Maternity Leave have alarmingly high default rates, 36.36% and 40% respectively <br> ➡️ This suggests stricter eligibility criteria or additional scrutiny for applicants| Working
|Occupation|- **Laborers** have the highest total disbursement (~31,5B) and the highest number of loans (~55,1K), followed by Sales staff, Core staff and Managers.<br> - **Managers and Accountants** leads in terms of Average Loan Amount, and these groups also have the strongest creditworthiness (high avg credit score: 0,55 and low default rates(6.21% for Managers and 4.83% for Accountants)  | Laborers
|Contract Type| - **Cash Loan** contributes the most to the disbursement volume (~122M) and Number of loans (~189K), however, the Default Rates of Cash Loans (9.13%) are significantly higher than **Revolving Loans** (5.77%) <br>➡️ stricter eligibility criteria for Cash Loans Application   | Cash Loans |
|Education|- **Secondary/ Secondary Special** and **Higher Education** have the highest total disbursement, approximately 85M and 37,8M <br>- In terms of Avg Loan Amount And Average Credit Score, **Academic degree and Higher education** dominates <br> - The higher the education level is, the lower the Default Rates are | Secondary/secondary special|
|Family Status|  - **Married** Group contributes most to the total disbursement (~90B) and number of loans (138K). This group also leads in the average loan amount and is the second lowest in terms of default rates (8.15%), | Married| 
|Housing Type| - **House/Apartment** Group dominates the Total Disbursement and Number of Loans. This group is the second lowest in terms of Default Rates (8.51%)| House/Apartment
|Region| - Rating = 1: low-risk, well-developed region <br> - Rating = 2: average-risk region <br> - Rating = 3: higher-risk region <br>- Most Disbursement Volume and Number of Loans come from **Region 2** and its Default Rates is also the second highest (8.57%) | Region 2|

➡️ **CONCLUSION:**
The current target loan portfolio mainly consists of female clients aged 36 to 55, belonging to the upper-middle income group. These individuals are typically manual workers, applying for cash loans, and possess a secondary or vocational education. Most are married, own a house or apartment, and reside in areas classified as Region Rating 2.


### :two: Internal Default Risk: <br>
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223833.png?raw=true)
#### 1. Correlation between Defaults Rates and Credit Score/Loans-to-Goods Ratio/Internal Loan-Income Ratio :
- The higher the Avg Credit Score is, the lower the Default Rates is <br>➡️ Default Rates are exceptionally high in (0,0.3) credit score buckets, suggesting stricter eligible criteria for these groups
- Customers whose loan amount is higher than the price of goods are more likely to default on their loans (8.8%)
- Customers whose loan amount–income ratios fall within the range (0, 1.8] and above 5.7 are less likely to default. This can be explained by the fact that:
<br>➤ Customers in the lower ratio range likely borrow within their financial means, showing responsible borrowing behavior,
<br>➤ While customers in the very high ratio group may have other strong credit characteristics (e.g., stable income, assets, or positive credit history) that enable them to handle large loan amounts relative to income.

#### 2. Correlation between Defaults Rates and Demographics :
| Demographics            | Conclusion        | Dominant Segment    |
|-------------------------|-------------------|---------------------|
|Gender| - **Female** borrowers have lower default rates (7%) than **Male** counterparts (10.1%) <br>- In both Gender Segments, the Default Rates correlate negatively with the Income Level | Male|
|Age|- There's a negative correlation between age and default rate <br>- In each Age Group, as the Income Levels increase, the Default Rates generally decrease <br> ➡️ This is understandable, as the youngest age group typically has weaker credit profiles and limited financial capacity. | (18-25) |
|Income Level|- The Mid-level Income Groups **(99K,135K] and (163K, 225K]** have the highest Default Rates, while those whose income are above 225 are the least likely to default | 99K,135K] and (163K, 225K]  |
|Income Type| - **Maternity Leave and Unemployed Group** have unexceptionally high Default Rates (40% and 36.4% respectively, while the figures for the remaining groups remain below 10%  | Unemployed|
|Occupation|- **Low-skill Laborers** have the highest Default Rates as expected (17.2%), followed by Waiters/barment staff and Drivers <br> ➡️ This is understandable since **Low-skill Laborers** often have unstable incomes, limited financial reserves, and lower credit reliability, making them more vulnerable to repayment difficulties.  | Low-skill Laborers|
|Contract Type| - **Cash Loan** have higher Default Rates (8.3%) than **Revolving Loans** (5.5%). <br> ➡️ This can be explained by the fact that Cash Loans typically involve larger lump-sum disbursements without flexible repayment terms, increasing financial pressure on borrowers, whereas Revolving Loans offer more flexible, smaller, and recurring borrowing limits, allowing better cash flow management and reducing default likelihood.  | Cash Loans |
|Education|- The Default Rates increase as the Education Level decrease. <br>- **Lower Secondary** has the lowest Default Rates (10.9%), likely due to limited financial literacy and weaker understanding of loan obligations, leading to poorer debt management and higher risk of delinquency. | Lower Secondary|
|Family Status|  - **Single/not married and Civil marriage** have the highest Default Rates (~9.9%), likely due to to less financial stability, fewer shared financial responsibilities, and potentially lower household income compared to married individuals.| Civil marriage and Single/not married| 
|Housing Type| - **Rented apartment and With Parents** Group have the highest Defaults Rates (12.3% and 11.7% respectively), likely due to lower financial independence and limited asset ownership, which may indicate weaker repayment capacity and higher credit risk| Rented Aparment and with Parents
|Region|- Customers living in **Region 3** have the highest Default Rates, likely due to less developed economic conditions, lower employment stability, and limited access to financial education or support services in that region. | Region 3|

➡️ **CONCLUSION:**
The customer segment most prone to loan defaults primarily includes male borrowers aged 18–25, with a middle-income level (99K–162K), who are unemployed, working as low-skilled laborers, taking out cash loans, having lower secondary education, being single/not married or in a civil marriage, and residing in rented apartments or with their parents in Region 3.


### :three: External Credit History: <br>
![alt](https://github.com/NguyenPhuongNghi/Credit-Default-Analysis/blob/main/photos/Screenshot%202025-07-18%20223931.png?raw=true)
#### 1. Correlation between Defaults Rates and External Active Loans/External Outstanding Debt/External Loan - Income Ratio:
- The Default Rates correlate positively with the Number of Active Loans, indicating that customers who already have multiple active loans are more likely to experience repayment difficulties, possibly due to over-leverage or poor debt management.
- The Default Rates are the lowest in External Outstanding Debt in (0,75k] and Above 587K, likely due to minimal repayment pressure in newly disbursed small loans and stronger creditworthiness in customers with high loan amounts.
- As the External Loan - Income Ratios increase, the Default Rates also increase, indicating that customers with a high proportion of external debt relative to income are more financially strained, and thus more prone to default. 
<br>⚠️**P/s: The External Active Loans/External Outstanding Debt/External Loan - Income Ratio are calculated based on the credit history in bureau (stored in "bureau" table), not internal dataset at Home Credit**

#### 2. Defaults Rates and External Active Loan-Income by Demographics:
| Demographics            | Conclusion        |
|-------------------------|-------------------|
|Gender|- Male borrowers have a higher overall default rate (10.06%) compared to female borrowers (8.27%).  This trend is consistent across all loan–income ratio bands <br> - For both genders, the default rate increases as the loan–income ratio rises, indicating higher financial strain with larger relative debts.| 
|Age|- Younger borrowers with high loan-to-income ratios have high default rates <br> ➡️ apply stricter credit checks and limits for this segment to mitigate default risk. <br>- Older borrowers appear more creditworthy, even at higher loan-income ratios.| 
|Income Level|- For all income groups, default rates generally increase with rising loan–income ratios, suggesting that higher loan burden relative to income increases risk <br> - In all loan–income ratio ranges, the default rates correlate negatively with the income level <br>➡️ Lower-income borrowers with high loan-to-income ratios are more likely to default, whilw the highest-income borrowers are the lowest risk of default in all loan-to-income ratio ranges |

#### 3. Default Rates segmented by Average Outstanding Debt levels and External Loan-to-Income ratios:
- The highest default rate (16.13%) occurs in the 0–75K debt range with a loan-to-income ratio between 3.6–7.2, suggesting that lower debt holders with higher relative borrowing are most at risk.
- For lower loan-to-income ratios (0–0.7), default rates remain relatively low across all debt levels, indicating lower risk. As the lower loan-to-income ratios increase, the default rates in all debt ranges also increase.
- The overall default rate is the highest in middle-level debt ranges and drops sharply for customers with the highest debt levels (Above 587K), possibly due to stricter lending criteria or more robust financial profiles in this group.
<br>➡️**Conclusion:** Borrowers with low to moderate debt but high external loan-to-income ratios are particularly vulnerable to default, highlighting the importance of monitoring not just absolute debt levels but also relative borrowing capacity.

### :six: Insights:
|No.| Insight  | Solution            | Details        |
|---|-----|-------------------|-------------------|
|1| Borrowers aged 18–25 and 26–35 have the highest default rates (13.2% and 11.7%, respectively)|Tighten Lending for Younger Age Segments|- Implement stricter credit checks or require guarantors/co-signers for younger applicants.<br>- Offer smaller loan amounts or require lower internal/external loan-income ratios for this group.|
|2| Default rate increases with higher loan-income ratios, especially in (3.6, 7.2] range.  |Cap Loan-to-Income Ratios at High Risk Thresholds    |- Enforce loan-income ratio limits (e.g., max 3.6) for customers with low-to-middle income levels. <br> - For high-income borrowers, allow higher ratios but combine with credit history, credit score filters or collateral requirements. |
|3| Customers with higher external debt (>587K) actually show slightly lower default rates (7.57%) than those in the mid-debt range   |Leverage External Outstanding Debt   |- Don’t take tougher actions or limiting access for customers based solely on their total debt levels ➡️ Prioritize debt-to-income and credit behavior instead. <br> - Monitor external debt trends over time for early warning signals.    |
|4| Borrowers with credit scores >0.5 have very low default rates (under 5%) |Prioritize High-Credit Score Segments   | - Create premium loan products or fast-track approvals for customers with high credit scores. <br>- Use score-based pricing to reward low-risk borrowers with better interest rates.    |
|5|Borrowers living with parents or in rented/municipal apartments face highest default rates (11%–13%).|Adjust Lending Based on Housing Type   | - Apply stricter screening or loan caps for borrowers with high-risk housing types. <br> - Consider housing stability as a variable in the credit scoring model.  |
|6|  Default rate rises sharply with more than 3 active loans (up to 17.2% at 10+ loans)  | - Manage Risk by Number of Active Loans    | - Limit the number of concurrent loans per customer. <br>-Monitor and flag customers reaching 4+ active loans for review or intervention. |
|7|  Borrowers in the middle-income range (135K–162K) have the highest default rates (8.68%), while high-income (>225K) borrowers are at lower risk of default.   | Target Middle-Income Segments| - Conduct enhanced risk assessments for middle-income segments.<br>- Provide financial literacy support to help them manage loan obligations better.

