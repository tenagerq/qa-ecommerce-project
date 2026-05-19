# E-commerce Application Testing Checklists
##  Login Feature Checklist
* [ ] Verify successful login with valid registered credentials
* [ ] Verify error handling for invalid email format (missing domain/attributes)
* [ ] Verify validation messages when submitting empty fields
* [ ] Verify login rejection with an incorrect password
* [ ] Verify that the "Login" button is disabled when mandatory fields are empty
* [ ] Verify form submission by pressing the "Enter" key on the keyboard
* [ ] Verify password masking (dots/asterisks) and visibility toggle (eye icon)
* [ ] Verify email field case insensitivity
* [ ] Verify temporary account lockout after 5 consecutive failed login attempts
---
## 📝 Registration Feature Checklist
* [ ] Verify successful account creation with valid and unique data
* [ ] Verify error handling for a too short Username (under 3 characters)
* [ ] Verify error handling for a too long Username (over 15 characters)
* [ ] Verify strict length validation at boundary limits (15 vs 16 characters)
* [ ] Verify registration rejection for an invalid email format
* [ ] Verify registration failure when attempting to use an already registered email
* [ ] Verify validation errors when "Password" and "Confirm password" fields do not match
* [ ] Verify password length restriction (minimum 8 characters)
* [ ] Verify automatic trimming of accidental leading/trailing spaces in input fields
* [ ] Verify that the "Register" button is inactive until all terms are accepted and required fields are filled
---
##  Search Bar Checklist
* [ ] Verify successful search with a standard alphanumeric keyword
* [ ] Verify application behavior when submitting an empty search query
* [ ] Verify system stability and error handling for extremely long search strings (500+ characters)
* [ ] Verify proper input sanitization when searching with special characters
* [ ] Verify security protection against basic SQL Injection payloads (' OR 1=1 --)
* [ ] Verify case insensitivity of search queries (e.g., "phone" vs "PHONE")
* [ ] Verify user-friendly "No results found" layout and message for non-existent items
* [ ] Verify automatic trimming of accidental spaces at the beginning or end of the search query
---
##  Add to Cart Checklist
* [ ] Verify successful single item addition to an empty cart
* [ ] Verify that cart counter correctly increments when adding the same item multiple times
* [ ] Verify that item quantity increments properly inside the cart page
* [ ] Verify block and error notification when adding items without selecting mandatory options (size/color)
* [ ] Verify real-time cart counter synchronization when adding different items in a single session
* [ ] Verify that cart items and counter state persist after a full page refresh (F5)
* [ ] Verify stock limit enforcement (cannot add more items than physically available in stock)
* [ ] Verify quick-add functionality directly from the product catalog quick-view cards
---
##  Password Reset Checklist
* [ ] Verify successful link generation and email delivery for a registered account
* [ ] Verify user enumeration protection (same success message for non-existent emails without actual link delivery)
* [ ] Verify validation handling for empty email field submission
* [ ] Verify rate limiting restrictions for multiple consecutive reset requests (anti-spam check)
* [ ] Verify case insensitivity matching for recovery emails
* [ ] Verify strict link token expiration after the 24-hour limit
* [ ] Verify one-time use policy for the password reset token link
