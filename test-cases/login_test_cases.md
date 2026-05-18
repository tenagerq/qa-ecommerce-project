ID: TC_LF_01
* **Title:** Successful login with valid credentials
* **Preconditions:** User is registered. Login page is open.
* **Steps:**
  1. Enter valid email into the "Email" field.
  2. Enter valid password into the "Password" field.
  3. Click the "Login" button.
* **Test data:** Email: user@example.com, Password: ValidPassword123
* **Expected result:** User is authorized and redirected to the Dashboard.
* **Priority:** High
---
ID: TC_LF_02
* **Title:** Login with invalid Email format
* **Preconditions:** Login page is open.
* **Steps:**
  1. Enter email without domain part into the "Email" field.
  2. Enter any password into the "Password" field.
  3. Click the "Login" button.
* **Test data:** Email: invalid_email.com, Password: ValidPassword123
* **Expected result:** Form is not submitted. Error message appears: "Enter a valid email".
* **Priority:** High
---
ID: TC_LF_03
* **Title:** Login with empty fields
* **Preconditions:** Login page is open.
* **Steps:**
  1. Leave "Email" and "Password" fields empty.
  2. Click the "Login" button.
* **Test data:** None.
* **Expected result:** Form is not submitted. "This field is required" error appears near both fields.
* **Priority:** High
---
ID: TC_LF_04
* **Title:** Login with invalid password
* **Preconditions:** User is registered. Login page is open.
* **Steps:**
  1. Enter valid email into the "Email" field.
  2. Enter incorrect password into the "Password" field.
  3. Click the "Login" button.
* **Test data:** Email: user@example.com, Password: WrongPassword777
* **Expected result:** Login denied. Security error appears: "Invalid email or password".
* **Priority:** High
---
ID: TC_LF_05
* **Title:** Login button state check with empty fields
* **Preconditions:** Login page is open. Input fields are empty.
* **Steps:**
  1. Check the visual state and clickability of the "Login" button.
* **Test data:** None.
* **Expected result:** "Login" button is disabled and does not respond to clicks.
* **Priority:** Medium
---
ID: TC_LF_06
* **Title:** Login using Enter key on the keyboard
* **Preconditions:** User is registered. Login page is open.
* **Steps:**
  1. Enter valid email into the "Email" field.
  2. Enter valid password into the "Password" field.
  3. Press the "Enter" key on the keyboard.
* **Test data:** Email: user@example.com, Password: ValidPassword123
* **Expected result:** The form is successfully submitted. User is authorized and redirected to the Dashboard.
* **Priority:** High
---
ID: TC_LF_07
* **Title:** Password visibility toggle (Eye icon check)
* **Preconditions:** Login page is open.
* **Steps:**
  1. Enter any text into the "Password" field and verify that characters are masked.
  2. Click the "Eye" icon inside the password field.
  3. Verify that characters become visible.
  4. Click the "Eye" icon again.
* **Test data:** Password: SecretPassword123
* **Expected result:** Initially, the password is hidden (displayed as dots •••••). After step 2, the text is visible. After step 4, the text becomes hidden again.
* **Priority:** Medium
---
ID: TC_LF_08
* **Title:** Case insensitivity for Email input
* **Preconditions:** User is registered with the email "user@example.com". Login page is open.
* **Steps:**
  1. Enter the registered email using uppercase letters into the "Email" field.
  2. Enter valid password into the "Password" field.
  3. Click the "Login" button.
* **Test data:** Email: USER@EXAMPLE.COM, Password: ValidPassword123
* **Expected result:** User is successfully authorized and redirected to the Dashboard. (Email verification should ignore capital letters).
* **Priority:** High
---
ID: TC_LF_09
* **Title:** Account lockout after multiple failed login attempts
* **Preconditions:** User is registered. Login page is open.
* **Steps:**
  1. Enter valid email and an incorrect password. Click "Login".
  2. Repeat step 1 five times in a row.
* **Test data:** Email: user@example.com, Password: WrongPassword777
* **Expected result:** After the 5th failed attempt, the account is temporarily locked. A security message appears: "Too many failed attempts. Account locked for 15 minutes."
* **Priority:** High
