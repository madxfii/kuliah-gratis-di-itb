# Sub-Modul 2.4: Python Basics

**Durasi:** 2-2.5 minggu | **Target Bloom Level:** Apply (C3)

---

## Tujuan Pembelajaran

- Setup Python environment
- Memahami **variables, data types, operators**
- Mengimplementasikan **functions, loops, conditionals**
- **Code transfer** dari Snap! logic ke Python syntax
- Mini-Project 2: Problem-solving dalam Python

---

## Setup Python

### Option 1: Web-Based (Recommended for Beginners)
- Go to: replit.com
- Create account
- New project → Select Python
- Code in browser, run immediately
- No installation needed!

### Option 2: Local Install
- Download Python 3.x from python.org
- Install
- Use editor: VS Code, PyCharm Community, atau IDE apapun
- Run from terminal: `python filename.py`

**For this course: Use Replit untuk simplicity**

---

## Python Basics

### 1. Variables & Print

```python
name = "Alice"
age = 20
score = 95.5

print(name)           # Output: Alice
print(f"Age: {age}")  # Output: Age: 20
print(score)          # Output: 95.5
```

### 2. Input dari User

```python
name = input("What's your name? ")
age = int(input("What's your age? "))  # Convert to int

print(f"Hello {name}, you are {age} years old")
```

### 3. Math Operations

```python
a = 10
b = 3

print(a + b)   # 13 (addition)
print(a - b)   # 7 (subtraction)
print(a * b)   # 30 (multiplication)
print(a / b)   # 3.33 (division)
print(a // b)  # 3 (integer division)
print(a % b)   # 1 (modulo/remainder)
print(a ** b)  # 1000 (exponentiation)
```

### 4. Comparison & Logic

```python
x = 10
print(x > 5)    # True
print(x == 10)  # True
print(x != 5)   # True

# Logic operators
print(x > 5 and x < 20)   # True (both conditions)
print(x < 5 or x > 20)    # False (neither condition)
print(not (x == 5))        # True (negation)
```

### 5. Strings

```python
name = "Computational Thinking"

print(len(name))        # 23 (length)
print(name.upper())     # COMPUTATIONAL THINKING
print(name.lower())     # computational thinking
print(name[0])          # C (first character)
print(name[-1])         # G (last character)
print(name[0:12])       # Computational (substring)
```

---

## Control Flow

### If-Else Conditionals

```python
score = 85

if score >= 90:
    print("A")
elif score >= 80:
    print("B")
elif score >= 70:
    print("C")
else:
    print("F")
```

### For Loops

```python
# Loop through range
for i in range(5):
    print(i)  # Output: 0, 1, 2, 3, 4

# Loop through list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# With step
for i in range(0, 10, 2):
    print(i)  # Output: 0, 2, 4, 6, 8
```

### While Loops

```python
count = 0
while count < 5:
    print(count)
    count += 1  # Increment
```

---

## Functions (Procedures)

### Define & Call Function

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")  # Output: Hello, Alice!
greet("Bob")    # Output: Hello, Bob!
```

### Function with Return Value

```python
def add(a, b):
    return a + b

result = add(3, 5)
print(result)  # Output: 8
```

### Multiple Parameters & Return

```python
def describe_person(name, age, city):
    info = f"{name} is {age} years old and lives in {city}"
    return info

output = describe_person("Alice", 25, "Jakarta")
print(output)
```

---

## Lists (Data Structures)

```python
# Create list
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]

# Access elements
print(numbers[0])   # 1 (first element)
print(numbers[-1])  # 5 (last element)

# Modify
numbers[0] = 10
numbers.append(6)   # Add to end
numbers.insert(1, 99)  # Insert at index

# Loop through
for num in numbers:
    print(num)

# List operations
print(len(numbers))  # Length
print(max(numbers))  # Maximum
print(sum(numbers))  # Sum
```

---

## Comparison: Snap! vs Python

| Concept | Snap! | Python |
|---------|-------|--------|
| **Print output** | [Say] | print() |
| **Variable** | [Set x to ...] | x = ... |
| **Loop** | [Repeat n times] | for i in range(n): |
| **Conditional** | [If ... then] | if ...: |
| **Function** | [Make a block] | def function_name(): |
| **List** | [Create list] | list_name = [...] |

**Key insight**: Same logic, different syntax!

---

## Hands-On Activities

### Activity 1: Convert Snap! to Python

**Original Snap! block**:
```
[Set [sum] to 0]
[Repeat (5) times]
    [Change [sum] by (block number)]
[Say [sum]]
```

**Convert to Python**:
```python
total = 0
for i in range(1, 6):
    total += i
print(total)  # Output: 15
```

### Activity 2: Simple Programs

**Program 1: Greet User**
```python
name = input("What's your name? ")
age = int(input("How old are you? "))

if age >= 18:
    print(f"Welcome, {name}! You're an adult.")
else:
    print(f"Welcome, {name}! You're a minor.")
```

**Program 2: Sum List**
```python
numbers = [10, 20, 30, 40, 50]
total = 0

for num in numbers:
    total += num

print(f"Sum: {total}")  # Output: Sum: 150
```

**Program 3: Find Maximum**
```python
numbers = [5, 2, 9, 1, 7]
max_num = numbers[0]

for num in numbers:
    if num > max_num:
        max_num = num

print(f"Maximum: {max_num}")
```

---

## Common Python Mistakes

| Error | Cause | Fix |
|-------|-------|-----|
| **IndentationError** | Missing colon or wrong indentation | Add : after if/for/def, indent next lines |
| **NameError** | Variable not defined | Check spelling, define variable first |
| **TypeError** | Wrong type operation | Convert types: int(x), str(x) |
| **IndexError** | List index out of range | Check list length, use len() |

---

## Ringkasan Sub-Modul 2.4

✓ **Python syntax** berbeda dari Snap!, tapi logic sama
✓ **Variables, loops, conditionals** fundamental untuk semua programming
✓ **Functions** enable code reuse & organization
✓ **Lists** allow work with collections of data

✓ **Practice adalah key** untuk master Python

---

## Mini-Project 2: Python Problem-Solving

**Task**: Solve 2-3 computational problems in Python:

Example 1: **Prime Number Checker**
```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

number = int(input("Enter number: "))
if is_prime(number):
    print(f"{number} is prime!")
else:
    print(f"{number} is not prime.")
```

Example 2: **Sum of Digits**
```python
def sum_digits(n):
    total = 0
    for digit in str(n):
        total += int(digit)
    return total

number = int(input("Enter number: "))
print(f"Sum of digits: {sum_digits(number)}")
```

Example 3: **Fibonacci Sequence**
```python
def fibonacci(n):
    fib = []
    a, b = 0, 1
    for _ in range(n):
        fib.append(a)
        a, b = b, a + b
    return fib

count = int(input("How many Fibonacci numbers? "))
print(fibonacci(count))
```

---

## Selanjutnya

Sub-Modul 2.5 akan focus pada **implementing algorithms dalam Python** — search, sort, data manipulation.

---

**Referensi**
- Khan Academy "Intro to Python" (free video lessons)
- Replit Python Docs: replit.com/docs
- Python.org Official Tutorial: python.org/3/tutorial
