# DSA-Sorting . 

All dsa sorting in one repository for  quick revision .

hum **interview-oriented Sorting** karte hain — sirf code nahi, balki **konsi sorting kab use hoti hai + example + interview questions**.

# 🔥 DSA Sorting — Interview ke liye Important

Sorting ko broadly 2 tarah se samjho:

* **Basic sorting:** Bubble, Selection, Insertion
* **Efficient sorting:** Merge, Quick, Heap
* **Special case:** Counting Sort
* **Practical C++:** `sort()`

---

## 1️⃣ Bubble Sort

### 🧠 Idea

Paas-paas ke elements compare karo. Agar order galat hai to swap.

Example:

```text
[5, 2, 8, 1]

5 > 2 → swap
[2, 5, 8, 1]

8 > 1 → swap
[2, 5, 1, 8]

Next round:
[2, 1, 5, 8]

Final:
[1, 2, 5, 8]
```

### 💼 Kis kaam aati hai?

Real projects mein generally **Bubble Sort use nahi karte**.

Mostly:

* Sorting ka basic concept samajhne ke liye
* Beginner/interview mein algorithm implementation poochne ke liye

### Complexity

```text
Best:  O(n)
Average: O(n²)
Worst: O(n²)
Space: O(1)
```

### 🎤 Interview Questions

**Q1. Bubble Sort ka main idea kya hai?**

👉 Adjacent elements compare karke wrong order hone par swap karna.

**Q2. Bubble Sort ko optimize kaise kar sakte hain?**

👉 `swapped` flag use karke. Agar kisi pass mein swap nahi hua, array already sorted hai.

---

# 2️⃣ Selection Sort

### 🧠 Idea

Har round mein **minimum element find karo** aur beginning mein rakh do.

Example:

```text
[5, 2, 8, 1, 3]
```

Minimum = `1`

```text
[1, 2, 8, 5, 3]
```

Ab remaining mein minimum = `2`

```text
[1, 2, 8, 5, 3]
```

Next minimum = `3`

```text
[1, 2, 3, 5, 8]
```

### 💼 Kis kaam aati hai?

* Basic sorting understanding
* Jab **swaps kam rakhne** ki need ho, selection sort useful concept hai
* Mostly educational/interview implementation

### Complexity

```text
Best = Average = Worst = O(n²)
Space = O(1)
```

### 🎤 Interview

**Q. Selection Sort aur Bubble Sort mein difference?**

👉 Bubble adjacent elements ko repeatedly swap karta hai, Selection minimum ko find karke correct position par swap karta hai.

---

# 3️⃣ Insertion Sort ⭐

Ye **important** hai.

### 🧠 Real-life example

Playing cards arrange karte waqt:

```text
5
```

Phir `2` mila:

```text
2 5
```

Phir `8`:

```text
2 5 8
```

Phir `1`:

```text
1 2 5 8
```

### 💼 Kis kaam mein?

**Nearly sorted data** ke liye bahut useful.

Example:

```text
[1, 2, 3, 5, 4, 6, 7]
```

Array almost sorted hai. Insertion Sort efficiently `4` ko correct position par le aa sakta hai.

### Complexity

```text
Best: O(n)
Average: O(n²)
Worst: O(n²)
Space: O(1)
```

### 🎤 Interview

**Q. Nearly sorted array ke liye kaunsi sorting choose karoge?**

👉 **Insertion Sort**

**Q. Insertion Sort ka best case O(n) kyun hai?**

👉 Jab array already sorted ho, har element ko bas ek comparison ke around process karna padta hai.

---

# 4️⃣ Merge Sort ⭐⭐⭐

Ye **placement/interview ke liye very important** hai.

### 🧠 Main concept

**Divide and Conquer**

Example:

```text
[8, 3, 2, 9, 7, 1]
```

Divide:

```text
[8, 3, 2]    [9, 7, 1]
```

Again:

```text
[8] [3,2]    [9] [7,1]
```

Finally single elements:

```text
[8] [3] [2] [9] [7] [1]
```

Ab merge karte waqt sort:

```text
[3,8] [2,9] [1,7]
```

Then:

```text
[2,3,8] [1,7,9]
```

Finally:

```text
[1,2,3,7,8,9]
```

### 💼 Kis kaam mein?

Merge Sort useful hai jab:

* Guaranteed `O(n log n)` chahiye
* **Stable sorting** chahiye
* Linked List sorting
* External sorting / large data scenarios

### Complexity

```text
Best: O(n log n)
Average: O(n log n)
Worst: O(n log n)

Space: O(n)
```

### 🎤 Interview Questions

**Q. Merge Sort ka concept kya hai?**

👉 Divide array into halves, recursively sort them, then merge sorted halves.

**Q. Merge Sort ki time complexity hamesha O(n log n) kyun hoti hai?**

👉 Array repeatedly half hota hai → `log n` levels, aur har level par total `n` elements process hote hain.

So:

```text
n × log n = O(n log n)
```

**Q. Merge Sort ka disadvantage?**

👉 Extra `O(n)` space lagti hai.

---

# 5️⃣ Quick Sort ⭐⭐⭐

Ye bhi **bahut important interview sorting** hai.

### 🧠 Main concept

**Pivot + Partition**

Example:

```text
[5, 2, 8, 1, 3]
```

Pivot = `5`

5 se smaller:

```text
[2, 1, 3]
```

5 se greater:

```text
[8]
```

So:

```text
[2,1,3] | 5 | [8]
```

Ab left part ko sort:

```text
[1,2,3] | 5 | [8]
```

Final:

```text
[1,2,3,5,8]
```

