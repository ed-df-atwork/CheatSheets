# PEP 8 — The Style Guide for Python Code

## 1. Indentation & Tabs
* **Indent:** Use 4 spaces per level.
* **Tabs or Spaces?:** Spaces are preferred.
* **Maximum Line Length:** Limit to 79 characters.

```python
# Good: Aligned with opening delimiter
foo = long_function_name(var_one, var_two,
                         var_three, var_four)

# Good: Extra indentation to distinguish from body
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)
```

## 2. Imports
* Group imports: Standard library, Third-party, then Local.

```python
import os
import sys

# Third-party
import flask
import pandas as pd

# Local
from my_package import my_module
```

## 3. Whitespace & Operators
* Always surround binary operators with a single space.
* Don't use spaces around `=` for keyword arguments.

```python
# Good
x = y + 1
i = i + 1
submitted += 1

# Good (Keyword arguments)
def complex_func(real, imag=0.0):
    return magic(r=real, i=imag)
```

## 4. Naming Conventions


| Entity | Convention | Example |
| :--- | :--- | :--- |
| **Packages** | lowercase | `requests` |
| **Classes** | CapWords | `MyClass` |
| **Functions** | snake_case | `calculate_total()` |
| **Constants** | ALL_CAPS | `MAX_TIMEOUT` |

```python
class UserProfile:
    pass

def calculate_total_price(item_count):
    total_cost = item_count * 1.5
    return total_cost

MAX_RETRY_ATTEMPTS = 5
```

## 5. Programming Recommendations

```python
# Use 'is' or 'is not' for None
if x is None:
    pass

# Use truthiness for empty sequences
if not my_list:
    print("List is empty")

# Use .startswith() and .endswith()
if name.startswith('Py'):
    pass
```

## 6. Comments & Docstrings

```python
def get_user_id(username):
    """Retrieve the unique ID for a given username.
    
    Args:
        username (str): The name to lookup.
    Returns:
        int: The user's ID.
    """
    user_id = db.fetch(username)  # Inline comment
    return user_id
```
