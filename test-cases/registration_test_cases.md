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
