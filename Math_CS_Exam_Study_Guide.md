# Math & Computer Science Exam: Study Guide

This guide covers every topic from the 20 sample questions. Each section has:
1. **Key ideas**: the formulas and rules you need.
2. **Sample question solved**: the original question, worked step by step.
3. **Practice**: new problems of the same type. **Answers are at the end of the file.**

Do the practice problems without looking, then check your answers.

---

## 0. One-page cheat sheet (read this the morning of the exam)

| Topic | Formula / trick |
|---|---|
| Quadratic | x = (−b ± √(b² − 4ac)) / 2a. Sum of roots = −b/a, product = c/a |
| Exponents | Rewrite both sides with the same base, then set the exponents equal |
| Trig | sin(A+B) = sinA cosB + cosA sinB; cos(A+B) = cosA cosB − sinA sinB |
| "Must be together" | Glue the group into 1 block: (units)! × (inside the block)! |
| Integral | ∫cos = sin, ∫sin = −cos, ∫xⁿ = xⁿ⁺¹/(n+1), ∫1/x = ln x |
| Rank | Number of non-zero rows after row reduction (= number of independent rows) |
| z-score | z = (x − μ) / σ |
| Modular inverse | Try x = 1, 2, 3, … until a·x mod m = 1 |
| Truth table | n variables → 2ⁿ rows. p⇒q is false **only** when p = T, q = F |
| Power set | 2ⁿ subsets |
| Max edges (simple undirected) | n(n−1)/2 |
| Insertion / bubble sort swaps | = number of **inversions** (pairs i<j with a[i] > a[j]) |
| BST depth / height | Longest root-to-leaf path, counted in **edges** (root = depth 0) |
| Min-heap extract-min | The new root is always the **2nd smallest** value |
| Linear probing | Slot taken → try the next one (+1), wrap around with mod m |
| Deadlock-free resources | n processes, each needing m: **n(m − 1) + 1** |
| FIFO paging | Evict the page that was loaded **first** (a queue) |
| NFA → DFA | n NFA states → at most **2ⁿ** DFA states |
| Brute-force subsets | 2ⁿ |

---

## 1. Algebra: quadratics and exponential equations

### Key ideas
- **Quadratic** ax² + bx + c = 0: factor it, or use x = (−b ± √D) / 2a with D = b² − 4ac.
  - D > 0: two real roots. D = 0: one root. D < 0: no real roots.
- "Largest **absolute value**" means you compare |x|, so −3.7 beats 2.5. Watch the sign.
- **Exponential equations**: write both sides as powers of the same base.
  27 = 3³, 9 = 3², 8 = 2³, 4 = 2², 16 = 2⁴, 32 = 2⁵, 125 = 5³.
  Then (aᵐ)ⁿ = aᵐⁿ, so 27^(x−2) = 3^(3(x−2)).
- If the bases can't be matched, take logs: aˣ = b → x = ln b / ln a.
- Log rules: log(ab) = log a + log b; log(aⁿ) = n·log a. Check that the answer keeps the log argument positive.

### Sample questions solved
**Q1.** 2x² − 3x − 5 = 0 → (2x − 5)(x + 1) = 0 → x = 2.5 or x = −1.
|2.5| > |−1|, so the answer is **2.5**.

**Q2.** 3^(x+1) = 27^(x−2) = 3^(3x−6) → x + 1 = 3x − 6 → 2x = 7 → **x = 3.5**.

### Practice
- A1. Find the root of x² − 5x + 6 = 0 with the largest absolute value.
- A2. Find the root of 3x² + 2x − 8 = 0 with the largest absolute value (one decimal place).
- A3. Find the root of x² + 4x + 1 = 0 with the largest absolute value (one decimal place).
- A4. Solve 2^(x+3) = 8^(x−1).
- A5. Solve 4ˣ = 2^(x+5).
- A6. Solve 9^(x−1) = 27^(x−3).
- A7. Solve 5ˣ = 20 (one decimal place).
- A8. Solve log₂(x) + log₂(x − 2) = 3.
- A9. Without solving, find the sum and the product of the roots of 2x² − 3x − 5 = 0.

---

## 2. Trigonometry

### Key ideas
**Values to memorize**

| angle | 0° | 30° | 45° | 60° | 90° |
|---|---|---|---|---|---|
| sin | 0 | 1/2 | √2/2 | √3/2 | 1 |
| cos | 1 | √3/2 | √2/2 | 1/2 | 0 |
| tan | 0 | √3/3 | 1 | √3 | undefined |

(Trick: sin goes √0/2, √1/2, √2/2, √3/2, √4/2; cos is the same list backwards.)

