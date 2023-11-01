# Database Design

### Consistency and Avoiding Redundancy:

1. **Unique Constraints**: 
    - Ensures unique data for specific columns, thereby preventing redundancy. For instance, `Admin_username` in the `admin` table and `Email` in the `customer` table have been made UNIQUE to prevent duplicate entries.

2. **Primary Keys**: 
    - Each table has a primary key, ensuring a unique identifier for each row, which in turn maintains consistency.

3. **Foreign Key Constraints**: 
    - Establishes a link between data in two tables, ensuring consistency across tables. 
    E.g: the `Variant_id` in the `attribute` table is a Foreign Key referring to the `variant` table. 

4. **CASCADE Options**: 
    - In the event of an update or delete operation, the CASCADE option ensures that changes are consistently reflected across related tables. This prevents orphan records and maintains database integrity.

### Normalizations and Improvements:

1. **First Normal Form (1NF)**:
    - Each table has a primary key, and there are no repeating groups or arrays. All attributes have atomic values.

2. **Second Normal Form (2NF)**:
    - Tables like `cart_item` and `order_item` have composite primary keys (`Cart_id` with `Item_id`, `Order_id` with `Item_id`). This decomposition ensures that every non-prime attribute is fully functionally dependent on the primary key.

3. **Third Normal Form (3NF)**:
    - Transitive dependencies are removed. For instance, the `category` table has a `Parent_Category_id` that points back to the same table, creating a hierarchical structure. Thus, by using a self-referencing foreign key, we ensure that the table is in 3NF by eliminating possible transitive dependencies.

4. **Modularity of Tables**:
    - The database is designed such that entities like customers, orders, items, carts, and attributes are in separate tables. This modular design makes the database scalable and easy to manage.

5. **Integrity Checks**:
    - Constraints like `CHECK (LENGTH(Card_number) = 16)` for card number length and `CHECK (Price >= 0)` for item price ensure data integrity by enforcing business rules.

6. **Hierarchical Data**:
    - The `category` table uses a self-referencing foreign key (`Parent_Category_id`) to establish a category hierarchy, allowing for nested categories in the e-commerce platform.

7. **Storing Images Using Firebase**:

    - When dealing with images especially in databases for e-commerce platforms where large volumes of images might be stored, it's often a best practice to avoid saving the images directly within the relational database. Because relational database storage can be more expensive compared to specialized storage solutions designed for multimedia content. Therefore we use Firebase to store images and store only the link to the image in the database. 