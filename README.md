# Customer-Churn-Analysis-CODTECH TASK
# INTERN ID-CITS5850
Customer Churn Analysis & Risk Engine
A business-intelligence machine learning project designed to identify utility and telecom customers who are at high risk of leaving (churning). This project builds an end-to-end data pipeline to handle mixed data types (categorical and numerical), train an ensemble classifier, and output granular risk probabilities that corporate retention teams can act upon.

📊 Dataset & Business Drivers
The model tracks simulated enterprise customer accounts across key metrics that directly influence customer loyalty:

TenureMonths: How many months the customer has stayed with the company.

MonthlyCharges: The customer's current billing rate.

SupportTickets: The frequency of technical or billing complaints raised.

ContractType: The customer's structural commitment framework (Month-to-month, One year, or Two year).

Corporate Distribution
Retained Customers (Class 0): 70.66% — The stable baseline customer base.

Churned Customers (Class 1): 29.34% — The at-risk segment directly impacting company revenue.

⚙️ Pipeline Architecture
Feature Engineering Pipeline (ColumnTransformer): Streamlines data preprocessing by automatically branching operations based on data types:

Numerical Features: Scaled using StandardScaler to prevent high billing rates from overpowering shorter month counts.

Categorical Features: Encoded using OneHotEncoder(drop='first') to cleanly map textual contract options into binary flags without creating redundant columns.

Stratified Partitioning: Ensures that the ~30% churn distribution is consistently represented across both training and testing subsets.

Ensemble Modeling: Deploys a RandomForestClassifier to map non-linear interactions (e.g., how high monthly charges combined with multi-year contracts impact churn differently than month-to-month plans).

Granular Risk Scoring: Bypasses rigid binary classification to output explicit probability percentages, allowing companies to prioritize high-risk interventions.
