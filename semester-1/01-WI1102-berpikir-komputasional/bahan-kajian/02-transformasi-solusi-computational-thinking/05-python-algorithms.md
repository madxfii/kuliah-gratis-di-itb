# Sub-Modul 2.5: Algoritma dalam Python

**Durasi:** 1-1.5 minggu | **Target Bloom Level:** Apply (C3)

---

## Tujuan Pembelajaran

- Mengimplementasikan **search algorithms** (linear, binary)
- Mengimplementasikan **sorting algorithms** (bubble, selection, insertion)
- Memahami **list operations** dan built-in functions
- Melakukan **algorithm analysis** (time complexity)

---

## Algorithm 1: Linear Search

```python
def linear_search(lst, target):
    """Find index of target in list, return -1 if not found"""
    for i in range(len(lst)):
        if lst[i] == target:
            return i
    return -1

# Test
numbers = [10, 5, 3, 8, 1]
print(linear_search(numbers, 8))   # Output: 3
print(linear_search(numbers, 99))  # Output: -1
```

**Time Complexity**: O(n) — worst case must check all elements

---

## Algorithm 2: Binary Search

```python
def binary_search(lst, target):
    """Efficient search for SORTED list"""
    left, right = 0, len(lst) - 1
    
    while left <= right:
        mid = (left + right) // 2
        
        if lst[mid] == target:
            return mid
        elif lst[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    
    return -1

# Test (must be SORTED!)
numbers = [1, 3, 5, 8, 10]
print(binary_search(numbers, 8))   # Output: 3
print(binary_search(numbers, 99))  # Output: -1
```

**Time Complexity**: O(log n) — exponentially faster for large lists

**Activity**: Compare linear vs binary search speed untuk list 1000 elements

---

## Algorithm 3: Bubble Sort

```python
def bubble_sort(lst):
    """Sort list in ascending order using bubble sort"""
    n = len(lst)
    
    for i in range(n):
        swapped = False
        for j in range(0, n - i - 1):
            if lst[j] > lst[j + 1]:
                # Swap
                lst[j], lst[j + 1] = lst[j + 1], lst[j]
                swapped = True
        
        if not swapped:
            break  # Already sorted
    
    return lst

# Test
numbers = [64, 34, 25, 12, 22, 11, 90]
print(bubble_sort(numbers.copy()))  # Output: [11, 12, 22, 25, 34, 64, 90]
```

**Time Complexity**: O(n²) — quadratic time

---

## Algorithm 4: Selection Sort

```python
def selection_sort(lst):
    """Sort using selection sort"""
    n = len(lst)
    
    for i in range(n):
        # Find minimum element in remaining list
        min_idx = i
        for j in range(i + 1, n):
            if lst[j] < lst[min_idx]:
                min_idx = j
        
        # Swap
        lst[i], lst[min_idx] = lst[min_idx], lst[i]
    
    return lst

# Test
numbers = [64, 34, 25, 12, 22, 11, 90]
print(selection_sort(numbers.copy()))  # Output: [11, 12, 22, 25, 34, 64, 90]
```

**Time Complexity**: O(n²) — always, regardless of input

---

## Python Built-in Functions (Less Code!)

```python
# Sorting (uses efficient algorithm internally)
numbers = [64, 34, 25, 12, 22, 11, 90]
numbers_sorted = sorted(numbers)  # Returns new sorted list
numbers.sort()  # Sorts in place

# Finding max/min
print(max(numbers))  # 90
print(min(numbers))  # 11
print(sum(numbers))  # Sum of all

# Count occurrences
fruits = ["apple", "banana", "apple", "cherry", "apple"]
print(fruits.count("apple"))  # 3

# Index of first occurrence
print(fruits.index("banana"))  # 1
```

**Real-world**: Professional programmers use built-in functions! Knowing algorithms helps understand when & why they work.

---

## Working with Data: Processing Lists

### Filter Data
```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# Get only even numbers
evens = []
for num in numbers:
    if num % 2 == 0:
        evens.append(num)
print(evens)  # [2, 4, 6, 8, 10]
```

### Transform Data
```python
# Square each number
squares = []
for num in numbers:
    squares.append(num ** 2)
print(squares)  # [1, 4, 9, 16, 25, ...]
```

### Aggregate Data
```python
# Count above threshold
count = 0
for num in numbers:
    if num > 5:
        count += 1
print(count)  # 5
```

---

## Algorithm Comparison: Which to Use?

| Problem | Algorithm | Reason |
|---------|-----------|--------|
| **Find element in unsorted list** | Linear search | No choice, must check all |
| **Find element in sorted list** | Binary search | 100x faster! |
| **Sort 100 elements** | Built-in sort() | Optimal & simple |
| **Learn sorting mechanism** | Bubble/Selection | Educational |
| **Real-world production code** | Built-in functions | Tested, optimized |

**Takeaway**: Understanding algorithms helps you choose the right tool!

---

## Mini-Project 2B: Data Analysis Program

**Task**: Process real-world data

```python
# Example: Student grades
students = {
    "Alice": [85, 90, 88],
    "Bob": [78, 82, 80],
    "Charlie": [92, 95, 93],
    "Diana": [88, 91, 89]
}

# Calculate average for each student
for student, grades in students.items():
    avg = sum(grades) / len(grades)
    print(f"{student}: {avg:.1f}")

# Find highest performer
best_avg = 0
best_student = ""
for student, grades in students.items():
    avg = sum(grades) / len(grades)
    if avg > best_avg:
        best_avg = avg
        best_student = student

print(f"Best student: {best_student} ({best_avg:.1f})")
```

---

## Ringkasan Sub-Modul 2.5

✓ **Linear search O(n)** — simple, works for unsorted data
✓ **Binary search O(log n)** — fast, requires sorted data
✓ **Bubble/Selection sort O(n²)** — educational, understand mechanism
✓ **Built-in functions** — use in production code
✓ **Algorithm choice matters** — right tool for right job

---

## Selanjutnya

Sub-Modul 2.6 akan focus pada **debugging techniques & code optimization** — making your code robust & efficient.

---

**Referensi**
- Python Docs: python.org/3/library
- Big O Notation: understand complexity
- Replit Examples: replit.com/templates
