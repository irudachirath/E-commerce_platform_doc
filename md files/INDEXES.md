# Indexes

### **Index Name**: `idx_date`

The `idx_date` index on the `shop_order` table's `Date` column improves query performance by allowing the database to quickly locate and access rows based on date values, rather than scanning the entire table.

### Before creating the index:

![alt text](https://github.com/irudachirath/E-commerce_platform_doc/blob/main/before_index.png?raw=true)

### After creating the index:

![alt text](https://github.com/irudachirath/E-commerce_platform_doc/blob/main/after_index.png?raw=true)


| Parameter          | Before Indexing   | After Indexing    | Reason for Difference                                    |
|--------------------|-------------------|-------------------|----------------------------------------------------------|
| **Index Type**     | ALL (Full Scan)   | Range             | The new index allows the DB to perform a range scan, which is more efficient than a full table scan for date-based queries. |
| **Rows Scanned**   | 24                | 6                 | With the new index, the DB can directly access the relevant rows without scanning the entire table. |
| **Key Used**       | NULL              | idx_date          | Before, no specific index was used for the date-based query. After indexing, the `idx_date` index is leveraged to optimize the query. |

### **Index Name**: `idx_Title_Description`

The `idx_Title_Description` index is a full-text index specifically designed for the `Title` and `Description` columns of the `product` table.

When users interact with an e-commerce platform, one of the primary actions they undertake is searching for products. The `idx_Title_Description` index serves this very purpose. By indexing the `Title` and `Description` columns, the system can adeptly match user queries against product titles and descriptions without having to scan each row individually.

**Example:**

Suppose a user wants to find products related to "organic tea". Using the full-text index, the query would look something like this:
```sql
SELECT *
FROM product 
WHERE MATCH(Title, Description) AGAINST('organic tea');
```
With the `idx_Title_Description` index, this query would promptly return all products with titles or descriptions that mention "organic tea" or are contextually relevant to it.