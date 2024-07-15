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
