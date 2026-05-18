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
