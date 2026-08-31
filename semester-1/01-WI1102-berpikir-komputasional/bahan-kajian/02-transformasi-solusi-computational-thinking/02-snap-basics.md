# Sub-Modul 2.2: Block-Based Programming dengan Snap!

**Durasi:** 2-2.5 minggu | **Target Bloom Level:** Apply (C3)

---

## Tujuan Pembelajaran

- Memahami interface dan blocks dalam Snap!
- Mengimplementasikan **sequence, loops, conditionals** dalam Snap!
- Menggunakan **variables & data structures** (lists)
- Membuat **programs yang interactive** (respond to user input)
- **Project 1**: Develop game atau interactive story

---

## Apa itu Snap!?

**Snap!** (snap.berkeley.edu) adalah block-based programming platform yang:
- Visual & intuitive — click & drag blocks
- Based on Scratch (lebih powerful)
- Used in UC Berkeley CS Principles curriculum
- FREE & browser-based (no installation needed)

### Why Snap! Sebelum Python?

1. **Lower barrier to entry** — focus on logic, not syntax
2. **Visual** — easier to see program flow
3. **Immediate feedback** — run program sambil coding
4. **Engaging** — create games & animations
5. **Same principles as Python** — transfer ke text-based easier

---

## Getting Started dengan Snap!

### Step 1: Create Account
1. Go to snap.berkeley.edu
2. Click "Create" or "Login"
3. Create account with email

### Step 2: Create New Project
1. Click "New Project"
2. Name project: "My First Snap Program"
3. You'll see:
   - **Sprite** (karakter/objek yang bisa diprogram)
   - **Blocks palette** (berbagai blok untuk program)
   - **Code area** (tempat drag blocks)

### Step 3: Familiarize Yourself
- Drag satu block ke code area
- Click block untuk execute
- Experiment dengan spritenya!

---

## Block Categories dalam Snap!

```
MOTION     → move sprite around (go to, turn, glide)
LOOKS      → appearance (costumes, say, think)
SOUND      → play sounds
PEN        → draw on stage
DATA       → variables & lists
EVENTS     → respond to triggers (click, key press)
CONTROL   → sequence, loops, conditionals
OPERATORS → math, logic, string operations
PROCEDURES → create own blocks (functions)
```

---

## Core Concepts dalam Snap!

### 1. Sequence (Urutan)

**Concept**: Blok-blok dijalankan dari atas ke bawah

```
Blocks:
[Move forward 100 steps]
[Turn right 90 degrees]
[Move forward 100 steps]
[Turn right 90 degrees]

Result: Sprite draws square!
```

**Learning**: Urutan penting. Jika urutan berubah, hasil berubah.

### 2. Loops (Perulangan)

**Concept**: Jalankan blok berkali-kali

#### Repeat Loop
```
[Repeat (4) times]
    [Move forward 100 steps]
    [Turn right 90 degrees]

Result: Same square, tapi lebih efficient code!
```

#### Forever Loop
```
[Forever]
    [Move forward 5 steps]
    [If touching edge, bounce]

Result: Sprite bounces around forever!
```

#### Until Loop
```
[Repeat until (touching [mouse-pointer]?)]
    [Move towards [mouse-pointer]]

Result: Sprite follows your mouse until caught!
```

### 3. Conditionals (If-Else)

**Concept**: Jalankan block hanya jika condition true

```
[If (key [space] pressed?)]
    [Jump up 50 steps]
[Else]
    [Stay where you are]

Result: Space bar triggers jump!
```

### 4. Variables (Penyimpan Data)

**Concept**: Simpan & gunakan data

```
[Set [score] to (0)]
[Repeat until (game over)]
    [If touching [food]]
        [Change [score] by (1)]
        [Say [score]]

Result: Tracker score dalam game!
```

### 5. Lists (Koleksi Data)

**Concept**: Simpan banyak data dalam satu struktur

```
[Set [inventory] to []]
[Add [apple] to [inventory]]
[Add [sword] to [inventory]]
[Add [map] to [inventory]]

[Say [item 1 of [inventory]]]
→ Says: "apple"
```

### 6. Functions/Procedures (Reusable Code)

**Concept**: Buat block sendiri untuk reuse code

```
[Make a block [draw_square]]
  [Repeat (4) times]
    [Move forward 100]
    [Turn right 90]

[Call [draw_square]]
[Move forward 150]
[Call [draw_square]]

Result: Two squares drawn! Code reuse!
```

