# Transactions

* `add_product`:

    - **Transaction Usage**: This procedure also starts a transaction at the beginning and commits it at the end. The goal here is to ensure that the insertion of a new product and its association with categories are treated as a single atomic operation.

* `add_item`:

    - **Transaction Usage**: This procedure starts a transaction at the beginning and commits it at the end. The idea is to ensure that all operations related to adding an item, such as fetching the Product_id, inserting the item, adding variants and attributes, and linking the item to its configurations, are treated as one atomic operation.