# Python Object-Oriented Programming: Practice Exercises

**Level:** Beginner to Intermediate
**Language:** Python 3
**Number of exercises:** 5

---

## Introduction

In these exercises, you will practise the fundamentals of Object-Oriented Programming (OOP) in Python. You will start by creating simple classes and gradually move towards more complex systems in which objects interact with each other.

The goal is not only to write classes, but also to understand how to design them, manage their data, and implement methods that change the state of an object.

### Learning objectives

By completing these exercises, you will learn how to:

* Define classes and create objects.
* Initialise attributes using the `__init__()` method.
* Write methods that operate on object attributes.
* Use `self` to access attributes and methods.
* Modify an object's state.
* Work with lists and dictionaries inside classes.
* Store objects inside other objects.
* Make one object call methods of another object.
* Validate input and handle invalid operations.
* Design small systems using multiple cooperating classes.

### General instructions

For every exercise:

1. Create the required class or classes.
2. Implement all specified attributes and methods.
3. Create at least two objects to test your implementation.
4. Test every method with different inputs.
5. Handle invalid operations appropriately.
6. Complete the additional challenges if you finish the main task.

**Important:** You should implement the exercises independently. You are encouraged to experiment with your own solutions, but make sure that your implementation satisfies all the requirements.

---

# Exercise 1: The Dog Class

**Difficulty:** Beginner

## Objective

Learn how to define a class, initialise attributes, create objects, and implement simple methods.

## Problem description

Create a class called `Dog` that represents a dog.

Every dog has a name, an age, and a breed. The class should also provide methods that allow the dog to bark, introduce itself, and celebrate its birthday.

## Required attributes

Implement the following attributes:

| Attribute | Description            | Example              |
| --------- | ---------------------- | -------------------- |
| `name`    | The dog's name         | `"Max"`              |
| `age`     | The dog's age in years | `3`                  |
| `breed`   | The dog's breed        | `"Golden Retriever"` |

All attributes should be initialised through the constructor.

## Required methods

### 1. `bark()`

Print the following message:

```text
Woof! Woof!
```

### 2. `introduce()`

Print a sentence containing the dog's name, age, and breed.

For example:

```text
Hi! My name is Max. I am 3 years old and I am a Golden Retriever.
```

### 3. `birthday()`

Increase the dog's age by one year.

The method should also print a message confirming that the dog has celebrated its birthday.

## Example usage

```python
dog1 = Dog("Max", 3, "Golden Retriever")
dog2 = Dog("Bella", 5, "Beagle")

dog1.introduce()
dog1.bark()

dog2.introduce()

dog1.birthday()
dog1.introduce()
```

## Additional challenges

1. Add a `get_age()` method that returns the dog's current age.
2. Add a `change_name(new_name)` method that changes the dog's name.
3. Create three different dogs and store them in a list.
4. Iterate through the list and call `introduce()` on every dog.

## Questions to consider

* What is the difference between a class and an object?
* Why do we use `self` inside methods?
* What happens if two objects have different attribute values?
* Why is the constructor useful?

---

# Exercise 2: Bank Account

**Difficulty:** Beginner

## Objective

Learn how to manage an object's state, modify numerical attributes, and validate operations.

## Problem description

Create a class called `BankAccount` that represents a bank account.

Every account belongs to a person and has a balance. The account holder should be able to deposit and withdraw money and check the current balance.

Your implementation must prevent invalid transactions.

## Required attributes

| Attribute | Description                 | Initial value        |
| --------- | --------------------------- | -------------------- |
| `owner`   | The account owner's name    | Provided by the user |
| `balance` | The current account balance | `0`                  |

## Required methods

### 1. `deposit(amount)`

Add the specified amount to the account balance.

Requirements:

* The amount must be greater than zero.
* If the amount is invalid, do not modify the balance.
* Print a message confirming the transaction or explaining why it failed.

### 2. `withdraw(amount)`