**Identities**
- sin(A ± B) = sinA cosB ± cosA sinB
- cos(A ± B) = cosA cosB ∓ sinA sinB  (note the sign flips)
- sin 2A = 2 sinA cosA;  cos 2A = cos²A − sin²A
- sin²A + cos²A = 1;  tan A = sinA / cosA
- sin(90° − A) = cos A;  cos(90° − A) = sin A
- Radians: π rad = 180°, so degrees × π/180.

**Pattern recognition**: if you see "sin·cos + cos·sin", it's sin(A+B). If you see "cos·cos − sin·sin", it's cos(A+B).

### Sample question solved
**Q3.** sin30° cos60° + cos30° sin60° has the pattern sinA cosB + cosA sinB = sin(A + B) = sin 90° = **1**.
Check with values: (1/2)(1/2) + (√3/2)(√3/2) = 1/4 + 3/4 = 1 ✓

### Practice
- B1. cos45° cos15° − sin45° sin15°
- B2. sin50° cos20° − cos50° sin20°
- B3. 2 sin15° cos15°
- B4. cos²22.5° − sin²22.5° (one decimal place, or exact)
- B5. tan45° + sin²30°
- B6. Solve sin x = 1/2 for 0° ≤ x < 360°.
- B7. Convert 135° to radians.
- B8. Simplify sin²(40°) + cos²(40°).

---

## 3. Combinatorics (counting)

### Key ideas
- n distinct items in a row: **n!**
- Choose k from n, order doesn't matter: **C(n,k) = n! / (k!(n−k)!)**
- Order matters: **P(n,k) = n! / (n−k)!**
- Repeated letters: n! / (a!·b!·…) where a, b, … are the repeat counts.
- Circular arrangements: (n − 1)!
- **"Must be together"**: glue the group into one block.
  Count the block as 1 unit, arrange the units, then multiply by the ways to arrange things **inside** the block.
- **"Must NOT be together"** = total − (together).

### Sample question solved (and why it works)
**Q4.** 8 books, 3 specific books must be together.

1. Tape the 3 books together into one "super-book".
2. Now there are 8 − 3 + 1 = **6 units** (5 single books + 1 block). They can be arranged in **6! = 720** ways.
3. Inside the block, the 3 books can be in any order: **3! = 6** ways (ABC, ACB, BAC, BCA, CAB, CBA).
4. Each block order combines with each arrangement of the units, so we **multiply**: 720 × 6 = **4320**.

Why multiply? For each of the 720 shelf layouts, you still get to choose 1 of 6 internal orders. That's 720 groups of 6.

### Practice
- C1. 6 people stand in a line. 2 specific people must stand together. How many ways?
- C2. Same as C1, but those 2 must **not** stand together.
- C3. 7 books, 3 specific books together **in a fixed order**.
- C4. How many distinct arrangements of the letters in BANANA?
- C5. How many 3-person committees can be chosen from 10 people?
- C6. 5 people sit at a round table. How many arrangements?
- C7. 8 books. Group X (3 books) must be together and group Y (2 other books) must be together.

---

## 4. Calculus: definite integrals and derivatives

### Key ideas
**Fundamental theorem**: ∫ₐᵇ f(x) dx = F(b) − F(a), where F′ = f.

| f(x) | antiderivative F(x) |
|---|---|
| xⁿ (n ≠ −1) | xⁿ⁺¹ / (n+1) |
| 1/x | ln\|x\| |
| eˣ | eˣ |
| cos x | sin x |
| sin x | −cos x |

**Derivatives**: (xⁿ)′ = n·xⁿ⁻¹, (sin x)′ = cos x, (cos x)′ = −sin x, (eˣ)′ = eˣ, (ln x)′ = 1/x.
Product rule: (uv)′ = u′v + uv′. Chain rule: (f(g(x)))′ = f′(g(x))·g′(x).

### Sample question solved
**Q5.** ∫₀^(π/2) cos x dx = [sin x]₀^(π/2) = sin(π/2) − sin 0 = 1 − 0 = **1**.

### Practice
- D1. ∫₀^π sin x dx
- D2. ∫₀¹ x² dx
- D3. ∫₀^π cos x dx
- D4. ∫₁^e (1/x) dx
- D5. ∫₀² (3x² + 1) dx
- D6. Differentiate x²eˣ.
- D7. ∫₀^(π/2) sin x cos x dx (hint: sin x cos x = ½ sin 2x, or substitute u = sin x)

---

## 5. Linear algebra

### Key ideas
- **Rank** = number of linearly independent rows (equivalently, columns).
  How to find it: row-reduce to echelon form and count the non-zero rows.
  - Quick check: if one row is a multiple of another, or a sum of others, it's dependent.
  - For an n×n matrix: det ≠ 0 ⟺ rank = n (full rank, invertible).
