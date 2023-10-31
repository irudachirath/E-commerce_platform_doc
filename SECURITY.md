# Security

1. **Password Encryption**:
   - **Salt Rounds**: For additional security, our encryption process incorporates salting, a method where random data is combined with the password. We've set the salt rounds to `10`, but this can be adjusted as per requirements to determine the complexity of the hashing operation.

   - **Hashing Process**: When a user sets or updates their password, it's transformed from plain-text into a cryptographic hash. We utilize the bcrypt algorithm, one of the most trusted methods in the industry. This ensures that the actual password is never stored directly in our database.

    ![alt text](https://github.com/irudachirath/E-commerce_platform_doc/blob/main/hash_password.png?raw=true)

2. **Password Verification**:
   - When a user logs in, their inputted password is compared with the stored hash in our database.
   - The bcrypt's `compare` function is used for this verification. It checks if the hashed version of the inputted password matches the stored hash without ever converting the hash back to plain-text. This ensures a secure and efficient login process.

   ![alt text](https://github.com/irudachirath/E-commerce_platform_doc/blob/main/compare_password.png?raw=true)


3. **SQL Injection Prevention using Prepared Statements**

    SQL Injection is one of the most prevalent and dangerous web application vulnerabilities. It allows attackers to insert malicious SQL code into queries, which can then be executed by the database.

    In our e-commerce platform, we're proactive in guarding against SQL Injection attacks by utilizing prepared statements in our SQL queries. Here's how prepared statements offer enhanced security:

    i. **Parameterized Queries**:
    - In our SQL queries, we use placeholders (`?`) instead of directly inserting values into the SQL string. This ensures that the database always treats the inputs as data rather than executable code.
    
    ii. **Separation of SQL Logic and Data**:
    - With prepared statements, SQL logic is defined first and kept separate from the data. When data is later bound to the placeholders, the database knows to treat it only as data and not part of the SQL logic. This makes it virtually impossible for an attacker to inject malicious SQL.

    For instance, consider the following SQL statements from our platform:

    ![alt text](https://github.com/irudachirath/E-commerce_platform_doc/blob/main/prepared_statements.png?raw=true)

    In both cases, any input provided by the user (or an attacker) will be treated strictly as data, eliminating the risk of SQL code execution.

    By consistently using prepared statements throughout our platform, we ensure that our database interactions remain secure, and our users' data is protected from potential injection threats.