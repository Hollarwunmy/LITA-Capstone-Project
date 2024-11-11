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

