# Python Cheat Sheet: Loops, Conditionals, and Functions

### 1. Conditionals (`if`, `elif`, `else`)
Used to run code based on whether a condition is `True` or `False`.

```python
score = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
else:
    print("Grade: C")

# Logical Operators
if score > 70 and score <= 100:
    print("Passing grade")

# Ternary Operator (One-liner)
status = "Pass" if score >= 60 else "Fail"
```

---

### 2. Loops (`for`, `while`)
Loops repeat a block of code until a specific condition is met.

#### For Loops
```python
# Loop through a range (0 to 4)
for i in range(5):
    print(i)

# Loop through a list
items = ["apple", "banana", "cherry"]
for item in items:
    print(item)

# With index using enumerate
for index, item in enumerate(items):
    print(f"{index}: {item}")
```

#### While Loops
```python
count = 0
while count < 5:
    print(count)
    count += 1
```

#### Loop Control
- `break`: Stops the loop entirely.
- `continue`: Skips the current iteration.

---

### 3. Functions
Functions are reusable blocks of code defined with `def`.

```python
# Function with parameters and a default value
def greet(name, message="Hello"):
    return f"{message}, {name}!"

# Calling the function
print(greet("Alice"))           # Hello, Alice!
print(greet("Bob", "Welcome"))  # Welcome, Bob!

# Lambda (Anonymous) Functions
square = lambda x: x * x
print(square(5)) # 25
```

---

### 4. List Comprehensions
A concise way to create lists using a single line of code.

```python
# [expression for item in iterable if condition]
numbers = [1, 2, 3, 4, 5, 6]
evens = [x for x in numbers if x % 2 == 0]
# Result: [2, 4, 6]
```