### 💼 Kis kaam mein?

Quick Sort useful hai jab:

* Average-case fast sorting chahiye
* In-place sorting preferred ho
* Array data ho

### Complexity

```text
Best: O(n log n)
Average: O(n log n)
Worst: O(n²)
```

### 🎤 Interview Questions

**Q. Quick Sort mein pivot kya hota hai?**

👉 Wo element jiske around array ko partition kiya jata hai.

**Q. Quick Sort worst case kab hota hai?**

👉 Jab repeatedly poor pivot choose ho, jaise already sorted array par certain pivot choices.

**Q. Quick Sort aur Merge Sort mein difference?**

👉 Quick Sort generally in-place hota hai aur average mein fast hota hai, while Merge Sort guaranteed `O(n log n)` deta hai but extra space leta hai.

---

# 6️⃣ Heap Sort ⭐⭐

Heap Sort mein **Heap** data structure use hota hai.

Example:

```text
[5, 2, 8, 1, 3]
```

Max Heap banaya:

```text
        8
       / \
      3   5
     / \
    1   2
```

Largest element `8` ko end mein bhejte hain.

Repeat:

```text
[1,2,3,5,8]
```

### 💼 Kis kaam mein?

* Jab `O(n log n)` guaranteed chahiye
* Extra array space avoid karna ho
* Heap/Priority Queue based problems mein concept useful hai

### Complexity

```text
Best: O(n log n)
Average: O(n log n)
Worst: O(n log n)
Space: O(1)
```

### 🎤 Interview

**Q. Heap Sort ki biggest advantage?**

👉 Worst case bhi `O(n log n)` aur in-place sorting possible.

**Q. Heap Sort ka connection kis data structure se hai?**

👉 Binary Heap.

---

# 7️⃣ Counting Sort ⭐⭐

Ye thodi different hai.

Ye elements ko compare nahi karta, **frequency count** karta hai.

Example:

```text
[4, 2, 2, 3, 1, 4]
```

Count:

```text
1 → 1
2 → 2
3 → 1
4 → 2
```

Result:

```text
[1,2,2,3,4,4]
```

### 💼 Kis kaam mein?

Jab values ka **range chhota** ho.

Example:

```text
Student marks:
[10, 5, 7, 5, 10, 2]
```

Range 0–100 hai → Counting Sort useful ho sakta hai.

### Complexity

```text
O(n + k)
```

`k` = range of values.

### 🎤 Interview

**Q. Counting Sort kab use nahi karoge?**

👉 Jab values ka range bahut bada ho.

Example:

```text
[1, 999999999]
```

Is case mein huge counting array banana inefficient hoga.

---

# 8️⃣ C++ `sort()` ⭐⭐⭐⭐⭐

Practical coding interview mein ye **sabse important** hai.

```cpp
sort(arr.begin(), arr.end());
```

Example:

```cpp
vector<int> arr = {5, 2, 8, 1, 3};

sort(arr.begin(), arr.end());
```

Output:

```text
[1,2,3,5,8]
```

Descending:

```cpp
sort(arr.begin(), arr.end(), greater<int>());
```

### 💼 Kis kaam mein?

Normal coding problems mein jab interviewer algorithm **implement karne ko specifically nahi bol raha**.

---

# 🧠 Ab sabka comparison

| Sorting   | Main Idea               | Best Use                              |
| --------- | ----------------------- | ------------------------------------- |
| Bubble    | Adjacent swap           | Learning/basic interview              |
| Selection | Minimum select          | Basic implementation                  |
| Insertion | Correct position insert | Nearly sorted array                   |
| Merge     | Divide + Merge          | Guaranteed O(n log n), stable sorting |
| Quick     | Pivot + Partition       | Fast average-case array sorting       |
| Heap      | Heap                    | O(n log n), in-place                  |
| Counting  | Frequency               | Small integer range                   |
| `sort()`  | Library sorting         | Normal coding problems                |

---

# 🔥 Interview mein ye questions MUST karo

### Level 1

1. Implement Bubble Sort.
2. Implement Selection Sort.
3. Implement Insertion Sort.
4. Sort array in ascending/descending order.
5. Find largest and smallest after sorting.

### Level 2

6. Implement Merge Sort.
7. Implement Quick Sort.
8. Merge two sorted arrays.
9. Sort an array containing only `0, 1, 2`.
10. Find kth smallest/largest element.

### Level 3 🔥

11. Count inversions in an array.
12. Find minimum swaps required to sort an array.
13. Sort array according to frequency.
14. Merge overlapping intervals.
15. Sort characters according to frequency.

---

# ⭐ Sabse Important Trick

Interview mein question dekhkar **sorting ko blindly mat lagana**.

Example:

### Question:

> Array contains only `0, 1, 2`. Sort it.

Normal:

```text
sort()
```

kaam karega.

But interviewer pooch sakta hai:

> **"Can you do it in O(n)?"**

Tab tumhe **Dutch National Flag Algorithm** yaad aana chahiye.

```text
0 → left
1 → middle
2 → right
```

Ye **bahut important placement question** hai.

---

## 🎯 Tumhari Sorting Preparation ka order

Tum is order mein padho:

```text
Bubble
   ↓
Selection
   ↓
Insertion
   ↓
Merge ⭐
   ↓
Quick ⭐
   ↓
Heap
   ↓
Counting
   ↓
STL sort()
   ↓
Sorting Problems 🔥
```

**Sabse pehle Bubble Sort ko master karo.** Uske baad main tumhe **Bubble Sort ka C++ code line-by-line, dry run, time complexity, aur interview mein uske tricky questions** karwaunga.
