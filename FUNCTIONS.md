# Functions

### **Function Name**: `isTheUserRegistered`

**Purpose**: This function checks the registration status of a user based on their email.

**Description**:
- The function accepts an email address (`p_email`) as its parameter.
- It queries the `customer` table to fetch the value of the `Is_registered` column for the provided email address.
- Based on the value of `Is_registered`, the function returns:
  - `-1` if there's no record found for the email, indicating the user is a new guest.
  - `0` if the user has previously made a purchase as a guest.
  - `1` if the user is a registered customer.

**Example:**
```sql
-- Check if the user with the email "john.doe@example.com" is registered
SELECT isTheUserRegistered('john.doe@example.com') AS is_registered;
```

**Output:**

```
is_registered
-------------
1
```


### **Function Name**: `GetMinPrice`

**Purpose**: This function retrieves the minimum price of a specific product based on its product ID.

**Description**:
- The function takes a `product_id` (`p_product_id`) as its parameter.
- It then queries the `item` table to find the minimum (lowest) price for all items associated with the given product ID.
- The function returns the minimum price as a decimal value with a precision of 9 digits and a scale of 2 (allowing for currency-style values).
  

**Example:**

```sql
-- Get the minimum price of the product with the ID 1
SELECT GetMinPrice(1) AS min_price;
```

**Output:**

```
min_price
---------
100.00
```

### **Function Name**: `CalculateDeliveryDays`

**Purpose**: This function calculates the estimated number of delivery days for a customer based on the customer's city and the stock availability of items in their cart.

**Description**:
- The function accepts two parameters:
  - `p_customer_id` (`INT`): The ID of the customer.
  - `p_city` (`VARCHAR(255)`): The city to which the delivery is being made.
  
- The function queries the `cart` table to identify the cart associated with the given customer ID.
- It then checks the `cart_item` and `item` tables to determine if there are any items in the cart that are out of stock.
- Based on the stock availability and delivery city, the function calculates the delivery days as per the following conditions:
  1. If all items are in stock and the delivery is to a main city (e.g., Colombo), the estimated delivery time is 5 days.
  2. If all items are in stock but the delivery is to a non-main city (e.g., Negombo), the estimated delivery time is 7 days.
  3. If any item is out of stock, an additional 3 days are added to the delivery estimates from the previous two points.
  
- The main cities considered in this function are: 'Anuradhapura', 'Colombo', 'Jaffna', 'Kandy', 'Galle', and 'Sri Jayewardenepura Kotte'.
- The function returns the estimated delivery days as an integer value.

**Example:**

```sql
-- Calculate the delivery days for a customer with ID 2 delivering to Colombo
SELECT CalculateDeliveryDays(2, 'Colombo') AS delivery_days;
```

**Output:**

```
delivery_days
-------------
5
```

Note: The above output suggests that the customer with ID 2, delivering to Colombo, will receive their items in 5 days, given that all items are in stock. If any item were out of stock, this would be increased to 8 days.