Withdraw the specified amount from the account.

Requirements:

* The amount must be greater than zero.
* The account must have sufficient funds.
* The balance must never become negative.
* If the transaction fails, the balance must remain unchanged.

### 3. `get_balance()`

Return the current account balance.

### 4. `display_info()`

Display the account owner's name and current balance.

## Example usage

```python
account1 = BankAccount("Anna")
account2 = BankAccount("Peter")

account1.deposit(1000)
account1.withdraw(250)

account2.deposit(500)

account1.display_info()
account2.display_info()

print(account1.get_balance())
```

Expected balance for `account1`:

```text
750
```

## Additional challenge: Money transfers

Implement the following method:

```python
transfer(amount, other_account)
```

The method should transfer money from the current account to another `BankAccount` object.

Requirements:

* The amount must be positive.
* The current account must have sufficient funds.
* The receiving account must be a valid `BankAccount` object.
* The transfer must update both accounts.
* If the transaction fails, neither account should be modified.

Example usage:

```python
account1 = BankAccount("Anna")
account2 = BankAccount("Peter")

account1.deposit(1000)
account1.transfer(300, account2)

account1.display_info()
account2.display_info()
```

After a successful transfer, Anna should have `700` and Peter should have `300`.

## Additional challenges

1. Add a `transaction_count` attribute that records successful deposits, withdrawals, and transfers.
2. Implement a `reset()` method that resets the account balance to zero.
3. Add a method that calculates interest using a given annual interest rate.
4. Prevent users from creating an account with a negative initial balance.

## Questions to consider

* Why should the balance be modified through methods?
* What is the difference between returning a value and printing it?
* Why is it important to validate transactions before modifying the balance?
* How can one object interact with another object?

---

# Exercise 3: Coffee Machine

**Difficulty:** Intermediate

## Objective

Practise using dictionaries as object attributes, updating dictionary values, managing an object's state, and implementing methods that work together.

## Problem description

Create a class called `CoffeeMachine` that simulates a coffee machine.

The machine stores a limited amount of water, coffee, milk, and sugar. It can prepare different types of coffee, but only if it has enough ingredients.

Each coffee type has a recipe describing the required quantities of ingredients.

When a coffee is successfully prepared, the machine must update its ingredient inventory.

## Required attributes

### 1. `ingredients`

Create a dictionary containing the available ingredients and their quantities.

Use the following initial values:

```python
ingredients = {
    "water": 1000,
    "coffee": 500,
    "milk": 500,
    "sugar": 200
}
```

All quantities are measured in millilitres or grams, depending on the ingredient.

### 2. `recipes`

Create a dictionary containing the recipes for different types of coffee.

Use the following recipes:

```python
recipes = {
    "espresso": {
        "water": 50,
        "coffee": 18,
        "milk": 0,
        "sugar": 0
    },
    "americano": {
        "water": 150,
        "coffee": 18,
        "milk": 0,
        "sugar": 0
    },
    "cappuccino": {
        "water": 100,
        "coffee": 18,
        "milk": 100,
        "sugar": 0
    },
    "latte": {
        "water": 100,
        "coffee": 18,
        "milk": 200,
        "sugar": 0
    }
}
```

### 3. `cups_served`

Create an attribute that counts the number of successfully prepared coffees.

Its initial value should be `0`.

## Required methods

### 1. `get_status()`

Display the current quantity of every ingredient.

Example output:

```text
Coffee machine status:
Water: 1000 ml
Coffee: 500 g
Milk: 500 ml
Sugar: 200 g
```

### 2. `check_ingredients(coffee_type)`

Check whether the machine has enough ingredients to prepare the requested coffee.

Requirements:

* Check whether the coffee type exists.
* Compare the required quantities with the available quantities.
* Return `True` if all required ingredients are available.
* Return `False` otherwise.
* Do not modify the inventory.

### 3. `make_coffee(coffee_type)`

