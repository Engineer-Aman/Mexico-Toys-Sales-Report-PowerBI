# Mexico-Toys-Sales-Report-PowerBI
:wave: All in below video you can see the mexico toys sales analysis report.:point_down:



https://github.com/Engineer-Aman/Mexico-Toys-Sales-Report-PowerBI/assets/126685886/69d4c230-41eb-46bc-87fe-1240dcf13187


## Business Requirement :- 
### 1.	Profit By Product – Bar Graph (Top 10 Products Only)
### 2.	Profit By Store – Bar Graph (Top 10 only)
### 3.	Sales By Year Quarter – Line Chart
### 4.	Sales By Store Location Over Time – Line Chart.



## KPI’s(Cards):-
      1.Sales 
      2.Coast
      



## Data Source:-

  https://www.mavenanalytics.io/data-pl...





## Basic Data transformation Check:-

### -	Change Data Types
### -	Promote Rows To Header If Required
### -	Replace Null With 0 or NA
### -	Add Custom Columns If Required


## Data Modeling :- 
### 1.	Add Date Master Table 
### 2.	Create Date Hierarchy
### 3.	Star Schema
### 4.	Cardinality (1-*/*-1 )Relationship



## Create Calculated Column:-
 ### 1. Sales = RELATED(products[Product_Price])*sales[Units] 
 ### 2. Cost = RELATED(products[Product_Cost])*sales[Units] 
 ### 3. Profit = RELATED(products[Profit Per Product])*sales[Units]
 ### 4. Profit Per Product = products[Product_Price]-products[Product_Cost]

## Create Table:-
Date Table = 
VAR StartDate=MIN(sales[Date])
VAR EndDate=MAX(sales[Date])
VAR Date_Table=
ADDCOLUMNS(
     CALENDAR(StartDate,EndDate),
     "Year",YEAR([Date]),
     "QuarterNo",QUARTER([Date]),
     "QuarterName",FORMAT([Date],"\QQ"),
     "MonthName",FORMAT([Date],"MMM"),
     "MonthNo",MONTH([Date])

)
RETURN Date_Table


	


