ID: TC_REG_01
* **Title:** Successful registration with valid data
* **Preconditions:** The registration page is open. The email address is not registered yet.
* **Steps:**
  1. Enter a valid username into the "Username" field.
  2. Enter a valid email address into the "Email" field.
  3. Enter a valid password (8+ characters) into the "Password" field.
  4. Enter the identical password into the "Confirm password" field.
  5. Click the "Register" button.
* **Test data:** Username: AlexQA, Email: alex.qa+test@example.com, Password: SecretPass123, Confirm password: SecretPass123
* **Expected result:** A new user account is successfully created. User is redirected to the Dashboard.
* **Priority:** Critical
---
ID: TC_REG_02
* **Title:** Registration with a too short Username
* **Preconditions:** The registration page is open.
* **Steps:**
  1. Enter a 2-character name into the "Username" field.
  2. Fill in all other fields with valid data.
  3. Click the "Register" button.
* **Test data:** Username: Al, Email: alex.qa+test@example.com, Password: SecretPass123, Confirm password: SecretPass123
* **Expected result:** Registration is blocked. A validation error appears: "Username must be between 3 and 15 characters".
* **Priority:** High
---
ID: TC_REG_03
* **Title:** Registration with an invalid Email format
* **Preconditions:** The registration page is open.
* **Steps:**
  1. Enter text without the "@" symbol into the "Email" field.
  2. Fill in all other fields with valid data.
  3. Click the "Register" button.
* **Test data:** Username: AlexQA, Email: alex_example.com, Password: SecretPass123, Confirm password: SecretPass123
* **Expected result:** The form is not submitted. A validation message appears: "Please enter a valid email address".
* **Priority:** High
---
ID: TC_REG_04
* **Title:** Registration with a password shorter than 8 characters
* **Preconditions:** The registration page is open.
* **Steps:**
  1. Enter a 7-character password into the "Password" field.
  2. Enter the same 7-character password into the "Confirm password" field.
  3. Fill in all other fields with valid data.
  4. Click the "Register" button.
* **Test data:** Username: AlexQA, Email: alex.qa+test@example.com, Password: Short12, Confirm password: Short12
* **Expected result:** Form submission fails. An error message appears: "Password must be at least 8 characters long".
* **Priority:** High
---
ID: TC_REG_05
* **Title:** Registration with mismatched passwords
* **Preconditions:** The registration page is open.
* **Steps:**
  1. Enter a valid password into the "Password" field.
  2. Enter a different password into the "Confirm password" field.
  3. Fill in all other fields with valid data.
  4. Click the "Register" button.
* **Test data:** Username: AlexQA, Email: alex.qa+test@example.com, Password: SecretPass123, Confirm password: DifferentPass456
* **Expected result:** Registration is rejected. A validation error appears: "Passwords do not match".
* **Priority:** High
---
ID: TC_REG_06
* **Title:** Register button state check with empty fields
* **Preconditions:** The registration page is open. All input fields are empty.
* **Steps:**
  1. Verify the visual state and clickability of the "Register" button.
* **Test data:** None.
* **Expected result:** The "Register" button is disabled (or does not trigger any action) until all required fields are filled properly.
* **Priority:** Medium
---

ID: TC_REG_07
* **Title:** Registration with an already registered Email address
* **Preconditions:** A user with the email "alex.qa@example.com" is already registered in the system. The registration page is open.
* **Steps:**
  1. Enter a valid username into the "Username" field.
  2. Enter the already existing email address "alex.qa@example.com" into the "Email" field.
  3. Enter a valid password and confirm it.
  4. Click the "Register" button.
* **Test data:** Username: AlexQA, Email: alex.qa@example.com, Password: SecretPass123, Confirm password: SecretPass123
* **Expected result:** Registration fails. An error message appears under the Email field: "This email address is already registered".
* **Priority:** High
---
ID: TC_REG_08
* **Title:** Boundary value check for Username length (Maximum limit - 15 characters)
* **Preconditions:** The registration page is open. The email address is not registered yet.
* **Steps:**
  1. Enter a username that is exactly 15 characters long into the "Username" field.
  2. Fill in all other fields with valid data.
  3. Click the "Register" button.
* **Test data:** Username: UserThirteen15X, Email: alex.qa+15@example.com, Password: SecretPass123, Confirm password: SecretPass123
* **Expected result:** Registration is successful. The system correctly accepts a username at the exact maximum length boundary.
* **Priority:** Medium
---
ID: TC_REG_09
* **Title:** Boundary value check for Username length (Exceeding limit - 16 characters)
* **Preconditions:** The registration page is open.
* **Steps:**
  1. Enter a username that is 16 characters long into the "Username" field.
  2. Fill in all other fields with valid data.
  3. Click the "Register" button.
* **Test data:** Username: UserFourteen16XX, Email: alex.qa+16@example.com, Password: SecretPass123, Confirm password: SecretPass123
* **Expected result:** Registration is blocked. A validation error appears below the field: "Username must be between 3 and 15 characters".
* **Priority:** High
---
ID: TC_REG_10
* **Title:** Automatic trimming of leading and trailing spaces in fields
* **Preconditions:** The registration page is open. The email address is not registered yet.
* **Steps:**
  1. Enter a valid username with accidental spaces at the beginning and the end into the "Username" field.
  2. Enter a valid email address with a space at the end into the "Email" field.
  3. Fill in the password fields with valid data.
  4. Click the "Register" button.
* **Test data:** Username: "  AlexQA  ", Email: "alex.qa+trim@example.com ", Password: SecretPass123, Confirm password: SecretPass123
* **Expected result:** Registration is successful. The system automatically clips (trims) the spaces. In the database, the account is saved cleanly as "AlexQA" and "alex.qa+trim@example.com".
* **Priority:** Medium

