# PEP 8 — The Style Guide for Python Code

## 1. Indentation & Tabs
*   **Indent:** Use **4 spaces** per indentation level.
*   **Tabs or Spaces?:** Spaces are preferred. Never mix them.
*   **Maximum Line Length:** Limit all lines to a maximum of **79 characters**.

## 2. Blank Lines
*   **Top-level functions/classes:** Surround with **two** blank lines.
*   **Method definitions inside a class:** Surround with **one** blank line.
*   **Inside functions:** Use sparingly to separate logical sections.

## 3. Imports
*   **Standard Library** imports first.
*   **Related Third-party** imports second.
*   **Local Application** imports last.
*   *Note: Use absolute imports or explicit relative imports.*

## 4. Whitespace in Expressions
*   **Avoid** extra spaces inside parentheses, brackets, or braces: `(spam[1], {eggs: 2})`.
*   **Avoid** space before a comma, semicolon, or colon.
*   **Always** surround these binary operators with a single space on either side:
    *   Assignment (`=`), augmented assignment (`+=`, `-=`), comparisons (`==`, `<`, `>`, `!=`), Booleans (`and`, `or`, `not`).

## 5. Naming Conventions

| Entity | Convention | Example |
| :--- | :--- | :--- |
| **Packages / Modules** | Short, all lowercase | `requests`, `my_module` |
| **Classes** | CapWords (PascalCase) | `MyClass` |
| **Functions / Variables** | lowercase_with_underscores | `calculate_total()` |
| **Constants** | ALL_CAPS_WITH_UNDERSCORES | `MAX_TIMEOUT` |
| **Methods** | lowercase_with_underscores | `get_data(self)` |
| **Private Internal** | Leading underscore | `_internal_var` |

## 6. Comments
*   **Block comments:** Indented to the same level as the code.
*   **Inline comments:** Use sparingly. Separate from code by at least two spaces.
*   **Docstrings:** Use `"""Triple Double Quotes"""` for all public modules, functions, classes, and methods.

## 7. Programming Recommendations
*   **Comparisons to Singletons:** Always use `is` or `is not`, never the equality operators (e.g., `if x is None:`).
*   **Boolean checks:** Use `if my_list:` instead of `if len(my_list) > 0:`.
*   **String starts/ends:** Use `''.startswith()` and `''.endswith()` instead of string slicing.
