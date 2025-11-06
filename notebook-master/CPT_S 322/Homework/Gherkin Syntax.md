**Charles Liu**
Dr. Parteek Kumar
$9/3/2025$

___

### **Part 1 Writing User Stories**

Write *five user stories* for a hypothetical online bookstore application. Each user story should follow the standard format:

> As a \[type of user], I want \[some action] so that \[some benefit]

Choose different features commonly found in e-commerce platforms. Suggested features include:

- User login and authentication
- Searching or browsing for books
- Adding items to a shopping cart
- Making a purchase
- Writing or viewing reviews

Ensure that each story:

- Identifies a specific user type
- Describes a meaningful goal
- Highlights the value or benefit to the user

___

**Shopping Cart**

As a *customer* of the online book store, I want a *shopping cart feature* so that *I can group the books I want for later purchase*.

**Reviews**
As a *customer* of the online book store, I want a *review book* so that *I can leave feedback for a book*.

**Managing Book Catalog**
As a *administrator* of the online book store, I want a *catalog managing* feature so that *I can manage the books in the online catalog*.

**Searching/Browsing for Books**
As any *user(customer/administrator)* of the online book store, I want a *search* feature so that *I can browse for books easily*

___

### **Part 2: Writing Gherkin Scenarios**

**Shopping Cart**
```md
Feature: Shopping Cart
	- As a customer of the online book store, I want a shopping cart feature so that I can group the books I want for later purchase.
		- Scenario: Adding book to cart
			- Given I have selected a book I want to add to cart
			- When I hit the "Add to Cart" button
			- Then the book should go in my shopping cart for later purchase.
		- Scenario: Deleting a book from cart
			- Given I have selected a book in my shopping cart
			- When I hit the "Delete from Cart" button
			- Then the book should go away from my shopping cart.
```

**Reviews**
```md
- Feature: Reviews
	- As a customer of the online book store, I want to review books so that I can leave feedback for a book.
		- Scenario: Adding review to book
			- Given I am on a book's review page
			- When I have selected a book I want to review and typed in a review
			-  And hit the "Review" button
			- Then the review should show up publicly and possibly affect the rating of the book
		- Scenario: Removing review for book
			- Given I am on a book's reviews page
			- When I have selected a book review
			- And I made I hit the "Delete Review" button
			- Then the review should go away
		- Scenario: Removing someone else's review
			- Given I am on the book's review page
			- When I have selected a book review someone else made 
			- And I try to hit the "Delete Review" button
			- Then I should be prevented and the review should remain
```


**Managing Book Catalog**

```md
- Feature: Managing Book Catalog
	- As a administrator of the online book store, I want a catalog managing feature so that I can manage the books in the online catalog.
		- Scenario: Add book to catalog
			- Given that I have entered the information of a book I want to sell
			- When I hit the "New Book" button
			- Then the book should be added to the public catalog for users to buy
		- Scenario: Delete book from catalog
			- Given that I have selected a book in the catalog
			- When I select the "Delete Book" button
			- Then the book should be removed from the catalog
```


**Searching/Browsing For Books**

```md
- Feature: Searching/Browsing for Books
	- As a administrator of the online book store, I want a catalog managing feature so that I can manage the books in the online catalog.
		- Scenario: Add book to catalog
			- Given that I have entered the information of a book I want to sell
			- When I hit the "New Book" button
			- Then the book should be added to the public catalog for users to buy
		- Scenario: Delete book from catalog
			- Given that I have selected a book in the catalog
			- When I select the "Delete Book" button
			- Then the book should be removed from the catalog
```

___