Prepare the requested coffee.

Requirements:

1. Check whether the requested coffee type exists.
2. Check whether enough ingredients are available.
3. If the coffee can be prepared, subtract the required quantities from the `ingredients` dictionary.
4. Increase `cups_served` by one.
5. Print a confirmation message.
6. If the operation fails, display an appropriate error message.
7. Never allow an ingredient quantity to become negative.

**Important:** The inventory must only be updated after all required ingredients have been checked.

### 4. `refill(ingredient, amount)`

Add ingredients to the machine.

Requirements:

* The ingredient must already exist in the `ingredients` dictionary.
* The amount must be greater than zero.
* Update the existing dictionary value.
* Reject invalid ingredient names and invalid amounts.

For example, refilling the machine with 500 ml of water should increase the water quantity from 1000 to 1500.

### 5. `add_recipe(coffee_type, recipe)`

Add a new coffee recipe to the `recipes` dictionary.

Requirements:

* The recipe must be a dictionary.
* It must contain the required ingredient keys: `water`, `coffee`, `milk`, and `sugar`.
* All ingredient quantities must be non-negative numbers.
* Do not overwrite an existing recipe unless you explicitly choose to support that behaviour.

### 6. `display_statistics()`

Display the number of coffees successfully prepared.

For example:

```text
Total coffees served: 5
```

## Example usage

```python
machine = CoffeeMachine()

machine.get_status()

machine.make_coffee("cappuccino")
machine.make_coffee("espresso")

machine.refill("water", 500)

machine.add_recipe(
    "mocha",
    {
        "water": 100,
        "coffee": 18,
        "milk": 100,
        "sugar": 10
    }
)

machine.make_coffee("mocha")

machine.get_status()
machine.display_statistics()
```

## Additional challenges

### Challenge 1: Customised coffee

Implement a method that allows the customer to request additional milk or sugar.

The extra ingredients must also be deducted from the inventory.

### Challenge 2: Reset the machine

Implement a `reset()` method that restores the ingredient quantities to their original values and resets `cups_served` to zero.

### Challenge 3: Ingredient reports

Implement a method that returns a list of ingredients that are running low. You can define the minimum threshold for each ingredient.

### Challenge 4: Coffee prices

Add a dictionary that stores the price of each coffee type. Implement a method that calculates the total revenue generated by the machine.

### Challenge 5: Dictionary operations

Implement a method called `update_recipe(coffee_type, ingredient, new_amount)` that updates a single ingredient quantity in an existing recipe.

For example, you should be able to change the amount of milk required for a latte without replacing the entire recipe.

## Questions to consider

* Why is a dictionary useful for storing ingredient quantities?
* How can you update one value in a dictionary?
* Why should you check all ingredients before modifying the inventory?
* What is the difference between `ingredients` and `recipes`?
* How can multiple methods operate on the same object attributes?

---

# Exercise 4: Shopping Cart

**Difficulty:** Intermediate

## Objective

Learn how to create multiple classes, store objects inside another object, and call methods on objects contained within a collection.

## Problem description

Create a simple shopping cart system.

The system should contain two classes:

* `Product`: represents a product available for purchase.
* `ShoppingCart`: stores products and calculates the total price of the cart.

The shopping cart must store actual `Product` objects, not just their names or prices.

This exercise introduces the idea that an object can contain references to other objects and call their methods.

## Class 1: `Product`

### Required attributes

| Attribute  | Description           |
| ---------- | --------------------- |
| `name`     | The product's name    |
| `price`    | The price of one unit |
| `quantity` | The number of units   |

### Required methods

#### 1. `get_total_price()`

Return the total price of the product, calculated using its price and quantity.

For example, if a product costs 10 and the quantity is 3, the total should be 30.

#### 2. `display_info()`

Display the product's name, unit price, and quantity.

#### 3. `update_quantity(new_quantity)`

Update the quantity of the product.

Reject invalid quantities.