- **Determinant**
  - 2×2: det[[a, b], [c, d]] = ad − bc
  - 3×3: expand along the first row: a(ei − fh) − b(di − fg) + c(dh − eg)
- **Inverse 2×2**: (1/det)·[[d, −b], [−c, a]]
- **Eigenvalues**: solve det(A − λI) = 0. For 2×2: λ² − (trace)λ + det = 0.
  Diagonal or triangular matrix → the eigenvalues are the diagonal entries.

### Sample question solved
**Q6.** Rows (1 2 3), (2 4 6), (0 1 1).
Row 2 = 2 × Row 1, so it adds nothing new. Rows 1 and 3 are not multiples of each other.
R2 − 2R1 = (0 0 0) → two non-zero rows remain → **rank 2**.

### Practice
- E1. Rank of the matrix with rows (1 2), (3 6).
- E2. Rank of the matrix with rows (1 0 1), (0 1 1), (1 1 2).
- E3. Rank of the matrix with rows (1 2 3), (4 5 6), (7 8 9).
- E4. det [[2, 1], [5, 3]]
- E5. det [[1, 2, 3], [0, 1, 4], [5, 6, 0]]
- E6. Eigenvalues of [[4, 1], [2, 3]].
- E7. Inverse of [[2, 1], [5, 3]].
- E8. Rank of the 3×3 identity matrix? Of the 3×3 zero matrix?

---

## 6. Statistics and probability

### Key ideas
- Mean μ = Σx / n. Median = middle value of the sorted data (average the two middle values if n is even).
- Variance σ² = Σ(x − μ)² / n (population) or / (n − 1) (sample). Standard deviation σ = √variance.
- **z-score**: z = (x − μ) / σ = "how many standard deviations from the mean". Negative means below the mean.
  Reverse it: x = μ + z·σ.
- Empirical rule (normal distribution): about 68% of data lies within ±1σ, 95% within ±2σ, 99.7% within ±3σ.
- Transformations: adding c to every value shifts the mean by c and leaves σ unchanged. Multiplying by k multiplies both the mean and σ by |k|.
- Probability = favourable outcomes / total outcomes (for equally likely outcomes).

### Sample question solved
**Q7.** z = (8 − 10) / 2 = **−1** (one standard deviation below the mean).

### Practice
- F1. μ = 50, σ = 5. z-score of x = 60?
- F2. μ = 100, σ = 15. Which x has z = −1.5?
- F3. Data: 2, 4, 4, 4, 5, 5, 7, 9. Find the mean and the population standard deviation.
- F4. Median of 3, 7, 1, 9, 5, 8.
- F5. Normal data, μ = 70, σ = 10. About what percent of the values lie between 50 and 90?
- F6. Every value in a dataset (μ = 10, σ = 2) is multiplied by 3 and then increased by 5. New mean and new σ?
- F7. Two fair dice are rolled. P(sum = 7)?

---

## 7. Number theory: modular arithmetic

### Key ideas (explained slowly)
- **a mod m** = the remainder when a is divided by m. Example: 17 mod 5 = 2 (because 17 = 3·5 + 2).
  Negative numbers: add m until the result is in 0…m−1. −3 mod 7 = 4.
- **a ≡ b (mod m)** reads "a is congruent to b mod m" and means a and b leave the **same remainder** when divided by m.
- **4x ≡ 1 (mod 7)** asks: *which x makes 4x leave remainder 1 when divided by 7?*
  That x is called the **modular inverse** of 4 mod 7.
