

# Second Largest Element in an Array

## 🧩 Problem Statement

Given an array of positive integers `arr[]`, return the **second largest** element from the array.  
If the second largest element doesn't exist (i.e., all elements are equal), return `-1`.

> **Note:** The second largest element must be **different** from the largest.

---

## ✅ Examples

### Example 1
**Input:**  
`arr = [12, 35, 1, 10, 34, 1]`  
**Output:**  
`34`  
**Explanation:**  
- Largest element: `35`  
- Second largest: `34`

---

### Example 2
**Input:**  
`arr = [10, 5, 10]`  
**Output:**  
`5`  
**Explanation:**  
- Largest element: `10`  
- Second largest: `5`

---

### Example 3
**Input:**  
`arr = [10, 10, 10]`  
**Output:**  
`-1`  
**Explanation:**  
- All elements are the same, so no second largest exists.

---

## 🧾 Constraints

- `2 ≤ arr.length ≤ 10⁵`
- `1 ≤ arr[i] ≤ 10⁵`

---

## 💡 Approach

1. Traverse the array once to find the **largest** and **second largest** distinct elements.
2. Use two variables:
   - `first` for the largest
   - `second` for the second largest
3. If no valid second largest is found, return `-1`.

---

## 🐍 Python Solution

```python
class Solution:
    def getSecondLargest(self, arr):
        first = float('-inf')
        second = float('-inf')

        for num in arr:
            if num > first:
                second = first
                first = num
            elif num > second and num < first:
                second = num

        return -1 if second == float('-inf') else second
```
<p align="center">
  <img src="https://profile-counter.glitch.me/Hunterdii/count.svg" />
</p>

