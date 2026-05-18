ID: TC_SB_01
* **Title:** Search for items using a standard alphanumeric query
* **Preconditions:** The homepage is open. Items containing the word "Phone" exist in the database.
* **Steps:**
  1. Enter the search query into the search bar.
  2. Press the Enter key or click the magnifying glass icon.
* **Test data:** Phone
* **Expected result:** The search results page opens. All products matching or containing the word "Phone" are displayed.
* **Priority:** High
---
ID: TC_SB_02
* **Title:** Submitting an empty search query
* **Preconditions:** The homepage is open. The search bar is empty.
* **Steps:**
  1. Click inside the search bar and leave it blank.
  2. Press Enter or click the search icon.
* **Test data:** None
* **Expected result:** The page does not reload, or a tooltip appears stating "Please enter a search term". No search is executed.
* **Priority:** Medium
---
ID: TC_SB_03
* **Title:** Search with an extremely long query
* **Preconditions:** The homepage is open.
* **Steps:**
  1. Copy and paste a 501-character string into the search bar.
  2. Click the search button.
* **Test data:** A string of 501 characters: "A...[501 times]...A"
* **Expected result:** The system handles the input without crashing or returning a 500 Internal Server Error. It displays a "No results found" page.
* **Priority:** Medium
---
ID: TC_SB_04
* **Title:** Search using special characters
* **Preconditions:** The homepage is open.
* **Steps:**
  1. Enter a string of special characters into the search bar.
  2. Click the search button.
* **Test data:** !@#$%^&*()
* **Expected result:** The system handles the characters properly. No layout distortion or raw code errors occur. The page displays: "No results found".
* **Priority:** Medium
---
ID: TC_SB_05
* **Title:** Search bar input with a basic SQL Injection payload
* **Preconditions:** The homepage is open.
* **Steps:**
  1. Input a malicious SQL script into the search field.
  2. Click the search button.
* **Test data:** ' OR 1=1 --
* **Expected result:** The application securely treats the input as a regular text string. No database records are leaked. Result message: "No results found".
* **Priority:** Critical
---
ID: TC_SB_06
* **Title:** Case insensitivity of the search query
* **Preconditions:** The homepage is open. Items containing the word "Phone" exist in the database.
* **Steps:**
  1. Enter the search query completely in uppercase into the search bar.
  2. Click the search button.
* **Test data:** `PHONE`
* **Expected result:** The system ignores case sensitivity. The search results page opens and correctly displays the exact same products as for the query "Phone".
* **Priority:** High
---
ID: TC_SB_07
* **Title:** Search for a non-existent item (No results behavior)
* **Preconditions:** The homepage is open. There are no products in the database matching the term "Spaceship".
* **Steps:**
  1. Enter a valid but non-existent word into the search bar.
  2. Click the search button.
* **Test data:** `Spaceship`
* **Expected result:** The search page opens successfully. A user-friendly message is displayed: "No results found for 'Spaceship'. Please try different keywords." No empty blank screen is shown.
* **Priority:** High
---
ID: TC_SB_08
* **Title:** Search query with leading and trailing spaces
* **Preconditions:** The homepage is open. Items containing the word "Phone" exist in the database.
* **Steps:**
  1. Enter the search term with accidental spaces at the beginning and the end.
  2. Click the search button.
* **Test data:** `   Phone   `
* **Expected result:** The system automatically trims the outer spaces. The search is executed for the keyword "Phone", and all relevant items are correctly displayed.
* **Priority:** Medium
