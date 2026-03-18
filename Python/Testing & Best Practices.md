# Python Testing & PEP 8 Cheat Sheet

### 1. Testing with Pytest
```python
# Save as test_logic.py
def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5
    assert add(-1, 1) == 0

# Run in terminal using: pytest
```

### 2. PEP 8 Quick Rules
- **Indentation:** Use 4 spaces per level.
- **Naming:**
  - `snake_case` for variables and functions.
  - `PascalCase` for classes.
  - `UPPER_CASE` for constants.
- **Imports:** Should be at the top of the file.
- **Line Length:** Limit all lines to a maximum of 79 characters.
