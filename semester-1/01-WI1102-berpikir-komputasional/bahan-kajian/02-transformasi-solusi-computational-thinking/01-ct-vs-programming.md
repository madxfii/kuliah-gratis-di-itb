# Sub-Modul 2.1: Computational Thinking ≠ Programming

**Durasi:** 0.5-1 minggu | **Target Bloom Level:** Understand (C2)

---

## Tujuan Pembelajaran

- Memahami **perbedaan mendasar** antara CT (way of thinking) dan Programming (tool)
- Mengenali bahwa **CT principles tetap sama** walaupun tools berubah
- Understand **levels of abstraction** dalam computing

---

## Intuisi Dasar

**Analogi Penting**: 

Computational Thinking ≈ **Architecture** (rencana rumah)
Programming ≈ **Construction** (membangun rumah)

- **Architect** merancang: denah, aliran ruangan, efisiensi ruang (CT)
- **Constructor** mengimplementasikan: memilih material, teknik bangunan, tools (Programming)
- **Same logic** (rencana), **different implementation** (tools & materials)

---

## Key Insight: CT adalah Universal, Programming adalah Tool-Specific

### CT (Mindset, Universal)
- Berlaku untuk semua problems: math, sains, bisnis, seni, dll
- Bisa dilakukan tanpa komputer (unplugged)
- Fokus pada: **BAGAIMANA berpikir tentang problem**
- Output: Algoritma (pseudocode, flowchart, rencana)

**Contoh CT tanpa komputer**:
```
Problem: Saya ingin membuat sandwich tapi tangan penuh barang

CT Solution (Algorithm):
1. Letakkan barang aman di tempat
2. Ambil roti, buka wrapper
3. Ambil topping (telur, lettuce, dll) dari fridge
4. Urutkan topping by logis (bread → spread → protein → veggies → bread)
5. Potong diagonal untuk aesthetic
6. Sajikan

CT principles digunakan (dekomposisi, sequencing, abstraction)
TANPA KOMPUTER!
```

### Programming (Tool-Specific, Implementation)
- Spesifik ke bahasa/tool yang dipilih (Python, Java, JavaScript, Snap!, dll)
- Memerlukan komputer/interpreter untuk run
- Fokus pada: **BAGAIMANA mengekspresikan logic dalam syntax yang benar**
- Output: Kode yang executable oleh mesin

**Contoh Programming** (dalam Python):
```python
# Python ini adalah IMPLEMENTATION dari algorithm search
def linear_search(list, target):
    for i in range(len(list)):
        if list[i] == target:
            return i
    return -1

# Tapi LOGIC di balik ini sama seperti pseudocode CT
```

---

## Abstraction Levels dalam Computing

Setiap layer punya own language & abstraction:

```
┌──────────────────────────────┐
│  Aplikasi (e.g., Gmail)      │ ← User interacts here
├──────────────────────────────┤
│  Programming Language        │ ← Python, JavaScript, Java
│  (High-level abstraction)    │ (Programmer writes here)
├──────────────────────────────┤
│  Machine Code                │ ← 0s and 1s (Low-level)
│  (CPU understands this)      │
└──────────────────────────────┘
```

**Contoh**:
- **High-level** (Python): `print("Hello")` — easy to read
- **Low-level** (Assembly): `mov eax, [ebp+8]; call printf` — hard to read
- **Machine** (Binary): `11001010 10111010 00110010` — incomprehensible to humans

**Key Point**: Regardless of language, **underlying logic (CT) is same!**

---

## Same Logic, Different Tools

### Problem: Find Maximum Number in List

#### Solution 1: CT Pseudocode (Language-Independent)
```
ALGORITHM: Find Max
INPUT: list of numbers
OUTPUT: maximum number

1. Assume first element is max
2. FOR each element in list (starting from 2nd):
     IF element > current_max:
         Update max = element
3. RETURN max
```

#### Solution 2: Python Implementation
```python
def find_max(numbers):
    max_num = numbers[0]
    for num in numbers[1:]:
        if num > max_num:
            max_num = num
    return max_num
```

