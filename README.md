# Banking Application

## Overview
This project is a secure banking application implemented in Java, designed with client-server architecture to simulate ATM operations. The application supports user authentication, money transfers, and balance inquiries with robust encryption and file-based data persistence.

## Features
1. **User Authentication:**
   - RSA (2048-bit) and AES (256-bit) encryption for secure communication.
   - Encrypted credential transmission with server-side validation.

2. **ATM Operations:**
   - **Money Transfer:** Transfer funds between user accounts with recipient ID validation and balance updates.
   - **Balance Inquiry:** Check savings and current account balances.

3. **Data Security:**
   - Public and private keys for secure data exchange.
   - Symmetric key encryption for session-level security.

4. **Data Persistence:**
   - User balances stored and updated in `balance.txt`.
   - Passwords securely stored in `password.txt`.

5. **Scalability:**
   - Supports multiple user connections with efficient socket management.

## Files
1. **`ATM.java`:** The client-side application simulating ATM operations.
2. **`BankServer.java`:** The server-side application handling authentication and account operations.
3. **`balance.txt`:** Contains user account details in the format:
   ```
   username savings_balance current_balance
   ```
   Example:
   ```
   joe 10000.0 1000.0
   chris 9700.0 700.0
   ```

4. **`password.txt`:** Contains user credentials in the format:
   ```
   username password
   ```
   Example:
   ```
   joe 9012
   chris 1234
   ```

## How to Run
1. **Setup Keys:**
   - Place `public_key.pem` and `private_key.pem` in the project directory for RSA encryption.

2. **Start the Server:**
   - Compile and run `BankServer.java`.
   - The server listens for client connections on port `12345`.

3. **Run the Client:**
   - Compile and run `ATM.java`.
   - The client connects to the server and provides a menu for operations.

4. **Add User Accounts:**
   - Update `balance.txt` and `password.txt` with user details.

## Usage
- **Login:**
  - Provide a valid user ID and password.
- **Operations:**
  - Transfer funds to other users.
  - Check account balances for savings and current accounts.
- **Exit:**
  - Safely terminate the session.

## Notes
- Ensure that `balance.txt` and `password.txt` are consistent with user details.
- The system supports up to 300 users with preloaded account and password files.

## Example
**Sample Input:**
```
Enter ID: joe
Enter Password: 9012
```

**Sample Output:**
```
Login successful!
1. Transfer money
2. Check account balance
3. Exit
Please select one of the above options: 2
Your savings account balance: 10000.0
Your checking account balance: 1000.0
```

## Future Enhancements
- Add support for database integration for better scalability.
- Implement advanced security features like OTP-based transactions.
- Extend functionalities to include account creation and transaction history.
