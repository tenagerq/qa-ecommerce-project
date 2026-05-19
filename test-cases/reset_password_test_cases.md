ID: TC_RP_01
* **Title:** Successful password reset request for a registered email
* **Preconditions:** The user is registered. The "Reset Password" page is open.
* **Steps:**
  1. Enter a valid registered email into the "Email" field.
  2. Click the "Reset password" button.
* **Test data:** Email: existing_user@example.com
* **Expected result:** A success message appears: "A reset link has been sent to your email". A real email containing a secure token link is delivered to the user's mailbox.
* **Priority:** Critical
---
ID: TC_RP_02
* **Title:** Password reset request for a non-existent email (Security Check)
* **Preconditions:** The "Reset Password" page is open. The email is not registered in the system.
* **Steps:**
  1. Enter a non-registered email into the "Email" field.
  2. Click the "Reset password" button.
* **Test data:** Email: unknown_user@example.com
* **Expected result:** (Security Best Practice) The system displays the generic success message: "A reset link has been sent to your email". However, no email is actually sent. This prevents hackers from guessing which emails exist in the database.
* **Priority:** High
---
ID: TC_RP_03
* **Title:** Attempting to submit the reset form with an empty Email field
* **Preconditions:** The "Reset Password" page is open.
* **Steps:**
  1. Leave the "Email" field completely blank.
  2. Click the "Reset password" button.
* **Test data:** None.
* **Expected result:** The form is not submitted. A validation error appears below the field: "Please enter your email address".
* **Priority:** High
---
ID: TC_RP_04
* **Title:** Rate limiting and anti-spam protection (Multiple consecutive requests)
* **Preconditions:** The user has just successfully requested a password reset (TC_RP_01). The page is open again.
* **Steps:**
  1. Enter the same registered email address.
  2. Click the "Reset password" button again within 10 seconds of the first attempt.
* **Test data:** Email: existing_user@example.com
* **Expected result:** The system blocks the second attempt and displays a warning: "Too many requests. Please wait 60 seconds before trying again" (or prompts a Captcha).
* **Priority:** Medium
---
ID: TC_RP_05
* **Title:** Case insensitivity of the Email field during password reset
* **Preconditions:** A user is registered with the email "User@Example.com". The "Reset Password" page is open.
* **Steps:**
  1. Enter the registered email entirely in lowercase letters.
  2. Click the "Reset password" button.
* **Test data:** Email: user@example.com
* **Expected result:** The system ignores case sensitivity, successfully matches the account, and sends the recovery link to the user.
* **Priority:** Medium
---
ID: TC_RP_06
* **Title:** Expiration of the password reset token link
* **Preconditions:** The user successfully received the password reset link via email. The link has a predefined expiration limit of 24 hours.
* **Steps:**
  1. Wait for 24 hours and 1 minute (or simulate token expiration in the database).
  2. Click the password reset link inside the email.
* **Test data:** Expired token URL.
* **Expected result:** The website loads but displays an error: "This password reset link has expired. Please request a new one." The user is not allowed to change the password.
* **Priority:** High
---
ID: TC_RP_07
* **Title:** One-time use restriction for the password reset token link
* **Preconditions:** The user received the password reset link, clicked it, and successfully changed their password to a new one.
* **Steps:**
  1. Go back to the original email.
  2. Click the exact same password reset link for a second time.
* **Test data:** Previously used token URL.
* **Expected result:** The link is no longer valid. The website displays an error: "This link has already been used or is invalid."
* **Priority:** High
