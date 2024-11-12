# LITA-Capstone-Project

### Project Title
Sales Performance Analysis for a Retail Store

### Project Summary
In this project, I'll be analyzing the sales performance of a retail store. To explore sales data and uncover key insights such as top-selling products, regional performance, and monthly sales trends. The goal is to produce an interactive Power BI dashboard that highlights the findings using Excel, PowerBi and SQL.

### Data Source
This is the regional dataset of the retail store provided by LITA for the project.

### Tools Used
- **Microsoft Excel**
  1. Data cleaning
  2. Analysis
  3. Visualisation
  
- **SQL**- Structured Query Language for querying of data

- **PowerBi**- interactive data visualisation of the dataset analysis

- **Github** - Portfolio building
  
### Data Structure
**Sales Performance of Retail Store**
- Order Id
- Customer Id
- Product
- Region
- Order Date
- Order Month
- Quantity
- Unit Price
- Total Sales

### Customer Segmentation for a Subscription Service 
- Customer Id
- Customer Name
- Region
- Subscription Type
- Subscription Start
- Suscription End
- Subscription Duration
- Cancelled
- Revenue

### Steps In Data Cleaning
- Download the dataset provided by LITA
- Check for null and duplicate values to be removed
- Standardise data formats for numbers and text

## Process of Data Analysis    

### Microsoft Data Analysis
- Highlight the Sales performance retail data to insert Pivot Table
- Click "From Table/Range"
- Click Existing woorksheet, then click okay
- Repeat same process on the Customer Segmentation for a subscription Service Data

### PowerBI
- Click on Get data to upload the data from MIcrosoft Excel.
- Once the data is uploaded, tick Sales and Customer data and click transform data
- Under the Power query editor, click on the view then tick column quality to check on the data quality
- Checkk the order date to ensure it correlates and if not, change to date format
- Create a new column and name it Order Month
- Change the date to month using the DAX formula Month Name = FORMAT(SalesData[OrderDate], "MMMM")
- The visualisation is initiated from the report view

### SQL

1. Use LITA;

-   select * from [dbo].[SalesData]

- Retrieve the total sales for each product category.
- select Product As ProductCategory, sum(salesamount) As TotalSales
from [dbo].[SalesData]
group by Product;

- Find the number of sales transactions in each region.
select Region, COUNT(OrderID) As NumberOfSales_Transactions
from [dbo].[SalesData]
Group By Region;


- Find the highest-selling product by total sales value.
select top 1 Product, sum(salesamount) As SalesValue
from [dbo].[SalesData]
group by Product
order by SalesValue desc

- Calculate total revenue per product.
select Product, sum(salesamount) As TotalRevenue
from [dbo].[SalesData]
group by Product;

- Calculate monthly sales totals for the current year.
select month(orderdate) Months, sum(salesamount) As Sales
from [dbo].[SalesData]
where YEAR(orderdate) = '2024'
group by month(orderdate)
order by month(orderdate);

-    Find the top 5 customers by total purchase amount.
select top 5 CustomerName, sum(Revenue) As Total_Purchase_Amount
from [dbo].[CustomerData]
group by CustomerName
order by sum(Revenue) desc

----Calculate the percentage of total sales contributed by each region.
select Region, concat(round(sum(salesamount)*100/(select sum(salesamount)
from [dbo].[SalesData]), 0), '%') As PercentageOfTotalSales

from [dbo].[SalesData]
group by region

----Identify products with no sales in the last quarter.
select product
from [dbo].[SalesData]
where SalesAmount is null and orderdate in (01/10/2024, 31/12/2024)