- An inverse exists **only if gcd(a, m) = 1**. Example: 6x ≡ 1 (mod 9) has no solution, because 6x is always a multiple of 3 and so can never be 1 more than a multiple of 9.
- **Method 1, trial (fastest for small m)**: try x = 1, 2, …, m−1 and compute a·x mod m.
- **Method 2, shortcut**: find a number of the form 1 + k·m (that's 1, 8, 15, 22, 29, … for m = 7) that a divides.
- **Solving ax ≡ b (mod m)**: find the inverse of a, then x ≡ b · inverse (mod m).
- Big powers: find a small power that is ≡ 1, then reduce. E.g. 2³ = 8 ≡ 1 (mod 7).

### Sample question solved
**Q8.** 4x ≡ 1 (mod 7)

| x | 4x | 4x mod 7 |
|---|---|---|
| 1 | 4 | 4 |
| 2 | 8 | **1** ✓ |

So **x = 2**. Check: 4·2 = 8 = 7 + 1 → remainder 1 ✓
(Shortcut: the numbers 1, 8, 15, … are ≡ 1 mod 7. 8 is divisible by 4 → x = 8/4 = 2.)

### Practice
- G1. Smallest positive x with 3x ≡ 1 (mod 7).
- G2. Smallest positive x with 5x ≡ 1 (mod 11).
- G3. Smallest positive x with 2x ≡ 3 (mod 5).
- G4. Smallest positive x with 7x ≡ 1 (mod 26).
- G5. Solve 6x ≡ 1 (mod 9).
- G6. Compute 17 mod 5 and −3 mod 7.
- G7. Compute 2¹⁰ mod 7.
- G8. Solve 3x ≡ 2 (mod 7).

---

## 8. Propositional logic: truth tables

### Key ideas
- n variables → **2ⁿ rows** (2 vars: 4, 3 vars: 8, 4 vars: 16).
- **p ⇒ q is false ONLY when p = T and q = F.** Every other row is true.
- p ⇔ q is true when p and q are equal. p ⊕ q (XOR) is true when they differ.
- p ⇒ q ≡ ¬p ∨ q;  ¬(p ⇒ q) ≡ p ∧ ¬q;  De Morgan: ¬(p ∧ q) ≡ ¬p ∨ ¬q.
- **Counting trick**: count the rows that make the formula **false** (usually fewer), then subtract from 2ⁿ.

### Sample question solved
**Q9.** (p ⇒ q) ∧ (q ⇒ r), 3 variables, 8 rows.
The formula is false when either part is false:
- p ⇒ q is false when p = T, q = F (r is free): **2 rows**
- q ⇒ r is false when q = T, r = F (p is free): **2 rows**
- No overlap (q can't be both F and T).

True rows = 8 − 4 = **4**: (F,F,F), (F,F,T), (F,T,T), (T,T,T).
Pattern: a chain of implications is true when the values never go "T then F" along the chain.

### Practice (count rows that are True)
- H1. p ∧ q (2 variables)
- H2. p ∨ q ∨ r (3 variables)
- H3. p ⇒ q (2 variables)
- H4. (p ⇒ q) ∧ (q ⇒ p) (2 variables)
- H5. (p ∧ q) ⇒ r (3 variables)
- H6. (p ∨ q) ∧ ¬r (3 variables)
- H7. p ⊕ q ⊕ r (3 variables)
- H8. Which formula without "⇒" is equivalent to ¬(p ⇒ q)?

---

## 9. Set theory

### Key ideas
- Power set P(S) = the set of all subsets. |P(S)| = **2ⁿ** (each element is either in or out: 2 × 2 × … × 2).
- Subsets with exactly k elements: C(n, k). Proper subsets: 2ⁿ − 1.
- Inclusion–exclusion: |A ∪ B| = |A| + |B| − |A ∩ B|.
- Cartesian product: |A × B| = |A|·|B|.

### Sample question solved
**Q10.** {a, b, c, d} has 4 elements → 2⁴ = **16** subsets (this count includes ∅ and the set itself).

### Practice
- I1. Number of elements in the power set of a 5-element set.
- I2. Number of 2-element subsets of {1, 2, 3, 4, 5, 6}.
- I3. |A| = 10, |B| = 8, |A ∩ B| = 3. Find |A ∪ B|.
- I4. Number of proper subsets of {a, b, c}.
- I5. Number of subsets of {a, b, c, d, e} that contain a.
- I6. |A| = 3, |B| = 4. Find |A × B|.

---

## 10. Graph theory and minimum spanning trees

### Key ideas
- Simple undirected graph (no loops, no multi-edges): max edges = **C(n,2) = n(n−1)/2**. Directed (no loops): n(n−1).
- **Handshake lemma**: sum of degrees = 2 × (number of edges), so the sum of degrees must be even.
- A **tree** with n vertices has exactly **n − 1 edges**.
- **MST with Kruskal's algorithm** (best for exam pictures):
  1. List all edges sorted by weight, smallest first.
  2. Take each edge **unless it creates a cycle**.
  3. Stop when you have n − 1 edges. Add up the weights.
- **Prim's algorithm**: start at any vertex and repeatedly add the cheapest edge that leaves the tree you have built so far.

### Sample questions solved
**Q11.** n = 5 → 5·4/2 = **10** edges.

**Q16 (image).** Use Kruskal on the picture: sort the edges, skip any edge whose two ends are already connected, stop at n − 1 edges, and sum. Practice it on J6 and J8.

### Practice
- J1. Max edges in a simple undirected graph with 8 vertices.
- J2. Number of edges in the complete graph K₆.
- J3. Number of edges in a tree with 10 vertices.
- J4. A graph has 12 edges. What is the sum of all its vertex degrees?
- J5. Can a graph have 5 vertices, each of degree 3? Why?
- J6. MST weight. Vertices A, B, C, D. Edges: A–B 1, B–C 4, A–C 3, C–D 2, B–D 5.
- J7. Max edges in a directed graph with 5 vertices (no self-loops).
- J8. MST weight. Vertices A–E. Edges: A–B 2, A–C 3, B–C 1, B–D 4, C–D 5, C–E 6, D–E 2.

---

## 11. Sorting algorithms

### Key ideas
- An **inversion** is a pair (i < j) with a[i] > a[j]. Each adjacent swap fixes exactly one inversion, so
  **insertion sort swaps = bubble sort swaps = number of inversions**.
- How to count inversions: for each element, count how many elements **to its right are smaller**, then add them up.
- Already sorted → 0 swaps. Reversed list of n items → n(n−1)/2 swaps.

| Algorithm | Best | Average | Worst | Stable? |
|---|---|---|---|---|
| Bubble | O(n) | O(n²) | O(n²) | yes |
| Insertion | O(n) | O(n²) | O(n²) | yes |
| Selection | O(n²) | O(n²) | O(n²) | no |
| Merge | O(n log n) | O(n log n) | O(n log n) | yes |
| Quick | O(n log n) | O(n log n) | O(n²) | no |
| Heap | O(n log n) | O(n log n) | O(n log n) | no |

### Sample question solved
**Q12.** [4, 2, 7, 1, 3]
- 4: smaller ones to its right are 2, 1, 3 → 3
- 2: 1 → 1
- 7: 1, 3 → 2
- 1: none → 0
- 3: none → 0

Total = 3 + 1 + 2 = **6 swaps**.

### Practice (adjacent swaps by insertion sort, ascending)
- K1. [3, 1, 2]
- K2. [5, 4, 3, 2, 1]
- K3. [1, 2, 3, 4, 5]
- K4. [2, 4, 1, 3, 5]
- K5. [6, 5, 8, 3, 1]
- K6. Which of bubble, insertion, selection, merge, quick, and heap sort has worst case O(n log n)?

---

## 12. Binary search trees

### Key ideas
- Insert: smaller → go left, larger → go right, until you reach an empty spot.
- **Depth of a node** = number of edges from the root (root depth = 0).
  **Depth/height of the tree** = the largest node depth.
  *Some exams count levels instead (root = level 1), which gives height + 1. Read the question carefully. Most CS courses count edges.*
- Max nodes in a binary tree of height h: 2^(h+1) − 1. Min height for n nodes: ⌊log₂ n⌋.
- Traversals: **In**order = Left, Root, Right (gives the values in sorted order). **Pre**order = Root, L, R. **Post**order = L, R, Root.
- Inserting values that are already sorted gives a "chain", whose height is n − 1.

### Sample question solved
**Q13.** Insert 5, 3, 7, 2, 4, 6, 8:
```
        5          depth 0
      /   \
     3     7       depth 1
    / \   / \
   2   4 6   8     depth 2
```
Depth = **2** (counting edges). If counted as levels, it's 3.

### Practice
- L1. Height of the BST built from 10, 5, 15, 3, 7, 12, 20.
- L2. Height of the BST built from 1, 2, 3, 4, 5.
- L3. Height of the BST built from 50, 30, 70, 20, 40, 60, 80, 10.
- L4. Inorder traversal of the tree in L1.
- L5. Preorder and postorder traversal of the tree in Q13.
- L6. Max number of nodes in a binary tree of height 3.

---

## 13. Heaps

### Key ideas
- **Min-heap**: every parent ≤ its children, so the minimum is at the root. (Max-heap is the reverse.)
- Array storage (0-indexed): children of i are 2i+1 and 2i+2; parent of i is ⌊(i−1)/2⌋.
- **Extract-min**: remove the root, move the **last** element to the root, then **sift down**: swap it with its **smaller** child while it is bigger than that child.
- **Insert**: put the new value at the end, then **sift up**: swap with the parent while it is smaller than the parent.
- **Exam trick**: after extract-min, the new root is always the **second-smallest value** in the original heap (assuming distinct values). For a max-heap it's the second-largest.

### Sample question solved
**Q14 (image).** Whatever the picture, the new root = the 2nd smallest value. Example heap [1, 3, 2, 7, 4, 5, 6]:
- Remove 1, move the last element (6) to the root: [6, 3, 2, 7, 4, 5]
- 6 vs children 3, 2 → swap with 2: [2, 3, 6, 7, 4, 5]
- 6 vs child 5 → swap: [2, 3, 5, 7, 4, 6]. New root = **2** ✓ (the 2nd smallest)

### Practice
- M1. Min-heap [1, 3, 2, 7, 4, 5, 6]: give the full array after one extract-min.
- M2. Insert 0 into the min-heap [1, 3, 2, 7, 4, 5, 6]. Give the resulting array.
- M3. Is [2, 5, 3, 9, 6, 4] a valid min-heap?
- M4. Max-heap [9, 7, 8, 3, 5, 6]: what is the new root after extract-max?
- M5. In a 0-indexed heap array, what are the children of index 4, and what is its parent?

---

## 14. Hashing

### Key ideas
- h(k) = k mod m gives the home slot.
- **Linear probing**: if the slot is full, try h+1, h+2, …, all mod m (so the search **wraps around** to 0).
- **Quadratic probing**: try h+1², h+2², h+3², … (mod m).
- **Chaining**: each slot holds a list, and colliding keys are appended to it.
- Load factor α = n / m (keys / slots).

### Sample question solved
**Q15.** m = 7, keys 10, 17, 3, 24
- 10 mod 7 = 3 → slot 3
- 17 mod 7 = 3 → taken → slot 4
- 3 mod 7 = 3 → 3, 4 taken → slot 5
- 24 mod 7 = 3 → 3, 4, 5 taken → **slot 6**

### Practice
- N1. m = 7, linear probing, keys 15, 22, 29. Where is 29 stored?
- N2. m = 10, linear probing, keys 23, 43, 13, 27. Where is 13 stored?
- N3. m = 7, linear probing, keys 5, 12, 6. Where is 6 stored?
- N4. m = 7, quadratic probing, keys 10, 17, 24. Where is 24 stored?
- N5. m = 5, chaining, keys 1, 6, 11, 3. How many keys are in the longest chain?
- N6. Load factor with 4 keys in 7 slots.

---

## 15. Operating systems: deadlock, paging, scheduling

### 15a. Deadlock-avoidance resource count
**Formula**: n processes each needing at most m units → minimum resources that guarantee no deadlock = **n(m − 1) + 1**.

**Why**: the worst case is that every process holds m − 1 units and waits for one more, so all are stuck. That uses n(m − 1) units. With just **one more** unit, some process can finish and release its units, and the rest follow.

**Q17.** 3 processes, each needs 4: 3 × 3 + 1 = **10**.

### 15b. Page replacement
- **FIFO**: evict the page that has been in memory the longest (first in, first out).
- **LRU**: evict the page that was used least recently.
- **OPT (optimal)**: evict the page that will be needed furthest in the future.
- A **hit** (page already in memory) changes nothing in FIFO. In LRU a hit refreshes the page.
- **Belady's anomaly**: with FIFO, adding more frames can cause **more** faults.

**Q18, slowly.** 4 frames, string 1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5, using FIFO. Think of the frames as a queue: new pages join on the right and the leftmost page is evicted.

| Ref | Queue (oldest → newest) | Fault? |
|---|---|---|
| 1 | 1 | F |
| 2 | 1 2 | F |
| 3 | 1 2 3 | F |
| 4 | 1 2 3 4 | F |
| 1 | 1 2 3 4 | hit |
| 2 | 1 2 3 4 | hit |
| 5 | 2 3 4 5 (evict 1) | F |
| 1 | 3 4 5 1 (evict 2) | F |
| 2 | 4 5 1 2 (evict 3) | F |
| 3 | 5 1 2 3 (evict 4) | F |
| 4 | 1 2 3 4 (evict 5) | F |
| 5 | 2 3 4 5 (evict 1) | F |

Faults = **10**. (With only 3 frames, FIFO gives 9. That's Belady's anomaly.)

### 15c. CPU scheduling
- Waiting time = start time − arrival time (for non-preemptive scheduling). Turnaround = finish − arrival.
- **FCFS** runs jobs in arrival order. **SJF** runs the shortest job first (this minimizes average waiting time). **Round Robin** gives each job a fixed time slice q in turn.

### Practice
- O1. 4 processes, each needs 3 units. Minimum resources that guarantee no deadlock?
- O2. 5 processes, each needs 2 units. Same question.
- O3. 6 units are available and each process needs 3. Max number of processes that guarantees no deadlock?
- O4. FIFO with 3 frames, string 1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5. Number of faults?
- O5. LRU with 4 frames on the same string as O4. Number of faults?
- O6. String 7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2, 1, 2, 0, 1, 7, 0, 1 with 3 frames. Faults under FIFO, LRU, and OPT?
- O7. Jobs arrive at time 0 with bursts 24, 3, 3 (in that order). Average waiting time under FCFS and under SJF?

---

## 16. Automata: NFA → DFA

### Key ideas
- **Subset construction**: each DFA state is a **set** of NFA states.
- An NFA with n states has 2ⁿ subsets, so the DFA has **at most 2ⁿ states** (this counts the empty set, which acts as a "dead" state).
- In practice you usually get fewer, because only the reachable subsets are built.
- DFA accepting states = the subsets that contain at least one NFA accepting state.
- Minimal DFA examples: binary strings with an even number of 0s → 2 states. Strings ending in "01" → 3 states.

### Sample question solved
**Q19.** 3 NFA states → 2³ = **8** possible DFA states.

### Practice
- P1. An NFA has 5 states. Max DFA states after subset construction?
- P2. How many binary strings of length 4 are there?
- P3. How many strings of length 3 over {a, b} contain at least one a?
- P4. Minimal number of DFA states for "binary strings with an even number of 0s".
- P5. Minimal number of DFA states for "binary strings ending in 01".

---

## 17. Complexity and brute force

### Key ideas
- Number of subsets of n items: 2ⁿ. Permutations: n!. Pairs: C(n, 2).
- Growth order: 1 < log n < n < n log n < n² < n³ < 2ⁿ < n!
- Useful powers: 2¹⁰ = 1024, 2²⁰ = 1,048,576, 2³⁰ ≈ 1.07 billion.
- Binary search on n items: at most ⌈log₂(n+1)⌉ comparisons.
- Loops: two nested loops over n → O(n²). A loop where i doubles (i *= 2) → O(log n).
- Master theorem examples: T(n) = 2T(n/2) + n → O(n log n) (merge sort). T(n) = T(n/2) + 1 → O(log n) (binary search).

### Sample question solved
**Q20.** 2²⁰ = **1,048,576** subsets.

### Practice
- Q1. Number of permutations of 10 items.
- Q2. Number of subsets of 30 items (approximately).
- Q3. Max comparisons for binary search on 1,000,000 sorted items.
- Q4. Order these from slowest to fastest growing: n², 2ⁿ, n log n, log n, n!, n.
- Q5. Time complexity of `for i in 1..n: for j in 1..n: ...`, and of `i = 1; while i < n: i *= 2`.
- Q6. Solve T(n) = 2T(n/2) + n.
- Q7. Number of pairs that a brute-force algorithm checks among 20 items.

---

## 18. Bonus: number systems (often on CS exams)
- Binary → decimal: 1011₂ = 8 + 0 + 2 + 1 = 11.
- Decimal → binary: divide by 2 repeatedly and read the remainders from bottom to top. 25 = 11001₂.
- Hex: FF₁₆ = 15·16 + 15 = 255. Each hex digit = 4 bits.
- Two's complement of −5 in 8 bits: 5 = 00000101 → flip the bits → 11111010 → add 1 → **11111011**.

Practice: X1. 110110₂ to decimal. X2. 45 to binary. X3. 2A₁₆ to decimal. X4. −3 in 8-bit two's complement.

---

# ANSWER KEY

**Original 20:** 1) 2.5 · 2) 3.5 · 3) 1 · 4) 4320 · 5) 1 · 6) 2 · 7) −1 · 8) 2 · 9) 4 · 10) 16 · 11) 10 · 12) 6 · 13) 2 · 14) the 2nd-smallest value in the heap · 15) 6 · 16) use Kruskal on the picture · 17) 10 · 18) 10 · 19) 8 · 20) 1,048,576

