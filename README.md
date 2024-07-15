# Restaurant-Data-Analysis-Using-SQL
This repository contains SQL queries for analyzing the restaurant dataset. The dataset contains 7000 transaction records from a restaurant, including details such as dates, invoice numbers, item names, prices, quantities, total amount, discounts, taxes, table numbers, server names, and categories.
The purpose of this repository is to demonstrate SQL queries for typical data analysis tasks using the restaurant dataset. These queries cover basic SQL operations, filtering, aggregation, and advanced querying techniques such as subqueries and ordering.

# Dataset Description
- **Table Name:** restaurant
- **Columns:**
  - `Dates` (Date)
  - `Invoice_no` (Invoice Number)
  - `ITEM_Name ` (Item Name)
  - `PRICE` (Price)
  - `QUANTITY ` (Quantity)
  - `SUB_TOTAL ` (Sub Total)
  - `Discount ` (Discount)
  - `Tax ` (Tax)
  - `Final_Total ` (Total Amount)
  - `Table_NUMBER ` (Table Number)
  - `SERVER_NAME` (Server Name)
  - `CATEGORY` (Category)

## Queries

### Basic Operations

1. **Creating Table:**
   ```sql
   CREATE TABLE RESTAURANT(
	  Dates DATE,
	  INVOICE_NO NUMERIC(100),
	  ITEM_Name VARCHAR(1000),
	  PRICE FLOAT,
	  QUANTITY VARCHAR(1000),
	  SUB_TOTAL FLOAT(50),
	  Discount FLOAT(50),
	  Tax FLOAT(50),
	  Final_Total FLOAT(50),
	  Table_NUMBER VARCHAR(100),
	  SERVER_NAME VARCHAR(20),
	  CATEGORY VARCHAR(50)
   );
   ```
2. **Selecting All Data**
	```sql
 	SELECT * FROM restaurant;
 	```

3. **Items ordered on 21-07-2023**
 
     ```sql
      SELECT * FROM restaurant WHERE Dates ='2023-07-21';
     ```
4. **Customers ordered Chicken Biriyani With Raitha And Gravy**
     ```sql
     SELECT * FROM restaurant 
     WHERE item_name ='Chicken Biriyani With Raitha And Gravy';
     ```
5. **Invoice no. and Total amount**
   ```sql
   SELECT invoice_no,SUM(final_total) FROM restaurant 
   GROUP BY invoice_no;
   ```
6. **Invoice no., Total amount and Item name**
   ```sql
   SELECT invoice_no,SUM(final_total),STRING_AGG(ITEM_Name, ', ') AS aggregated_item_names FROM restaurant 
   GROUP BY invoice_no;
   ```
7. **Invoice no., Total amount, Date and Item name**
   ```sql
   SELECT invoice_no,SUM(final_total),MIN(Dates) AS agg_date,
   STRING_AGG(ITEM_Name, ', ') AS aggregated_item_names FROM restaurant 
   GROUP BY invoice_no;
   ```
8. **Invoice no. with highest Total Amount**
   ```sql
   SELECT invoice_no,SUM(final_total) AS ft FROM restaurant 
   GROUP BY invoice_no 
   ORDER BY ft DESC
   LIMIT 1;
   ```