## Class 2: `ShoppingCart`

### Required attributes

| Attribute | Description                         |
| --------- | ----------------------------------- |
| `items`   | A list containing `Product` objects |

Initially, the shopping cart should be empty.

### Required methods

#### 1. `add_product(product)`

Add a `Product` object to the cart.

The method should receive an existing `Product` object as an argument.

#### 2. `remove_product(product_name)`

Remove a product from the cart by its name.

If the product does not exist, display an appropriate message.

#### 3. `calculate_total()`

Calculate and return the total price of the shopping cart.

**Requirement:** Iterate through the list of products and call each product's `get_total_price()` method.

Do not duplicate the product price calculation inside the shopping cart.

#### 4. `display_cart()`

Display every product in the cart and the total price.

This method should call each product's `display_info()` method.

#### 5. `find_product(product_name)`

Search for a product by name.

Return the corresponding `Product` object if found, or `None` if it does not exist.

## Example usage

```python
apple = Product("Apple", 1.5, 3)
bread = Product("Bread", 2.0, 2)
milk = Product("Milk", 1.8, 1)

cart = ShoppingCart()

cart.add_product(apple)
cart.add_product(bread)
cart.add_product(milk)

cart.display_cart()

print("Total:", cart.calculate_total())
```

The expected total is `10.3`.

## Additional challenges

### Challenge 1: Discounts

Implement a method called `apply_discount(percentage)` that calculates the total price after a discount.

For example, a 10% discount on a cart worth 100 should result in a discounted total of 90.

### Challenge 2: Product quantities

Implement an `increase_quantity(product_name, amount)` method that finds a product and updates its quantity.

The shopping cart should call the relevant method on the `Product` object.

### Challenge 3: Duplicate products

Decide how your shopping cart should behave when the same product is added twice.

You may either:

* Store duplicate product objects separately, or
* Increase the quantity of the existing product.

Implement your chosen approach consistently.

### Challenge 4: Empty cart

Make sure your cart handles an empty list correctly. The total price of an empty cart should be zero.

## Questions to consider

* Why does the shopping cart store objects instead of just product names?
* What is the difference between `cart.items` and a single `Product` object?
* Why is calling `product.get_total_price()` better than duplicating its calculation?
* How can one class delegate responsibility to another class?
* What happens if the shopping cart contains no products?

---

# Exercise 5: Library Management System

**Difficulty:** Intermediate to Advanced

## Objective

Learn how to design a system consisting of multiple classes that interact with one another.

This exercise combines attributes, methods, lists, searching, state management, and object composition.

## Problem description

Create a library management system that allows users to add books, borrow books, return books, and check which books are available.

The system should contain two classes:

* `Book`: represents an individual book.
* `Library`: manages a collection of books.

The `Library` class should store `Book` objects in a list and use the methods of those objects to perform borrowing and returning operations.

## Class 1: `Book`

### Required attributes

| Attribute     | Description                            | Initial value        |
| ------------- | -------------------------------------- | -------------------- |
| `title`       | The book's title                       | Provided by the user |
| `author`      | The author's name                      | Provided by the user |
| `is_borrowed` | Whether the book is currently borrowed | `False`              |

### Required methods

#### 1. `borrow()`

Mark the book as borrowed if it is currently available.

Requirements:

* If the book is available, update `is_borrowed` to `True`.
* If it is already borrowed, do not change its state.
* Return `True` if the operation succeeds and `False` otherwise.

#### 2. `return_book()`

Mark the book as available again.

Requirements:

* If the book is borrowed, update `is_borrowed` to `False`.
* If the book is already available, do not change its state.
* Return `True` if the operation succeeds and `False` otherwise.

#### 3. `display_info()`

Display the title, author, and availability status.

Example output:

```text
Title: 1984
Author: George Orwell
Status: Available
```

## Class 2: `Library`

### Required attributes