**1. Algebra**
A1) roots 2, 3 → **3** · A2) roots 4/3 ≈ 1.3 and −2 → **−2.0** · A3) −2 ± √3 = −0.27, −3.73 → **−3.7** · A4) x + 3 = 3x − 3 → **3** · A5) 2x = x + 5 → **5** · A6) 2x − 2 = 3x − 9 → **7** · A7) ln20/ln5 ≈ **1.9** · A8) x(x−2) = 8 → x = 4 (x = −2 rejected) → **4** · A9) sum **3/2**, product **−5/2**

**2. Trigonometry**
B1) cos60° = **1/2** · B2) sin30° = **1/2** · B3) sin30° = **1/2** · B4) cos45° = **√2/2 ≈ 0.7** · B5) 1 + 1/4 = **1.25** · B6) **30°, 150°** · B7) **3π/4** · B8) **1**

**3. Combinatorics**
C1) 5!·2! = **240** · C2) 720 − 240 = **480** · C3) 5!·1 = **120** · C4) 6!/(3!2!) = **60** · C5) **120** · C6) 4! = **24** · C7) 5 units: 5!·3!·2! = **1440**

**4. Calculus**
D1) [−cos x]₀^π = 1 + 1 = **2** · D2) **1/3** · D3) **0** · D4) ln e − ln 1 = **1** · D5) [x³ + x]₀² = **10** · D6) **eˣ(x² + 2x)** · D7) **1/2**