---

## Hands-On Learning Path untuk Snap!

### Week 1: Basics (Sequence, Loops, Conditionals)

**Activity 1.1**: Make Sprite Move
```
- Click "Motion" block
- [Move forward 10 steps]
- Try different numbers
- What happens?
```

**Activity 1.2**: Draw Square (Repeat Loop)
```
- Repeat 4 times:
  [Move 100]
  [Turn 90]
```

**Activity 1.3**: Follow Mouse (Forever + Conditional)
```
- Forever:
  [Point towards mouse]
  [Move 5 steps]
```

**Activity 1.4**: Bounce Game (Variables + Conditionals)
```
- Set score = 0
- Forever:
  [Move randomly]
  [If touching edge: bounce]
  [If touching food: score + 1]
```

### Week 2: Algorithms (Search, Sort)

**Activity 2.1**: Linear Search dalam List
```
[Make a block [search_list]]
  [Set [found] to false]
  [For each [item] in [list]]
    [If [item] = [target]]
      [Set [found] to true]
```

**Activity 2.2**: Bubble Sort
```
[Make a block [bubble_sort]]
  [Repeat until sorted...]
    [For each adjacent pair...]
      [If pair[i] > pair[i+1]: swap]
```

**Mini-Project 1**: Game atau Interactive Story
- Create character
- Respond to keyboard input
- Keep score/state dengan variables
- Combine motion, conditionals, loops

---

## Common Snap! Patterns

### Pattern 1: Game Loop
```
[Set [game_over] to false]
[Forever]
    [Move player by keyboard input]
    [Move enemies randomly]
    [Check collisions]
    [If collision: set game_over to true]
[Display final score]
```

### Pattern 2: Menu Navigation
```
[Ask [Choose: 1=Play, 2=Instructions, 3=Quit]]
[If answer = 1: call play_game]
[If answer = 2: call show_instructions]
[If answer = 3: stop all]
```

### Pattern 3: Data Management
```
[Create list [players]]
[Create list [scores]]
[Repeat for each player:]
    [Ask player for score]
    [Add score to scores list]
[Sort scores list]
[Display top 3]
```

---

## Debugging dalam Snap!

### Common Issues & Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **Sprite tidak bergerak** | Wrong block type, or block not connected | Check: Motion block? Value > 0? Block highlighted? |
| **Loop infinite** | Loop condition never true | Change condition or add break statement |
| **Variable always 0** | Not incrementing | Check: set vs change block? Inside loop? |
| **Unexpected behavior** | Logic error | Trace through step-by-step, add say() to debug |

### Debugging Strategies

**Strategy 1: Add Debug Output**
```
[Say [score]] ← Show variable value
[Say [reached here]] ← Trace program flow
```

**Strategy 2: Simplify & Test**
- Remove complex parts temporarily
- Test each part individually
- Reintroduce complexity gradually

**Strategy 3: Read Error Messages**
- Snap! gives helpful hints
- Read message carefully
- Usually suggests fix

---

## Ringkasan Sub-Modul 2.2

✓ **Snap! adalah visual way** untuk mengajar programming logic
✓ **Blocks = constructs yang dikelompokan**: Motion, Loops, Conditionals, Variables, dll
✓ **Hands-on learning** lebih baik daripada hanya teori
✓ **Debugging adalah skill** yang harus dipelajari

✓ **Mini-Project 1 (Game/Story)** akan consolidate all skills

---

## Mini-Project 1 Assignment

**Create Game atau Interactive Story**

Requirements:
- Use at least 2 sprites
- Use loops (repeat atau forever)
- Use conditionals (if-else)
- Use variables (untuk track state: score, health, level)
- Respond to keyboard atau mouse input
- Has clear win/lose condition

**Examples**:
- Catch falling food (score increases)
- Avoid obstacles (health decreases)
- Story with branching paths (conditionals)
- Quiz game (check answers, keep score)

**Deliverable**: Submit link ke Snap project + explain your code

---

## Selanjutnya

Sub-Modul 2.3 akan explore **algorithms dalam Snap!** — implement searching, sorting, lebih advanced problems.

---

**Referensi**
- Snap! Documentation: snap.berkeley.edu/help
- UC Berkeley CS Principles: bjc.berkeley.edu
- Code.org: code.org (Courses for reference)
