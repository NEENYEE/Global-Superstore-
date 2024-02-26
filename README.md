## Sales Performance Analysis

![image](https://github.com/NEENYEE/Global-Superstore-/assets/101926233/3ec26576-3040-4c0f-832c-80f0789f2ebd)


Welcome to the Global Superstore Sales Analysis documentation! Here, we embark on a journey to extract valuable insights from the sales data of Global Superstore, a leading global online retailer headquartered in New York. With a vast product catalog and a commitment to being a one-stop-shop for customers worldwide, Global Superstore serves a diverse clientele spanning 147 countries.


## Problem Statement

The following questions have been identified as key areas of analysis to drive improvements in business operations:

Question 1:
a) Identify the three countries that generated the highest total profit for Global Superstore in 2014.
b) For each of these three countries, find the three products with the highest total profit. Specifically, determine the products' names and the total profit for each product.

Question 2:
a) Identify the three subcategories with the highest average shipping cost in the United States.

Question 3:
a) Assess Nigeria’s profitability (i.e., total profit) for 2014 and compare it to other African countries.
b) Investigate potential factors responsible for Nigeria’s poor performance, such as shipping costs and average discount rates.

Question 4:
a) Identify the product subcategory that is the least profitable in Southeast Asia.
b) Determine if there is a specific country in Southeast Asia where Global Superstore should consider discontinuing the identified subcategory.

Question 5:
a) Determine the least profitable city in the United States (in terms of average profit), excluding cities with less than 10 orders.
b) Investigate the factors contributing to the low average profit in this city.

Question 6:
a) Identify the product subcategory with the highest average profit in Australia.

Question 7:
a) Determine the most valuable customers of Global Superstore and analyze their purchasing behavior.


## Data Source

The dataset was provided by Digitaley drive as an integral part of my capstone project [download here](https://docs.google.com/spreadsheets/d/1nxESpFzWjlGDMGDVLH69xmDzIl9l6OEq/edit#gid=633280281). The dataset is made up of three tables namely:
- Orders - made up of 51,290 rowa and 24 columns.
- Returns - made up of 1173 rows and 3 columns
- Persons - made up of 13 rows and 2 columns

## Tools

This analysis leveraged Power BI Desktop for its interactive visualizations, data modeling capabilities, and seamless integration with various data sources. Within Power BI, Power Query was employed for data transformation and cleaning tasks, including shaping data, merging datasets, and creating custom calculations. Features like buttons and tool tips were also include to enhance page navigations.

## Data Cleaning and Transformation

Data preparation is a critical phase in the analysis process, involving various tasks to clean, transform, and structure the raw data for analysis. In the case of the Global Superstore sales data, several steps were undertaken to ensure the data was accurate, consistent, and ready for analysis.

**Steps Taken**
- Data Sorting: Sorted the data by Row ID to ensure consistency and facilitate subsequent operations.
Find and Replace: Replaced 'JoyBell-'

- Date Format Standardization: changed all date columns to YYYY-MM-DD format to ensure uniformity and compatibility for analysis.

- Feature engineering: Created separate columns for year and month from the date data to facilitate time-based analysis; and dropped the "Postal Code" column as it was deemed irrelevant for the analysis.

- Handling Blanks and Duplicates: Checked for and addressed any blank or duplicate records in the dataset to maintain data integrity. It was observed that each customer had 2 customer IDs and this was consistent across all customers.

## Data Analysis

The data analysis phase involved leveraging DAX measures to delve into the dataset and extract valuable insights. Below are two snippets of my DAX measures

### Measure: Average Discount

Description: Calculates the average discount for sales in the African market during the year 2014.

```dax
Average Discount = 
CALCULATE(
    AVERAGE('Sales'[Discount]), 
    'Sales'[Market] = "Africa",
    YEAR('Sales'[Order Date]) = 2014
)
```

### Measure: Profit Margin

Description: Calculates the profit margin as a percentage of total sales.

```dax
Profit Margin = DIVIDE(SUM('Sales'[Profit]), SUM('Sales'[Sales])) * 100
```

## Key insights and Recommendations

Visualizations are instrumental in distilling complex data into actionable insights. This section showcases key visualizations derived from the analysis of Global Superstore sales data, along with the pivotal insights garnered from them. The visualizations were grouped into four categories namely: United states, Nigeria, Sub-category and Customers.
[global--.pdf](https://github.com/NEENYEE/Global-Superstore-/files/14409772/global--.pdf).

- Global superstore is made up of 138 countries, with total sales of $12.6M, total profit $1.5M and a profit margin of 11.6%, all across four years (2011-2014)
- The three countries that generated the highest income are united states, India and China.
- The subcategories with the highest shipping cost in the US are copiers ($165.3), machines ($132.2) and tables ($70)
- In 2014, Nigeria made no profit acroos all the months. When compared to other african countries in Africa, it was observed to be one of the contries with the highest losses. On further investigation, it was observed that these losses could be as a result high discount rate as it was one of the three countries with the highest average discount. The findings from the average shipping costs revealed that it wasn't a significant factor attributed to the losses.
- In south asia, the least profitable sub-categories are tables, accessories and supplies with profits of -18,618.3, -8,641.5 and -4,034 respectively. With table being the least profotable, it was observed that Indonesia incurred significant losses from this product. Therefore, further investigations should be carried to find out why and probably suspend the supply of tables to indonesia.
- The least profitable cities in the US are lancaster, burlington, San-Antonio and Rockford. These cities offered the most discount, made the least sales and very few orders. Therefore, thorough analysis of the market conditions in these cities should be carried out.
- In Australia, the prodduct category withbthe least profits are tables, fasteners, labels, envelopes, binders and art.
- There are 794 customers across 138 countries. The most most valuable customers by profit are Tamara Chand (copiers), Raymond Buch (copiers), Sanjit Chand (binders), Hunter Lopez (copiers) and Bill Eplett (copiers) with total profits of 8,672.9, 8,453, 8,205, 7,816, 7,410. They have been at the top from 2011 to 2014.
- They are the top customers because they purchase most of top sub-categories by profit.








