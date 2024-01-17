# Dutch National Flag Algorithm

### Algorithm Explanation:

1. **Initialization:**

   - Initialize three pointers: `low` for 0s, `high` for 2s, and `i` for traversal.

2. **One-Pass Iteration:**

   - Iterate through the array using the `i` pointer until it crosses the `high` pointer.
   - If `nums[i]` is 0, swap it with the element at the `low` pointer and move both `low` and `i` pointers to the right.
   - If `nums[i]` is 2, swap it with the element at the `high` pointer and move the `high` pointer to the left.
   - If `nums[i]` is 1, leave it in its place and move `i` to the next position.

3. **Result:**
   - After the iteration, the array will be sorted with 0s on the left, 1s in the middle, and 2s on the right.

### JavaScript Code:

```javascript
function sortColors(nums) {
  let low = 0; // pointer for 0
  let high = nums.length - 1; // pointer for 2
  let i = 0; // pointer for traversal

  while (i <= high) {
    if (nums[i] === 0) {
      // Swap with the element at the low pointer
      [nums[i], nums[low]] = [nums[low], nums[i]];
      low++;
      i++;
    } else if (nums[i] === 2) {
      // Swap with the element at the high pointer
      [nums[i], nums[high]] = [nums[high], nums[i]];
      high--;
    } else {
      // Element is already 1, move to the next
      i++;
    }
  }
}

// Example usage:
const nums = [2, 0, 2, 1, 1, 0];
sortColors(nums);
console.log(nums); // Output: [0, 0, 1, 1, 2, 2]
```

> Leetcode Problem #74 : https://leetcode.com/problems/sort-colors/description/
