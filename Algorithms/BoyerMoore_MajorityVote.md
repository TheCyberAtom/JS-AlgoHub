# Boyer–Moore Majority Vote Algorithm

The Boyer-Moore Majority Vote Algorithm is an efficient algorithm used to find the majority element in a sequence. The majority element is an element that appears more than n/2 times in an array of size n. The key feature of this algorithm is its ability to find the majority element in a single pass with O(1) space complexity.

### How it work :

The Boyer-Moore Majority Vote Algorithm is a space-efficient algorithm designed to identify the majority element in an array or sequence. By maintaining a candidate and a count, the algorithm iterates through the elements, updating the candidate when the count reaches zero. It guarantees the identification of the majority element, if it exists, in a single pass with O(1) space complexity. This makes it particularly suitable for large datasets where memory efficiency is crucial.

#### Psuedo Code

<ul>
    <li>Initialize an element m and a counter c with c = 0</li>
    <li>
    For each element x of the input sequence:
    <ul>
        <li>If c = 0, then assign m = x and c = 1</li>
        <li>else if m = x, then assign c = c + 1</li>
        <li>else assign c = c − 1</li>
    </ul>
    </li>
    <li>Return m</li>
</ul>

#### Example :

```javascript
function findMajorityElement(nums) {
  let candidate = null;
  let count = 0;

  // Step 1: Find a candidate
  for (let num of nums) {
    if (count === 0) {
      candidate = num;
      count = 1;
    } else if (num === candidate) {
      count++;
    } else {
      count--;
    }
  }
  // Step 2: Verify the candidate
  count = 0;
  for (let num of nums) {
    if (num === candidate) {
      count++;
    }
  }
  // Step 3: Check if the candidate is a majority element
  if (count > nums.length / 2) {
    return candidate;
  } else {
    return null; // No majority element
  }
}
// Example usage:
const nums = [2, 2, 1, 1, 1, 2, 2];
const majorityElement = findMajorityElement(nums);

if (majorityElement !== null) {
  console.log(`The majority element is: ${majorityElement}`);
} else {
  console.log("There is no majority element in the array.");
}
```

> Leetcode Problem #169 : https://leetcode.com/problems/majority-element/description/
