# Credit_Card_Weekly_Financial_Dashboard

📌 Project Overview

The Credit Card Weekly Financial Dashboard is a Power BI project designed to provide real-time insights into credit card operations, revenue performance, customer segmentation, and risk metrics.

The dashboard enables stakeholders to monitor key performance indicators (KPIs), track week-over-week (WoW) growth, and evaluate activation and delinquency rates for better financial decision-making.

🎯 Project Objective

To develop a comprehensive weekly dashboard that:

Tracks revenue and transaction trends

Monitors credit card activation and delinquency rates

Analyzes customer demographics and segmentation

Provides actionable business insights

Supports data-driven financial decisions

🛠 Tools & Technologies Used

SQL Server – Data extraction & querying

Power BI Desktop – Dashboard development

DAX (Data Analysis Expressions) – KPI calculations

Data Modeling – Relationship building & schema design

📊 Key KPIs Monitored

💰 Total Revenue – ₹57M+

💳 Total Transaction Amount – ₹46M

📈 Total Interest Earned – ₹8M

📊 Week-over-Week (WoW) Revenue Growth – 28.8%

👥 Customer Activation Rate – 57.5%

⚠ Delinquency Rate – 6.06%

📈 Dashboard Features
🔹 1. Revenue Monitoring

Combined annual fees, transaction amount, and interest earned

Weekly performance comparison

Current vs Previous week revenue tracking

🔹 2. Customer Segmentation

Age group classification

Income group categorization

Gender-based revenue contribution analysis

Male: ₹31M

Female: ₹26M

🔹 3. Card Category Performance

Blue & Silver cards contribute 93% of overall transactions

🔹 4. Geographic Insights

TX, NY & CA contribute 68% of total revenue

🔹 5. Risk Metrics

Activation Rate: 57.5%

Delinquency Rate: 6.06%

🧮 Important DAX Calculations
Revenue Calculation
Revenue = 
'cc_detail'[annual_fees] + 
'cc_detail'[total_trans_amt] + 
'cc_detail'[interest_earned]
Week Number Calculation
week_num2 = WEEKNUM('cc_detail'[week_start_date])
Current Week Revenue
Current_week_Revenue =
CALCULATE(
    SUM('cc_detail'[Revenue]),
    FILTER(
        ALL('cc_detail'),
        'cc_detail'[week_num2] = MAX('cc_detail'[week_num2])
    )
)
Previous Week Revenue
Previous_week_Revenue =
CALCULATE(
    SUM('cc_detail'[Revenue]),
    FILTER(
        ALL('cc_detail'),
        'cc_detail'[week_num2] = MAX('cc_detail'[week_num2]) - 1
    )
)
Age Group Segmentation
AgeGroup =
SWITCH(
    TRUE(),
    cust_detail[customer_age] < 30, "20-30",
    cust_detail[customer_age] < 40, "30-40",
    cust_detail[customer_age] < 50, "40-50",
    cust_detail[customer_age] < 60, "50-60",
    cust_detail[customer_age] >= 60, "60+",
    "Unknown"
)
📌 Key Insights Generated

Revenue increased by 28.8% in Week 53

Blue & Silver cards dominate transaction volume

Male customers contribute higher revenue than female customers

Majority revenue comes from top 3 states (TX, NY, CA)

Moderate credit risk observed with 6.06% delinquency rate

📂 Project Workflow

Data Extraction from SQL Server

Data Cleaning & Validation

Data Modeling (Fact & Dimension Tables)

DAX Measure Creation

Dashboard Design & KPI Development

Insights & Business Recommendations

💡 Business Impact

Enabled real-time financial performance monitoring

Automated weekly revenue tracking

Identified customer behavior patterns

Supported credit risk assessment

Reduced manual reporting effort

🚀 Future Enhancements

Predictive churn modeling

Credit risk forecasting

Time intelligence (YTD, MTD, YoY comparisons)

Customer lifetime value analysis

👨‍💻 Author

Bharat jadoun
Data Analyst | SQL | Power BI | DAX

⭐ How to Use

Download the .pbix file

Open in Power BI Desktop

Refresh data connection (if required)

Explore interactive filters and slicers
