# Customer_Churn_Analysis
Power BI analysis of telecommunication customer churn using DAX to uncover key churn drivers, tenure trends, payment behavior, and actionable retention insights.

## Project Overview

The telecommunication industry faces high customer churn rates, leading to revenue loss. By analyzing churn patterns, a company can implement strategic retention plans, improve customer experience, and optimize pricing models. 

## Objectives 
This project seeks to analyze customer churn in a telecommunication company by examining customer demographics, subscription details, contract types, billing information, and service usage. My project aims to:

- Identify key churn drivers
- Segment high-risk customers
- Offer strategic retention solutions
- Develop data-driven recommendations using Power BI

## Data Source

The dataset used is synthetically generated to mirror real-world telecom customer behavior.

## Tools
- **Power BI**
- **DAX**
- **Python (for data generation)**

# Dataset Description

- **Rows**: 7,043 customers
- **Columns**: 21 variables
- **Features**:
  - Customer demographics
  - Subscription and service usage
  - Contract and payment details
  - Monthly and total charges
  - Churn indicator
    
# Data Cleaning & Preprocessing

- Verified data types 
- Categorical data standardization: Numerical values in the Senior Citizen column were changed to "No" for 0 and "Yes" for 1.
  ![Senior Citizens](https://github.com/user-attachments/assets/04f0ee5d-bd04-4643-9bee-58896104ae34)

- Handled missing - Missing values in the `TotalCharges` column were found to correspond with customers who had a tenure of 0 months. This indicates that these customers were newly subscribed or never activated their services, which explains why they had not been billed. Additionally, most of these customers did not have Internet service, possibly leading to non-subscription and hence, no charges.
![Total Charges1](https://github.com/user-attachments/assets/23b21577-f082-42f5-98a1-09ad121aa623)

- No duplicate entries found
- The tenure column was transformed into an integer data type and then divided into five groups:
  - 0–12 months
  - 13–24 months
  - 25–48 months
  - 49+ months
![Tenure Groups](https://github.com/user-attachments/assets/8a94162b-eabc-408f-b1b0-f6187d291e25)

- Created spending index for customer segmentation
![Spending Group](https://github.com/user-attachments/assets/45ade027-7487-429e-a1b4-6bec13c3d2e9)


## Key DAX Measures

- `Churn Rate`
![Churn Rate](https://github.com/user-attachments/assets/527e2c1a-0abb-4cc8-81ea-18ddf36f18d2)

- `Avg Monthly Charges (Churned vs. Retained)`
![Average Monthly Charges Churned](https://github.com/user-attachments/assets/b54de916-aea9-44e0-b342-1f0792cd48a2)
![Avg Monthly Charges Retained](https://github.com/user-attachments/assets/a3706235-f77c-4438-b44b-616e6b59c0be)

- `Avg Total Charges`
![Avg Total Charges Churned](https://github.com/user-attachments/assets/d9b43d88-9a78-43a7-9fd7-03f28b617dbb)

- `Retention Rate`
![Retention Rate](https://github.com/user-attachments/assets/054f8a89-f31d-4d9b-aa65-e4a6e4b168ea)

- `Monthly Revenue Lost`
![Revenue Lost](https://github.com/user-attachments/assets/1231e21e-08ff-4b22-b89d-4fadb62a631a)

- Churn rates by feature (Tech Support, Tenure, Streaming, Payment Type, etc.)
![Tech Support Churn Rate](https://github.com/user-attachments/assets/915fca3b-4631-4974-831b-438c02fbf485)
![Streaming Movies Churn Rate](https://github.com/user-attachments/assets/a8ad3140-2cdf-49db-98cc-473b49fdd69e)
![PhoneService Churn Rate](https://github.com/user-attachments/assets/09d24ad7-c1ef-4ece-b87f-807fd694abbb)

## Data Analysis & Visualization
### 1. Executive Summary
![Executive Summary](https://github.com/user-attachments/assets/e57e254e-03f8-417f-9d06-789d811a0dd5)
### Key Findings:
1.	**Total Customers:** 7,043 | **Churn Rate:** 26.54% | **Retention Rate:** 73.46%
-	This translates to 1,869 lost customers out of 7,043, indicating a substantial revenue impact, while a 73% retention rate appears healthy.
2. **Customer Tenure & Churn:** The churn rate declines as customer tenure increases, with the highest churn (53.33%) occurring in the first 6 months.
-	This signals dissatisfaction or unmet expectations early in the customer journey, as the early-stage experience is critical.
-	Poor onboarding, unmet expectations, or lack of early engagement may be driving early exits.
3. **Contract Type Influence:** Month-to-month contracts have the highest churn (1,655), unlike two-year and one-year contracts, which show strong retention.
-	Customers on long-term contracts are more stable, proving that longer commitments improve retention. Incentivizing longer commitments may reduce churn.
-	Implication: Flexible plans, while attractive, lead to instability.
4. **Higher Monthly Charges Correlate with Churn.**
-	Churned customers pay an average of $74/month, suggesting price sensitivity. Customers perceiving insufficient value for cost are more likely to leave.
5. **Payment Method Correlation:** Electronic check users represent the largest churn segment (1,071 customers), potentially due to service dissatisfaction or lack of engagement.
-	Digital payment options (credit card, bank transfer) have lower churn rates.
-	Friction in payment processes contributes to attrition.

### 2. Churn Analysis
![Churn Dashboard](https://github.com/user-attachments/assets/c0b7fbbf-d240-435e-a1f9-f624e0781b62)
### Key Findings:
1.	**Revenue Impact:** 1,869 customers churned, resulting in $139K monthly revenue loss. This highlights the urgency for retention strategies.
2.	Churn is evenly split across gender (**Male: 930, Female: 939**)
3.	Senior citizens represent a considerable churn group (**476 vs. 1,393 non-seniors**), suggesting age-specific service improvements may help.
4.	Customers using multiple services (**e.g., phone service, streaming movies**) or fiber optics (**1,297 cases**) show higher churn counts, suggesting service dissatisfaction.
-Internet or streaming services and tech support, while popular, may not meet customer expectations.
-	Heavy churn among users of StreamingTV, Tech Support, and Phone Service may indicate service quality or cost issues.
5. High churn is associated with customers in the new or short-tenure monthly charge brackets, suggesting they may not see sufficient value for the cost.

## Recommendations

1. **Enhance Onboarding Experience:** Focus on improving the first 6-month customer journey through personalized engagement and onboarding support. Early-Tenure Engagement, e.g., launch a “90-Day Success Program” with check-ins and incentives for new customers. Also introduce retention offers (e.g., **loyalty rewards, waived fees**).
2. **Incentivize Long-Term Contracts:** Offer a **10%** discount for annual contracts and free perks (e.g., extra data) for two-year sign-ups.
3. **Optimize Pricing for At-Risk Customers:** Introduce customized plans for high-spending churn candidates (e.g., $74+ tier) with added benefits.
4. **Promote Automated Payments:** Introduce seamless and secure digital payment methods to retain customers who prefer convenience. Also launch an “Auto-Pay Bonus” campaign (e.g., $5 monthly credit for enrolling in auto-pay).
5. **Service Quality Assurance:** Mandate tech support inclusion for premium bundles to reduce frustration-driven churn.
6. **Prioritize fiber optic internet service and senior citizen interventions** or retention programs to recover ~40% of lost revenue. Dive deeper into customer feedback related to fiber optic services and implement service quality improvements.
7. **Promote Service Bundles:** Discount multi-service packages (e.g., internet + streaming) to improve customer retention.

## Conclusion
The analysis reveals that **new customer experience, contract flexibility, pricing,** and **payment methods** are pivotal to reducing churn. By implementing targeted onboarding, loyalty incentives, and payment conveniences, the company can significantly improve retention and revenue stability. I'll be sharing a more thorough discount predictive analysis soon.









