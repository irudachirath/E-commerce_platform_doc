# Security

1. **Password Encryption**:
   - **Salt Rounds**: For additional security, our encryption process incorporates salting, a method where random data is combined with the password. We've set the salt rounds to `10`, but this can be adjusted as per requirements to determine the complexity of the hashing operation.

   - **Hashing Process**: When a user sets or updates their password, it's transformed from plain-text into a cryptographic hash. We utilize the bcrypt algorithm, one of the most trusted methods in the industry. This ensures that the actual password is never stored directly in our database.

![alt text](https://github.com/irudachirath/E-commerce_platform_doc/blob/main/hash_password.png?raw=true)

2. **Password Verification**:
   - When a user logs in, their inputted password is compared with the stored hash in our database.
   - The bcrypt's `compare` function is used for this verification. It checks if the hashed version of the inputted password matches the stored hash without ever converting the hash back to plain-text. This ensures a secure and efficient login process.

   ![alt text](https://github.com/irudachirath/E-commerce_platform_doc/blob/main/compare_password.png?raw=true)