**5. Linear algebra**
E1) **1** · E2) row 3 = row 1 + row 2 → **2** · E3) row 3 − row 2 = row 2 − row 1 → **2** · E4) 6 − 5 = **1** · E5) −24 + 40 − 15 = **1** · E6) λ² − 7λ + 10 = 0 → **5, 2** · E7) **[[3, −1], [−5, 2]]** · E8) **3** and **0**

**6. Statistics**
F1) **2** · F2) 100 − 22.5 = **77.5** · F3) mean **5**, Σ(x−μ)² = 32, 32/8 = 4 → σ = **2** (sample s ≈ 2.14) · F4) (5 + 7)/2 = **6** · F5) ±2σ → **≈95%** · F6) mean 3·10 + 5 = **35**, σ = 3·2 = **6** · F7) 6/36 = **1/6**

**7. Modular arithmetic**
G1) 3·5 = 15 → **5** · G2) 5·9 = 45 → **9** · G3) 2·4 = 8 ≡ 3 → **4** · G4) 7·15 = 105 = 4·26 + 1 → **15** · G5) gcd(6, 9) = 3 → **no solution** · G6) **2** and **4** · G7) 2³ ≡ 1, so 2¹⁰ = (2³)³·2 ≡ **2** · G8) inverse of 3 is 5 → x ≡ 10 ≡ **3** (check: 9 ≡ 2 ✓)