#### Solution 3: Snap! Block Implementation
```
[set [max] to (item 1 of [list])]
[repeat (length of [list]) - 1]
    [if (item [i] of [list]) > [max]]
        [set [max] to (item [i] of [list])]
```

#### Solution 4: JavaScript Implementation
```javascript
function findMax(numbers) {
    let max = numbers[0];
    for (let i = 1; i < numbers.length; i++) {
        if (numbers[i] > max) {
            max = numbers[i];
        }
    }
    return max;
}
```

**Observation**: **Semua solusi punya SAME LOGIC**, hanya expression-nya berbeda!

---

## Why Learn Both CT and Programming?

### CT Gives You...
- **Universality** — think systematically about ANY problem
- **Foundation** — understanding logic before syntax
- **Transferability** — skills apply across languages

### Programming Gives You...
- **Concrete Skills** — ability to actually CODE
- **Practical Experience** — debugging, testing, real-world challenges
- **Career Readiness** — industry demands coding skills

**Both are necessary!** CT tanpa programming = beautiful ideas tapi tidak implementable. Programming tanpa CT = code yang works tapi tidak elegant/efficient.

---

## How We'll Bridge CT to Programming

### Progression dalam Modul 2:

```
Week 1:
  CT pseudocode & flowcharts → understand logic independent of tool

Week 2-3:
  CT logic → Snap! blocks → see same logic in visual form
  Easier to learn programming basics (sequence, loop, conditional)

Week 4-5:
  Same logic → Python code → learn syntax & professional programming
  By now, logic is clear, only syntax is new
```

### Side-by-Side Comparisons

Setiap algoritma akan ditampilkan dalam:
1. **Pseudocode** (logic tanpa syntax)
2. **Snap! blocks** (visual representation)
3. **Python code** (text-based)

Ini akan help transfer learning between tools.

---

## Practical Example: Bubble Sort

### Step 1: CT Pseudocode (Pure Logic)
```
ALGORITHM: Bubble Sort
INPUT: unsorted list
OUTPUT: sorted list (ascending)

1. REPEAT until list is sorted:
     2. FOR each adjacent pair in list:
         3. IF first > second:
             4. SWAP them
```

### Step 2: Snap! Visual Implementation
```
[set [sorted] to [false]]
[repeat until [sorted]]
    [set [sorted] to [true]]
    [repeat ((length of list) - 1)]
        [if (item [i] of list) > (item [i+1] of list)]
            [swap items [i] and [i+1]]
            [set [sorted] to [false]]
```

### Step 3: Python Implementation
```python
def bubble_sort(arr):
    sorted = False
    while not sorted:
        sorted = True
        for i in range(len(arr) - 1):
            if arr[i] > arr[i+1]:
                arr[i], arr[i+1] = arr[i+1], arr[i]
                sorted = False
    return arr
```

**Notice**: Same algorithm, expressed 3 ways!

---

## Mini-Activity: Translate Between Forms

### Problem: Check if number is Prime

**Pseudocode:**
```
ALGORITHM: Is Prime?
INPUT: number n
OUTPUT: true if prime, false otherwise

1. IF n < 2: RETURN false
2. FOR i from 2 to sqrt(n):
     IF n divisible by i: RETURN false
3. RETURN true
```

**Your task** (optional):
1. Draw this as flowchart
2. Identify which blocks/steps correspond to: sequence, loop, conditional
3. Can you implement this in Python after learning syntax? (Save for later!)

---

## Ringkasan Sub-Modul 2.1

✓ **CT adalah mindset, Programming adalah tool**
✓ **CT principles berlaku universal, programming tools berbeda**
✓ **Same logic dapat diexpress dalam berbagai bahasa/tools**
✓ **Both CT & Programming diperlukan** untuk become effective problem-solver

---

## Selanjutnya

Sub-Modul 2.2 akan introduce **Snap!** — block-based programming yang akan make transition ke programming lebih mudah!

---

**Referensi**
- Beecher 2017 — "Computational Thinking & Programming"
- Code.org Curriculum Philosophy — "Unplugged to Code"
- ISTE/CSTA — Programming Standards
