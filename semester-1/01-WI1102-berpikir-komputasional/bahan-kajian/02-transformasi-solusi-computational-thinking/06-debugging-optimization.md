# Sub-Modul 2.6: Debugging & Optimization

**Durasi:** 1 minggu | **Target Bloom Level:** Analyze (C4)

---

## Tujuan Pembelajaran

- Menggunakan **debugging strategies** untuk find & fix bugs
- Memahami **common programming errors** dan solusinya
- Melakukan **code optimization** untuk efficiency
- Melakukan **code review** & refactoring

---

## Debugging Strategies

### Strategy 1: Print Debugging

```python
def find_max(numbers):
    max_num = numbers[0]
    
    for i in range(1, len(numbers)):
        print(f"i={i}, current={numbers[i]}, max_so_far={max_num}")  # DEBUG
        
        if numbers[i] > max_num:
            max_num = numbers[i]
    
    return max_num

# Output akan show setiap step
result = find_max([3, 7, 2, 9, 1])
```

**When to use**: Quick debugging untuk understand flow

### Strategy 2: Trace Manually

```python
# Trace algorithm step-by-step manually

numbers = [3, 1, 2]

# Bubble sort trace:
# Pass 1: [3,1,2] → [1,3,2] → [1,2,3]
# Pass 2: [1,2,3] → no swaps
# Result: [1,2,3]
```

**When to use**: Understand algorithm logic

### Strategy 3: Test Cases

```python
def sum_digits(n):
    """Bug: only handles positive numbers"""
    total = 0
    for digit in str(n):
        total += int(digit)
    return total

# Test cases
print(sum_digits(123))    # 6 ✓
print(sum_digits(1))      # 1 ✓
print(sum_digits(-123))   # ERROR! (negative numbers not handled)
```

**When to use**: Find edge cases & unexpected inputs

### Strategy 4: Simplify Code

```python
# Complex version (hard to debug)
result = [x**2 for x in [i for i in range(10) if i%2==0]]

# Simplified
even_numbers = []
for i in range(10):
    if i % 2 == 0:
        even_numbers.append(i)

squares = []
for num in even_numbers:
    squares.append(num ** 2)

result = squares
# Now easier to debug!
```

**When to use**: Reduce complexity to isolate bugs

---

## Common Errors & Fixes

| Error | Example | Fix |
|-------|---------|-----|
| **Off-by-one** | `range(n)` misses last element | Use `range(1, n+1)` or check boundaries |
| **Uninitialized var** | Using variable before defining | Initialize before use |
| **Comparison logic** | `if x > 10` when should be `if x < 10` | Test edge cases |
| **List index** | Accessing index out of range | Check `len(list)` first |
| **Type mismatch** | Adding string + number | Convert types: `int()`, `str()` |
| **Infinite loop** | Loop condition never becomes false | Verify loop changes variable |

---

## Code Optimization

### Optimization 1: Reduce Loops

**Before** (inefficient):
```python
# Check same list 5 times
for user in users:
    check_user(user)
for user in users:
    process_user(user)
for user in users:
    store_user(user)
# ... repeat 2 more times
```

**After** (optimized):
```python
# Single pass
for user in users:
    check_user(user)
    process_user(user)
    store_user(user)
```

### Optimization 2: Use Right Data Structure

**Before** (slow):
```python
# Searching in list is O(n)
students = [
    {"name": "Alice", "id": 1},
    {"name": "Bob", "id": 2},
    ...
]

def find_student(student_id):
    for student in students:  # O(n)
        if student["id"] == student_id:
            return student
```

**After** (fast):
```python
# Dictionary lookup is O(1)
students = {
    1: {"name": "Alice"},
    2: {"name": "Bob"},
    ...
}

def find_student(student_id):
    return students.get(student_id)  # O(1)
```

### Optimization 3: Cache Results

**Before** (recalculate):
```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)  # SLOW! Recalculates same values

print(fibonacci(30))  # Takes seconds!
```

**After** (cache results):
```python
def fibonacci(n, cache={}):
    if n in cache:
        return cache[n]  # Return cached result
    
    if n <= 1:
        return n
    
    result = fibonacci(n-1, cache) + fibonacci(n-2, cache)
    cache[n] = result  # Store in cache
    return result

print(fibonacci(30))  # Instant!
```

---

## Code Review Checklist

When reviewing code (yours or others'), check:

- [ ] **Correctness**: Does it produce right results for all test cases?
- [ ] **Readability**: Can another programmer understand the code?
- [ ] **Efficiency**: Is it reasonably fast? Any obvious inefficiencies?
- [ ] **Edge cases**: Handles empty input? Negative numbers? Large values?
- [ ] **Comments**: Explain WHY, not WHAT (code shows what)
- [ ] **Naming**: Variable/function names clear & meaningful?
- [ ] **DRY**: No code repetition? Extract common patterns to functions?

---

## Example: Code Refactoring

### Before (Messy)
```python
def process():
    a = input("Enter: ")
    b = int(a)
    c = []
    for i in range(b):
        c.append(i*2)
    s = 0
    for x in c:
        s = s + x
    print(s)
```

### After (Clean)
```python
def calculate_sum_of_evens(count):
    """Calculate sum of first count even numbers"""
    evens = [i * 2 for i in range(count)]
    return sum(evens)

def main():
    count = int(input("Enter number: "))
    result = calculate_sum_of_evens(count)
    print(f"Sum: {result}")

main()
```

**Improvements**:
- Clear variable names (count, evens, result)
- Extract function for reusability
- Add docstring for clarity
- Single responsibility (calculate vs. print)

---

## Testing Your Code

```python
def test_linear_search():
    """Test linear_search function"""
    assert linear_search([1, 2, 3], 2) == 1  # Found
    assert linear_search([1, 2, 3], 5) == -1  # Not found
    assert linear_search([], 1) == -1  # Empty list
    assert linear_search([1], 1) == 0  # Single element
    print("All tests passed!")

test_linear_search()
```

**Good test cases cover**:
- Normal cases (expected inputs)
- Edge cases (empty, single element, large numbers)
- Invalid cases (not found, wrong type)

---

## Ringkasan Sub-Modul 2.6

✓ **Debugging is systematic** — use strategies to find root cause
✓ **Print debugging, manual trace, test cases** — different tools for different bugs
✓ **Optimization matters** — right algorithm & data structure = 100x faster
✓ **Code review** — catch bugs early, improve quality
✓ **Testing** — verify correctness for various inputs

---

## Mini-Project 2 Final

**Complete Mini-Project 2** dengan:
1. Solve 3 Python problems using algorithms learned
2. Write clean, readable code with comments
3. Test edge cases
4. Optimize for efficiency where applicable
5. Code review dari peers (optional)

**Example deliverable**:
- Program 1: Search algorithm problem
- Program 2: Sort or data processing
- Program 3: Analysis or puzzle-solving
- Submit dengan: code + output + brief explanation

---

## Modul 2 Complete!

✓ **Understood CT vs Programming**
✓ **Implemented logic in Snap! blocks**
✓ **Implemented algorithms in Python**
✓ **Learned debugging & optimization**
✓ **Completed Mini-Projects 1 & 2**

**CPMK 1 Achievement**: ~85-90% (understand + apply dengan tools)
**CPMK 2 Achievement**: ~30-40% (starting to analyze problems independently)

---

**Next: Modul 3 — Dampak & Tren Komputing pada Domain Tertentu!**

---

**Referensi**
- Python Debugging: docs.python.org
- Code Optimization: pythonspeed.com
- Big O Notation: bigocheatsheet.com
