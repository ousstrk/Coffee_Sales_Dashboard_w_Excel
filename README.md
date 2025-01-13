Excel Sales Dashboard Project

This project involves creating a consolidated dataset from orders, customers, and products tables, applying data transformations such as merging, formatting, and calculated fields. The dashboard includes:
- A line chart for sales trends by coffee type.
- A bar chart for total sales by country.
- A top 5 customers chart.
Interactive features like date filters and slicers (coffee type, size, loyalty card) enhance user analysis. Perfect for tracking and visualizing sales data efficiently!

Data Formatting Process

1. Combining Sheets: 
  The dataset includes three sheets:
    Orders: Contains order information.
    Customers: Contains customer details.
    Products: Contains product specifications.
I merged the data into the Orders sheet as much as possible to keep everything consolidated.

2. Adding Customer Information:
Using the XLOOKUP formula, I pulled the following columns from the Customers sheet: Customer Name, Email, Country
The formula sample: =XLOOKUP(C2,customers!$A$1:$A$1001,customers!$B$1:$B$1001,,0)

3. Adding Product Information:
Using the INDEX function, I retrieved the following columns from the Products sheet: Coffee Type, Roast Type, Size, Unit Price
The formula sample: =INDEX(products!$A$1:$G$49,MATCH(orders!$D2,products!$A$1:$A$49,0),MATCH(orders!I$1,products!$A$1:$G$1,0))

4. Calculating Sales:
I calculated the Sales column in the Orders sheet with multiplying values of Unit Price and Quantity Column:

5. Expanding Abbreviations:
The Coffee Type and Roast Type columns had abbreviations that I found inconvenient.
Using the IF formula, I replaced the abbreviations with their full names.
The formula sample: =IF(I2="Rob","Robusta",IF(I2="Exc","Excelsa",IF(I2="Ara","Arabica",IF(I2="Lib","Liberica",""))))

6. Standardizing the Date Format:
Since date formats differ between the US and Europe, I unified the date format to: DD-MMM-YYYY (e.g., 13-Jan-2025) to avoid confusion.

7. Adjusting Size Format: 
The Size column originally displayed values as [0.5, 1, 2.5]. I converted these to a more descriptive format: [0.5 kg, 1.0 kg, 2.5 kg].

8. Formatting Currency:
I converted the Unit Price and Sales columns from numbers to a currency format.

9. Removing Duplicates:
I used the Remove Duplicates feature to eliminate duplicate rows from the dataset. Fortunately, there were no duplicates!

10. Making Table from Orders sheet:
Finally, I converted the Orders sheet into a table, ensuring that any new data added will automatically update the dashboard dynamically.

Dashboard Design:
A line chart showing the total sales over time, grouped by Coffee Type.
One vertical bar graph displaying total sales amounts by Country.
Another vertical bar graph highlighting the Top 5 Customers based on sales.

Filters and Slicers:
Added a date filter to allow users to select specific time ranges.
Added slicers for the following columns to filter data: Coffee Type, Size, Loyalty Card


![image](https://github.com/user-attachments/assets/ba51950c-c795-4cd8-977f-940b8578b4e3)