**8. Logic**
H1) **1** · H2) only FFF is false → **7** · H3) **3** · H4) **2** · H5) only TTF is false → **7** · H6) 3 ways for p∨q × (r = F) → **3** · H7) an odd number of Ts → **4** · H8) **p ∧ ¬q**

**9. Sets**
I1) **32** · I2) C(6,2) = **15** · I3) 10 + 8 − 3 = **15** · I4) **7** · I5) 2⁴ = **16** · I6) **12**

**10. Graphs**
J1) **28** · J2) **15** · J3) **9** · J4) **24** · J5) **No**: the degree sum would be 15, which is odd · J6) A–B 1, C–D 2, A–C 3 → **6** · J7) **20** · J8) B–C 1, A–B 2, D–E 2, (A–C 3 skipped: cycle), B–D 4 → **9**

**11. Sorting**
K1) **2** · K2) **10** · K3) **0** · K4) (2,1), (4,1), (4,3) → **3** · K5) 3 + 2 + 2 + 1 → **8** · K6) **merge and heap sort**

**12. BST**
L1) **2** · L2) **4** (a chain) · L3) 10 hangs below 20 → **3** · L4) **3, 5, 7, 10, 12, 15, 20** · L5) pre: **5, 3, 2, 4, 7, 6, 8**; post: **2, 4, 3, 6, 8, 7, 5** · L6) 2⁴ − 1 = **15**

