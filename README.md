# Contains Duplicate

## Problem
Given an integer array `nums`, return `true` if any value appears more than once. Return `false` if every element is distinct.

## Examples

**Example 1**
```text
Input: nums = [1, 2, 3, 3]
Output: true
```

**Example 2**
```text
Input: nums = [1, 2, 3, 4]
Output: false
```

## Approach 1: Brute Force

Compare each element with every element that comes after it. If two elements are equal, a duplicate exists.

- **Time Complexity:** O(n²)
- **Auxiliary Space Complexity:** O(1)

## Approach 2: Hash Set

Use a C++ `unordered_set` to store numbers already visited.

1. Create an empty hash set.
2. Traverse the array.
3. If the current number already exists in the set, return `true`.
4. Otherwise, insert the number into the set.
5. If the traversal finishes without finding a duplicate, return `false`.

### C++ Solution

```cpp
#include <vector>
#include <unordered_set>
using namespace std;

class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> seen;

        for (int num : nums) {
            if (seen.count(num)) {
                return true;
            }

            seen.insert(num);
        }

        return false;
    }
};
```

### Complexity Analysis

- **Time Complexity:** O(n) expected
- **Auxiliary Space Complexity:** O(n) worst case

Here, `n` represents the number of elements in the array.

## Key Learnings

- Nested loops can lead to O(n²) time complexity.
- A hash set stores unique values.
- `unordered_set::count()` checks whether a value exists.
- `unordered_set::insert()` adds a value to the set.
- Hash sets can improve expected lookup time to O(1).

## Topics

- Arrays
- Hashing
- `unordered_set`
- Time and Space Complexity

## Language

C++
