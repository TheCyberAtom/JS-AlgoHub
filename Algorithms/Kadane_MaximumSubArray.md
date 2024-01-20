# Kadane Algorithm - Maximum Subarray

The Kadane's Algorithm is a widely used algorithm to find the maximum sum of a contiguous subarray within a one-dimensional array of numbers. The algorithm works by keeping track of the current subarray sum and updating it at each step. It efficiently handles both positive and negative numbers.

### Algorithm Explanation:

1. **Initialization:**

   - Initialize two variables: `maxEndingHere` and `maxSoFar` to track the maximum sum of the subarray ending at the current position and the overall maximum sum encountered so far.

2. **Iteration:**

   - Iterate through the array. At each step, update `maxEndingHere` to be the maximum of the current element or the sum of the current element and `maxEndingHere`.
   - Update `maxSoFar` to be the maximum of `maxSoFar` and `maxEndingHere`.

3. **Result:**
   - The final value of `maxSoFar` represents the maximum sum of a contiguous subarray in the given array.

#### Example :

JavaScript Example:

```javascript
function maxSubArray(nums) {
  let maxEndingHere = nums[0];
  let maxSoFar = nums[0];

  for (let i = 1; i < nums.length; i++) {
    maxEndingHere = Math.max(nums[i], maxEndingHere + nums[i]);
    maxSoFar = Math.max(maxSoFar, maxEndingHere);
  }

  return maxSoFar;
}

// Example usage:
const nums1 = [-2, 1, -3, 4, -1, 2, 1, -5, 4];
const maxSum1 = maxSubArray(nums1);
console.log(`Maximum sum of a contiguous subarray: ${maxSum1}`);
// Output: Maximum sum of a contiguous subarray: 6

const nums2 = [1, 2, -1, 3, -2, 4];
const maxSum2 = maxSubArray(nums2);
console.log(`Maximum sum of a contiguous subarray: ${maxSum2}`);
// Output: Maximum sum of a contiguous subarray: 7
```

> Leetcode Problem #53 : https://leetcode.com/problems/maximum-subarray/
