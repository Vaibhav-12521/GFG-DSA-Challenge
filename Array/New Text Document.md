Here is a complete and **well-structured `README.md`** file for the **"Second Largest Element in an Array"** problem in the GFG 160 Days DSA Challenge. You can directly copy-paste this into your GitHub repository.

---

````markdown
# 🥈 Second Largest Element in an Array

**Problem Statement:**  
Given an array of positive integers `arr[]`, return the **second largest distinct element** in the array.  
If the second largest element does not exist (i.e., all elements are the same), return `-1`.

---

## 🔍 Examples

```text
Input:  arr[] = [12, 35, 1, 10, 34, 1]
Output: 34

Input:  arr[] = [10, 5, 10]
Output: 5

Input:  arr[] = [10, 10, 10]
Output: -1
````

---

## 📚 Constraints

* 2 ≤ arr.length ≤ 10⁵
* 1 ≤ arr\[i] ≤ 10⁵

---

## 📑 Table of Contents

1. [Naive Approach - Sorting](#1-naive-approach---sorting)
2. [Better Approach - Two Pass Search](#2-better-approach---two-pass-search)
3. [Optimal Approach - One Pass Search](#3-optimal-approach---one-pass-search)

---

## ✅ 1. Naive Approach - Sorting

### 💡 Idea

Sort the array and then traverse it from the second last index to find the first element which is not equal to the largest one.

### 🧠 Code

```python
def getSecondLargest(arr):
    n = len(arr)
    arr.sort()
    for i in range(n - 2, -1, -1):
        if arr[i] != arr[n - 1]:
            return arr[i]
    return -1

# Example usage
arr = [12, 35, 1, 10, 34, 1]
print(getSecondLargest(arr))  # Output: 34
```

### ⏱ Time & Space Complexity

* Time: O(n \* log n)
* Space: O(1)

---

## ✅ 2. Better Approach - Two Pass Search

### 💡 Idea

Traverse the array twice:

1. First to find the largest element
2. Second to find the largest element smaller than the first

### 🧠 Code

```python
def getSecondLargest(arr):
    n = len(arr)
    largest = -1
    secondLargest = -1

    for i in range(n):
        if arr[i] > largest:
            largest = arr[i]

    for i in range(n):
        if arr[i] != largest and arr[i] > secondLargest:
            secondLargest = arr[i]

    return secondLargest

# Example usage
arr = [12, 35, 1, 10, 34, 1]
print(getSecondLargest(arr))  # Output: 34
```

### ⏱ Time & Space Complexity

* Time: O(n)
* Space: O(1)

---

## ✅ 3. Optimal Approach - One Pass Search

### 💡 Idea

Traverse the array once while keeping track of both the largest and second largest elements.

### 🧠 Code

```python
def getSecondLargest(arr):
    n = len(arr)
    largest = -1
    secondLargest = -1

    for i in range(n):
        if arr[i] > largest:
            secondLargest = largest
            largest = arr[i]
        elif arr[i] != largest and arr[i] > secondLargest:
            secondLargest = arr[i]

    return secondLargest

# Example usage
arr = [12, 35, 1, 10, 34, 1]
print(getSecondLargest(arr))  # Output: 34
```

### ⏱ Time & Space Complexity

* Time: O(n)
* Space: O(1)

---

## 🙌 Conclusion

* ✅ Sorting is simple but not optimal.
* ✅ Two-pass approach improves time but still iterates twice.
* ✅ One-pass is the most **efficient and optimal solution**.

---

## 📌 Author

Contributed by [Vaibhav Singh](https://github.com/Vaibhav-12521) as part of the [GFG 160 Days DSA Challenge](https://github.com/Vaibhav-12521/GFG-DSA-Challenge)

---

