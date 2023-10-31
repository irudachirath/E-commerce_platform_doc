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

### **Function Name**: `GetDeliveryDays`

**Purpose**: This function retrieves the number of days required to deliver to a specified city.

**Description**:
- The function takes a city name (`p_city`) as its parameter.
- It checks whether the provided city is one of the main cities.
- If the city is among the main cities, then the delivery days are set to 5.
- If the city is not in the main cities list, the delivery days are set to 7.
- The function returns the number of delivery days as an integer.

**Example:**

```sql
-- Get the delivery days for the city 'Galle'
SELECT GetDeliveryDays('Galle') AS delivery_days;
```

**Output:**

```
delivery_days
-------------
5
```