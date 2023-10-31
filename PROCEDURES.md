# Procedures for product management

A set of procedures that can be used to manage products, variants, and attributes.

### Purpose of each procedure:

* `insert_variant_if_not_exists`: Inserts a given variant name into the variant table if it does not exist.
* `insert_attribute_if_not_exists`: Inserts a given attribute name into the attribute table if it does not exist for the given variant.
* `add_item`: Adds a new item to the item table, with the given product ID, price, quantity, image, variant types, and attribute names.
* `add_product`: Adds a new product to the product table, with the given title, category list, description, weight, SKU, and image.

### Example queries:

Insert a new variant named "Size" into the variant table if it does not exist
```sql
CALL insert_variant_if_not_exists('Size');
```
Insert a new attribute named "Color" into the attribute table for the "Size" variant, if it does not exist
```sql
CALL insert_attribute_if_not_exists('Color', 'Size');
```

Add a new item to the item table
```sql
CALL add_item(1, 100.00, 10, 'product.jpg', 2, 'Size,Color', 'Red,Blue');
```

Add a new product to the product table
```sql
CALL add_product('T-Shirt', 'Clothing,Tops', 'A comfortable and stylish t-shirt.', 0.5, 'T-Shirt-1', 't-shirt.jpg');
```

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