**13. Heaps**
M1) **[2, 3, 5, 7, 4, 6]** · M2) **[0, 1, 2, 3, 4, 5, 6, 7]** · M3) **Yes** · M4) **8** (array becomes [8, 7, 6, 3, 5]) · M5) children **9 and 10**, parent **1**

**14. Hashing**
N1) slots 1, 2, 3 → **3** · N2) slots 3, 4, 5 → **5** · N3) 6 is taken by 12 → wraps to **0** · N4) 3 → 3+1 = 4 (taken) → 3+4 = 7 mod 7 = **0** · N5) bucket 1 holds 1, 6, 11 → **3** · N6) 4/7 ≈ **0.57**

**15. OS**
O1) 4·2 + 1 = **9** · O2) 5·1 + 1 = **6** · O3) 2n + 1 ≤ 6 → **2** · O4) **9** · O5) **8** · O6) FIFO **15**, LRU **12**, OPT **9** · O7) FCFS: (0 + 24 + 27)/3 = **17**; SJF: (0 + 3 + 6)/3 = **3**

**16. Automata**
P1) **32** · P2) **16** · P3) 8 − 1 = **7** · P4) **2** · P5) **3**

**17. Complexity**
Q1) **3,628,800** · Q2) 2³⁰ ≈ **1.07 billion** · Q3) **20** · Q4) **log n, n, n log n, n², 2ⁿ, n!** · Q5) **O(n²)** and **O(log n)** · Q6) **O(n log n)** · Q7) C(20,2) = **190**

**18. Number systems**
X1) 32 + 16 + 4 + 2 = **54** · X2) **101101** · X3) 2·16 + 10 = **42** · X4) **11111101**
