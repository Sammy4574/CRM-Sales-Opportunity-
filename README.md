# CRM-Sales-Opportunity
Customer relationship management (CRM) system

### Table of contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Insights](#insights)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [Refrences](#refrences)


### Project Overview
This data analysis project is to extract useful information out of the CRM sales dataset in order to improve customer relationship, increase revenue, and maximize sales performance.
The project's primary goal will be to analyze important CRM system datasets, such as:

Accounts table: Customer information and company details.

Products table: Product details, pricing, and categorization.

Sales pipeline table: Sales transactions, sales agent and deal stage.

Sales team table: Sales manager and sales regions.

![crm1](https://github.com/user-attachments/assets/e9f7e33a-8028-4cde-bffd-5f137abd4677)
![crm2](https://github.com/user-attachments/assets/61d12063-f9be-4687-896b-c27c56f47cf0)
![crm3](https://github.com/user-attachments/assets/e8ef28e5-f56e-4251-b478-dc140ee754c2)

### Data Sources
The primary dataset used for this analysis is "CRM+Sales+Opportunities" folder, containing information about the accounts, products and each sales made by CRM system.

accounts.xlsx

data_dictionary.xlsx

products.xlsx

sales_pipeline.xlsx

sales_teams.xlsx

### Tools
- MYSQL - Data Cleaning, data retrieval and analysis
  - [Download here](https://mysql.com)
- Power BI - Visualization, creating reports and recommendations

### Data Cleaning
During the project setup, we performed the following tasks:
1. Data loading, cleaning, inspection and formatting
2. Handling missing values
3. Data validation 

### Exploratory Data Analysis
EDA involed exploring the CRM data to answer key questions, such as:
  - What is the total number of accounts in the CRM system?
  - Which product series has the highest sales?
  - How many deals are currently in the "Won" and "Lost" stage?
  - What is the average sales cycle length for each sales agent?

### Data Analysis
Include some SQL functions:

```
SELECT COUNT(*) AS total_accounts
FROM accounts;
```

```
SELECT series, SUM(sales_price) AS total_sales
FROM products
INNER JOIN sales_pipeline ON products.product = sales_pipeline.product
WHERE deal_stage = 'Won'
GROUP BY series
ORDER BY total_sales DESC;
```

```
SELECT sales_teams.sales_agent, ROUND(AVG(DATEDIFF(close_date, engage_date)), 0) AS average_sales_cycle_length
FROM sales_pipeline
INNER JOIN sales_teams ON sales_pipeline.sales_agent = sales_teams.sales_agent
WHERE deal_stage = 'Won'
GROUP BY sales_agent
LIMIT 10;
```


### Insights
- Pipeline Analysis: Visualization of the sales pipeline stages to show the distribution and progression of deals.
- Sales Performance: Identification of top-performing sales agents and their impact on overall sales.
- Account Analysis: Breakdown of customer accounts by region and products to identify high-potential sectors.
- Deal Value Trends: Analysis of deal amounts to uncover patterns related to deal size and closing success.

### Recommendations
Based on the analysis, the following actions were recommended:
- Embark on a sales coaching program aimed at enhancing the potency of sales.
- Give sales representatives the resources and information they need to close more deals.
- Focus sales efforts on the most qualified prospects.
- Put in place a strong customer relationship management (CRM) system to boost sales team productivity.
- Assure data accessibility and accuracy to improve sales forecasting and decision-making.

### Limitations
Sampling bias: It's possible that some customers are not fully represented in the dataset.
Restricted data: Not all sales aspects (e.g economic indicators, competitor data) may be included in the dataset.

### Refrences
[W3Schools](w3schools.com)

[Coursera](coursera.com)

[Stack Overflow](stackoverflow.com)

💻


