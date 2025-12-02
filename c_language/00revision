# C Language Programming Notes

## 1. Introduction to C Programming

* **History and Importance:**
    * Developed by **Dennis Ritchie** (Bell Labs, early 1970s).
    * A **procedural**, **general-purpose** language.
    * Known for efficiency, direct hardware access, and being the foundation for many modern languages (C++, Java).
* **Structure of a C Program:**
    1.  Preprocessor Directives (`#include`).
    2.  Global Declarations.
    3.  `main()` Function (The **entry point**).
    4.  User-Defined Functions.
* **Compilation and Execution Process:**
    1.  **Source Code** (`.c`) ->
    2.  **Preprocessor** (handles `#include`) ->
    3.  **Compiler** (Assembly code) ->
    4.  **Assembler** (Object code `.o`) ->
    5.  **Linker** (Executable file `.exe`) ->
    6.  **Execution**.
* **Tokens:** Smallest individual units.
    * **Keywords:** 32 reserved words (`int`, `if`, `while`).
    * **Identifiers:** Names given to variables, functions (case-sensitive).
    * **Constants:** Fixed values.
    * **Variables:** Named memory locations to store data.
* **Input and Output:**
    * **Output:** `printf()` (Formatted output).
    * **Input:** `scanf()` (Formatted input, requires `&` address-of operator).

## 2. Data Types

* **Primitive Types:**
    * `int` (Integers)
    * `float` (Single-precision floating-point)
    * `double` (Double-precision floating-point)
    * `char` (Single character, uses ASCII value)
    * `void` (No value)
* **Type Modifiers:**
    * **Size:** `short`, `long`, `long long`.
    * **Sign:** `signed` (default, positive/negative), `unsigned` (positive only, doubles positive range).
* **`sizeof()` Operator:** Returns the size in bytes of a type or variable.
* **Integer Overflow/Underflow:** Value exceeds the range the data type can store.
* **Type Casting:**
    * **Implicit (Automatic):** Done by the compiler (e.g., `int` to `float`).
    * **Explicit (Forced):** Programmer uses `(type)expression`.
* **Strings:** A **1D array of characters** terminated by the **null character** (`\0`).

## 3. Operators & Expressions

| Type | Operators | Usage |
| :--- | :--- | :--- |
| **Arithmetic** | `+`, `-`, `*`, `/`, `%` (Modulus) | Standard mathematical operations. |
| **Relational** | `==`, `!=`, `>`, `<`, `>=`, `<=` | Used for comparison (returns 0 or 1). |
| **Logical** | `&&` (AND), `||` (OR), `!` (NOT) | Combine boolean expressions. |
| **Assignment** | `=`, `+=`, `-=`, etc. | Assigns or combines assignment with arithmetic. |
| **Increment/Decrement** | `++`, `--` | `++i` (Prefix: increment then use); `i++` (Postfix: use then increment). |
| **Bitwise** | `&`, `|`, `^`, `~`, `<<`, `>>` | Operate on individual bits. |

* **Bitwise Applications:**
    * **Even/Odd Check:** `(number & 1)` returns 0 for even, 1 for odd.
    * **Swap Values:** Using XOR (`^`) without a temp variable.
* **Precedence & Associativity:** Determine the order of operation execution.

## 4. Control Flow

* **Conditional Statements:**
    * `if`, `if-else`, nested `if`.
    * `switch-case`: Multi-way branching based on a single expression value. Requires `break` to prevent fall-through.
* **Loops (Iteration):**
    * **`for`:** Best when the number of iterations is **known**.
    * **`while`:** Checks condition **before** execution (zero or more times).
    * **`do-while`:** Executes loop body **at least once**, then checks condition.
* **Control Jump Statements:**
    * **`break`:** Exits the innermost loop or `switch`.
    * **`continue`:** Skips the rest of the current iteration and moves to the next.
    * **`goto`:** Transfers control to a labeled statement (generally discouraged).

## 5. Arrays & Strings

### Arrays
* **Definition:** Contiguous memory collection of elements of the **same data type**.
* **1D Arrays:** Accessed using a single index, starting from 0.
    * Declaration: `datatype arrayName[size];`
* **2D Arrays (Matrices):** Accessed using row and column indices (`arr[i][j]`).
* **Applications:** Searching, sorting, matrix operations.

### Strings
* **Definition:** A character array terminated by `\0`.
* **Input/Output:**
    * `scanf("%s", ...)`: Reads until whitespace (unsafe).
    * `gets()`: Reads entire line (highly unsafe/deprecated).
    * `fgets(str, size, stdin)`: **Safe** way to read a line.
* **String Functions (from `<string.h>`):**
    * `strlen()`: Returns length (excludes `\0`).
    * `strcpy()`: Copies source to destination.
    * `strcat()`: Concatenates strings.
    * `strcmp()`: Compares strings (returns 0 if equal).

## 6. Functions & Debugging

* **Functions:** Reusable block of code.
    * **Declaration/Prototype:** Defines signature (name, return type, params).
    * **Definition:** Contains the code body.
* **Call by Value:** Passes a **copy** of the argument; original variable **cannot** be modified.
* **Call by Reference:** Passes the **address** of the argument (using pointers); original variable **can** be modified.
* **Recursion:** A function calling itself; requires a **base case** to terminate.
* **Debugging:**
    * **Print-based:** Using `printf()` to trace variable states and execution flow.
    * **Common Errors:** Segmentation Fault (accessing invalid memory), Infinite Loops, Divide by Zero.
    * **gdb (Optional):** Debugger used with commands like `break`, `run`, `next`, `print`.

## 7. User-Defined Data Types

### Structures (`struct`)
* Groups variables of **different** data types under a single name.
* All members occupy **separate** memory locations.
* **Usage:** Access members using the **dot operator** (`.`).

### Unions (`union`)
* Members **share the same memory location**.
* Size is equal to the size of the **largest** member.
* Only **one** member can store a valid value at any time.

### Enumerations (`enum`)
* Assigns names to **integer constants** (improves readability).
* By default, the first value is 0, the next is 1, and so on.
* Example: `enum Days { SUN, MON, TUE };` (SUN=0, MON=1, TUE=2).
