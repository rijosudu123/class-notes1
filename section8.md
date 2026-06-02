# Python Errors & Exceptions Cheat Sheet

Python errors fall into two main categories: **Syntax Errors** (broken rules, code won't start) and **Exceptions** (logical failures that happen *while* the code is running).

---

## 1. Common Python Exceptions

| Exception Name | Why It Happens | Example Code |
| :--- | :--- | :--- |
| **`SyntaxError`** | Missing colons `:`, open parentheses, or bad indentation. | `if True print("Hi")` |
| **`NameError`** | Using a variable or function before defining it. | `print(my_variable)` |
| **`TypeError`** | Mixing incompatible data types together. | `"Score: " + 10` |
| **`ValueError`** | Right data type, but the value itself is invalid. | `int("apple")` |
| **`IndexError`** | Trying to access a list position that doesn't exist. | `items = [1, 2]` <br> `print(items[5])` |
| **`KeyError`** | Looking up a dictionary key that doesn't exist. | `user = {"id": 1}` <br> `print(user["name"])` |
| **`ZeroDivisionError`** | Attempting to divide any number by zero. | `5 / 0` |

---

## 2. Basic Error Handling Template

Use `try` and `except` blocks to handle exceptions gracefully without crashing your entire script.

```python
try:
    # 1. Put the risky code here
    age = int(input("Enter your age: "))
    days = 365 / age

except ValueError:
    # 2. Runs if the user inputs text instead of a number
    print("Please enter a valid whole number.")

except ZeroDivisionError:
    # 3. Runs if the user inputs 0
    print("Age cannot be zero.")

else:
    # 4. (Optional) Runs ONLY if the try block succeeded perfectly
    print(f"You are roughly {days} days old.")

finally:
    # 5. (Optional) ALWAYS runs, no matter what happened above
    print("Check complete.")