| Attribute | Description                      |
| --------- | -------------------------------- |
| `name`    | The library's name               |
| `books`   | A list containing `Book` objects |

The list should initially be empty.

### Required methods

#### 1. `add_book(book)`

Add a `Book` object to the library.

The method must receive a `Book` object as an argument.

#### 2. `find_book(title)`

Search for a book by its title.

Return the corresponding `Book` object if found. Otherwise, return `None`.

#### 3. `borrow_book(title)`

Borrow a book from the library.

Requirements:

1. Find the requested book.
2. If the book does not exist, display an error message.
3. If the book exists, call its `borrow()` method.
4. Display whether the borrowing operation succeeded.

**Important:** The library should not directly reimplement the borrowing logic. The `Book` object should be responsible for managing its own borrowing state.

#### 4. `return_book(title)`

Return a book to the library.

Requirements:

1. Find the requested book.
2. If the book does not exist, display an error message.
3. If the book exists, call its `return_book()` method.
4. Display whether the operation succeeded.

#### 5. `available_books()`

Return a list of all books that are currently available.

The method should return `Book` objects, not just titles.

#### 6. `display_books()`

Display information about every book in the library.

This method should call `display_info()` on each `Book` object.

## Example usage

```python
book1 = Book("1984", "George Orwell")
book2 = Book("Dune", "Frank Herbert")
book3 = Book("The Hobbit", "J. R. R. Tolkien")

library = Library("Central Library")

library.add_book(book1)
library.add_book(book2)
library.add_book(book3)

library.display_books()

library.borrow_book("1984")
library.borrow_book("1984")  # This should fail

library.return_book("1984")

print("Available books:")

for book in library.available_books():
    book.display_info()
```

## Additional challenges

### Challenge 1: Prevent duplicate books

Prevent the same book from being added multiple times.

For this exercise, you can identify duplicates by comparing their titles.

### Challenge 2: Count available books

Implement a method called `count_available_books()` that returns the number of books currently available.

### Challenge 3: Count borrowed books

Implement a method called `count_borrowed_books()` that returns the number of books currently borrowed.

### Challenge 4: Search by author

Implement a method called `find_books_by_author(author)` that returns all books written by the specified author.

### Challenge 5: Library statistics

Implement a method called `display_statistics()` that displays:

* The total number of books.
* The number of available books.
* The number of borrowed books.

### Challenge 6: Book search

Implement a method called `search_books(keyword)` that returns all books whose titles contain a given keyword.

## Questions to consider

* Why does the library store `Book` objects instead of storing each book's attributes separately?
* Why does `Library.borrow_book()` call `Book.borrow()`?
* Which class is responsible for managing whether a book is borrowed?
* What is the difference between returning a book object and returning a list of book objects?
* How would you extend this system to support library members?

---

# Final Challenge: Extend One of Your Projects

After completing all five exercises, choose one project and extend it with at least two new features.

Possible ideas include:

* Add a customer system to the coffee machine.
* Add a transaction history to the bank account.
* Add categories and stock management to the shopping cart.
* Add library members and borrowing limits to the library.
* Add new attributes and behaviours to the dog class.

Your implementation should continue to follow the principles of object-oriented programming.

## Final checklist

Before submitting your work, make sure that:

* [ ] All required classes have been implemented.
* [ ] Every required attribute is initialised correctly.
* [ ] Every required method works as specified.
* [ ] You have created and tested multiple objects.
* [ ] Invalid operations are handled appropriately.
* [ ] Lists and dictionaries are used where required.
* [ ] Objects interact through their methods where specified.
* [ ] You have tested edge cases.
* [ ] Your code is readable and consistently formatted.

## Submission

Submit your Python code in a `.py` file or a Jupyter Notebook.

Include a short demonstration showing that your implementation works. You should be able to explain the purpose of each class, its attributes, and its methods.

**The main goal is to understand how to design objects that manage their own data and collaborate with other objects to solve a problem.**
