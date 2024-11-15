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

- Find the top 5 customers by total purchase amount.
select top 5 CustomerName, sum(Revenue) As Total_Purchase_Amount
from [dbo].[CustomerData]
group by CustomerName
order by sum(Revenue) desc

- Calculate the percentage of total sales contributed by each region.
select Region, concat(round(sum(salesamount)*100/(select sum(salesamount)
from [dbo].[SalesData]), 0), '%') As PercentageOfTotalSales

- from [dbo].[SalesData]
group by region

- Identify products with no sales in the last quarter.
select product
from [dbo].[SalesData]
where SalesAmount is null and orderdate in (01/10/2024, 31/12/2024)

### Pivot Chart Analysis of Sales Performance of Retail Store

![image](https://github.com/user-attachments/assets/bb126cef-3443-45d4-9d98-a5c0ce018bd9)
- The bar chart shows total sales across four regions with the South leading at nearly 5million, followed by the East, North, and West. The South strong performance indicates it may have higher demand or more effective sales strategies compared to other regions.

![image](https://github.com/user-attachments/assets/407b0cd4-072b-4912-8f40-f7f7f4c3217d)
- The line chart shows monthly revenue trends, with a peak in February near 3million, followed by a sharo drop in March and relatively lower flluctuations for the rest of the year. The data suggests strong revenue early in the year, with a more stable but lower revenue pattern across subsequent months.

![image](https://github.com/user-attachments/assets/443854e9-619b-4aa2-bd7d-0c911656549c)
- The bar chart displays total sales for 2023 and 2024 while 2023 shows alomst 5.5 million and 2024 declining to about 5 million. This stats indicates a significant drop in sales from 2023 to 2024.

![image](https://github.com/user-attachments/assets/1a81f230-a971-4001-aef8-f8fb9a71bbc1)
- The chart shows average sales of different clothing products. Shoes have the highest average sales with 326.7 units, followed by Shirts with 308.8 units.






