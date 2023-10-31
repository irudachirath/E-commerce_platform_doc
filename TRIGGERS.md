# Triggers

### Purpose of each trigger:

* `order_item_after_insert`: Updates the quantity of the item after an order is placed and deletes the item from the cart table.
* `after_customer_update`: Creates a cart for the customer when an unregistered user registers as a customer.
* `after_customer_insert`: Creates a cart for a customer when the customer is registered.