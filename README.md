## Sales Insights Data Analysis Project

**Sales Insights Data Analysis Project Overview**

The Sales Insights Data Analysis Project aims to provide valuable insights into a company's sales operations by analyzing various aspects of customer data, transactions, revenue, and product categories. This project focuses on reviewing and analyzing key metrics to gain a comprehensive understanding of the company's performance and trends. The main areas of focus include:

1. **Total Number of Customers:**
   The project begins by examining the total number of customers in the company's database. This data provides an essential foundation for understanding the customer base and its growth over time. It helps in evaluating the company's ability to attract and retain customers.

2. **All Customer Records:**
   The project delves deeper into customer records, looking at factors such as demographics, purchase history, and customer segmentation. This analysis allows for a better understanding of customer preferences, behaviors, and patterns, aiding in targeted marketing strategies and personalized customer experiences.

3. **Transactions of the Market:**
   Analyzing transaction data provides insights into the frequency and volume of purchases made by customers. By understanding transaction patterns, the company can identify peak buying periods, popular products, and potential gaps in the market that can be capitalized on.

4. **Total Revenue:**
   The project calculates the total revenue generated over a specific time frame. This metric serves as a key indicator of the company's financial performance. It helps in evaluating the effectiveness of pricing strategies, product launches, and overall sales efforts.

5. **Categories by Zone:**
   The analysis involves categorizing products by various zones or regions. This segmentation allows for a comparison of sales performance across different areas, identifying which product categories are more popular in specific zones. This information can guide inventory management and marketing decisions tailored to each region's preferences.

By conducting this data analysis project, the company can achieve the following benefits:

- **Informed Decision-Making:** Data-driven insights enable the company to make informed decisions regarding inventory management, marketing campaigns, and product development.

- **Optimized Marketing Strategies:** Understanding customer preferences and transaction trends helps tailor marketing strategies to specific customer segments and regions, increasing the likelihood of success.

- **Enhanced Customer Experience:** Personalized experiences can be created based on customer records, leading to improved customer satisfaction and loyalty.

- **Revenue Growth Opportunities:** Identifying underperforming product categories or untapped markets can open up new revenue growth opportunities.

- **Efficient Resource Allocation:** By identifying peak buying periods and popular products, resources can be allocated more efficiently to meet demand.

In conclusion, the Sales Insights Data Analysis Project offers a comprehensive overview of the company's sales operations, customer behavior, revenue, and market trends. Through this analysis, the company can make strategic decisions that positively impact its growth, profitability, and customer satisfaction.

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`



