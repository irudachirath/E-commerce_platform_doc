# Procedures for generating admin reports

A set of procedures that can be used to generate admin reports for a given year, quarter, product category, product, or customer.

### Purpose of each procedure:

* `set_quarter_dates`: Sets the start and end dates of a quarter, given the year and quarter.
* `get_sales_quantity`: Gets the sales quantity for all products, or for a given product category or product, for a given year and quarter.
* `get_sales_of_a_category`: Gets the sales quantity for all products in a given product category, for a given year and quarter.
* `get_sales_of_a_product`: Gets the sales quantity for a given product, for a given year and quarter.
* `get_orders_quantity`: Gets the number of orders placed for a given year and quarter.
* `get_most_sellings`: Gets the top selling products for a given year, quarter, and number of products.
* `get_order_report`: Gets the order details for a given customer, given the customer ID.
* `get_most_popular_time_for_product`: Gets the most popular time of year for a given product.

### Example queries:

Get the sales quantity for all products for the year 2023 and quarter 1
```sql
CALL get_sales_quantity(2023, 1);
```

Get the sales quantity for all products in the category 1 for the year 2023 and quarter 1
```sql
CALL get_sales_of_a_category(1, 2023, 1);
```
Get the sales quantity for the product with ID 1 for the year 2023 and quarter 1
```sql
CALL get_sales_of_a_product(1, 2023, 1);
```
Get the number of orders placed in the year 2023 and quarter 1
```sql
CALL get_orders_quantity(2023, 1);
```
Get the top 10 selling products for the year 2023 and quarter 1
```sql
CALL get_most_sellings(2023, 1, 10);
```
Get the order details for the customer with ID 1
```sql
CALL get_order_report(1);
```
Get the most popular time of year for the product with ID 1
```sql
CALL get_most_popular_time_for_product(1);