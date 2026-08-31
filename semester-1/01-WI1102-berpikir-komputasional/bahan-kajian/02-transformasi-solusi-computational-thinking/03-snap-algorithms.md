# Sub-Modul 2.3: Algoritma dalam Snap!

**Durasi:** 1-1.5 minggu | **Target Bloom Level:** Apply (C3)

---

## Tujuan Pembelajaran

- Mengimplementasikan **search algorithms** dalam Snap!
- Mengimplementasikan **sorting algorithms** dalam Snap!
- Memahami **efficiency tradeoffs** antara algoritma berbeda
- Melakukan **algorithm comparison** (tempo, complexity)

---

## Algorithm 1: Linear Search dalam Snap!

**Pseudocode (dari Modul 1)**:
```
ALGORITHM: Linear Search
INPUT: list, target value
OUTPUT: index of target (-1 if not found)

FOR each element in list:
    IF element = target:
        RETURN index
RETURN -1
```

**Implementasi dalam Snap!**:
```
[Make a block [linear_search target_val]]
    [Set [index] to 0]
    [Set [found] to false]
    [For i from 1 to (length of [list])]
        [If (item i of [list]) = [target_val]]
            [Set [found] to true]
            [Set [index] to i]
    [Report [index] if [found], else -1]
```

**Activity**: 
1. Create list dengan 10 numbers
2. Implement linear_search block
3. Call block untuk cari value tertentu
4. Test dengan berbagai values (found & not found)

---

## Algorithm 2: Binary Search dalam Snap!

**Pseudocode**:
```
ALGORITHM: Binary Search (for SORTED list)
INPUT: sorted list, target value
OUTPUT: index of target (-1 if not found)

SET left = 0, right = length - 1
WHILE left <= right:
    SET mid = (left + right) / 2
    IF list[mid] = target:
        RETURN mid
    IF list[mid] < target:
        left = mid + 1
    IF list[mid] > target:
        right = mid - 1
RETURN -1
```

**Implementasi dalam Snap!** (simplified):
```
[Make a block [binary_search target_val]]
    [Set [left] to 1]
    [Set [right] to (length of [list])]
    [Repeat until [found] or [left] > [right]]
        [Set [mid] to ((left + right) / 2)]
        [If (item [mid] of [list]) = [target_val]]
            [Set [found] to true]
            [Report [mid]]
        [If (item [mid] of [list]) < [target_val]]
            [Set [left] to [mid + 1]]
        [Else]
            [Set [right] to [mid - 1]]
    [Report -1]  ← not found
```

**Activity**:
1. Create SORTED list (important for binary search!)
2. Implement both linear_search & binary_search
3. Time both untuk large lists (e.g., 1000 elements)
4. Observe: binary search much faster!

---

## Algorithm 3: Bubble Sort dalam Snap!

**Pseudocode**:
```
ALGORITHM: Bubble Sort
INPUT: unsorted list
OUTPUT: sorted list (in place)

REPEAT until list is sorted:
    sorted = true
    FOR each adjacent pair in list:
        IF first > second:
            SWAP them
            sorted = false
```

**Implementasi dalam Snap!**:
```
[Make a block [bubble_sort]]
    [Set [sorted?] to false]
    [Repeat until [sorted?]]
        [Set [sorted?] to true]
        [For i from 1 to ((length of [list]) - 1)]
            [If (item i of [list]) > (item (i+1) of [list])]
                [Set [sorted?] to false]
                [Swap items i and i+1 in list]
```

**Swap helper block**:
```
[Make a block [swap_items idx1 idx2]]
    [Set [temp] to (item [idx1] of [list])]
    [Set item [idx1] to (item [idx2] of [list])]
    [Set item [idx2] to [temp]]
```

**Activity**:
1. Create unsorted list
2. Implement bubble sort
3. Watch animation (add visual steps)
4. Measure time untuk sort 100 elements

---

## Algorithm 4: Selection Sort dalam Snap!

**Pseudocode**:
```
ALGORITHM: Selection Sort
INPUT: unsorted list
OUTPUT: sorted list (in place)

FOR i from 1 to length-1:
    SET min_index = i
    FOR j from i+1 to length:
        IF list[j] < list[min_index]:
            SET min_index = j
    SWAP list[i] with list[min_index]
```

**Implementasi dalam Snap!**:
```
[Make a block [selection_sort]]
    [For i from 1 to ((length of [list]) - 1)]
        [Set [min_index] to i]
        [For j from (i+1) to (length of [list])]
            [If (item j of [list]) < (item [min_index] of [list])]
                [Set [min_index] to j]
        [Swap items [i] and [min_index]]
```

**Activity**:
1. Implement selection sort
2. Compare time dengan bubble sort
3. For 100 elements: which is faster?

---

## Algorithm Comparison: Bubble vs Selection

| Aspect | Bubble Sort | Selection Sort | Binary Search | Linear Search |
|--------|-------------|-----------------|---|---|
| **Best Case** | O(n) if already sorted | O(n²) | O(log n) | O(1) |
| **Worst Case** | O(n²) | O(n²) | O(log n) | O(n) |
| **Easy to understand** | Yes | Yes | Moderate | Yes |
| **Stable** | Yes | No | N/A | N/A |
| **When to use** | Educational | General purpose | Sorted data only | Unsorted data |

**Key Insight**: Different algorithms have different trade-offs. Choice depends on data & constraints!

---

## Mini-Project 2A: Sorting Visualizer

**Task**: Create Snap program yang:
1. Generates random list
2. Implements bubble sort
3. Visualizes sorting process (show bars/numbers being moved)
4. Measures time taken
5. Allows user choose different sort algorithms

**Learning**: See algorithm efficiency visually!

---

## Pattern Recognition dalam Algorithm

### Pattern 1: Iterate Through Data
```
FOR each element in list:
    Do something with element
```
Used in: search, sum, average, finding min/max

### Pattern 2: Compare Adjacent Elements
```
FOR each adjacent pair:
    IF pair[i] > pair[i+1]:
        SWAP
```
Used in: sorting (bubble), checking if sorted

### Pattern 3: Divide & Conquer
```
Divide problem into smaller subproblems
Solve each subproblem
Combine solutions
```
Used in: binary search, merge sort, quicksort

### Pattern 4: Accumulate Result
```
SET result = 0
FOR each element:
    result = result + element
RETURN result
```
Used in: sum, count, product, all aggregations

---

## Common Mistakes in Algorithm Implementation

| Mistake | Impact | Fix |
|---------|--------|-----|
| **Off-by-one error** | Loop misses element atau loops extra time | Check: start index, end index, loop condition |
| **Forgot to swap** | Elements not actually sorted | Verify swap logic |
| **Infinite loop** | Program hang | Check loop condition dapat berakhir |
| **Mutation mistake** | Wrong list being sorted | Verify you're modifying correct list |

**Debug Strategy**: Add [say] blocks untuk trace values!

---

## Ringkasan Sub-Modul 2.3

✓ **Linear search O(n)** — simple but slow for large lists
✓ **Binary search O(log n)** — fast but requires sorted data
✓ **Bubble sort O(n²)** — simple, good for educational purposes
✓ **Selection sort O(n²)** — comparable efficiency, sometimes faster
✓ **Algorithm efficiency matters** — same problem, different solutions have different speed/space

---

## Selanjutnya

Sub-Modul 2.4 akan introduce **Python** — transition dari Snap! blocks ke text-based programming. Same algorithms, different syntax!

---

**Referensi**
- Snap! Help: snap.berkeley.edu/help
- Algorithm Visualization: visualgo.net (for understanding)
- Big O Notation Basics: see appendix dalam textbook
