# Majority Element

This is a solution for the "Majority Element" problem on LeetCode using Python.

## Problem Description

Given an array of integers, find the majority element, which appears more than `n // 2` times, where `n` is the length of the array. You may assume that the array is non-empty and the majority element always exists in the array.

## Approach

The provided Python code implements a well-known algorithm called Boyer-Moore Voting Algorithm. This algorithm efficiently finds the majority element in a given array in a single pass.

1. Initialize two variables `res` and `count` to keep track of the current candidate for the majority element and its count.

2. Iterate through the input array `nums`.

3. For each element `n` in the array:
   - If `count` is equal to 0, set `res` to the current element `n`. This essentially assumes the current element as the majority candidate.
   - Update `count` by incrementing it if the current element `n` is equal to the current candidate `res`, or decrement it otherwise.

4. After the loop, the `res` variable will contain the majority element.

5. Return `res` as the majority element.

## Python Code

```python
from typing import List

class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        res, count = 0, 0

        for n in nums:
            if count == 0:
                res = n
            count += (1 if n == res else -1) 
        return res
```

## Usage

You can use this `Solution` class to find the majority element in an array of integers by creating an instance of the class and calling the `majorityElement` method with your input list of numbers.

```python
# Example usage
solution = Solution()
nums = [2, 2, 1, 1, 1, 2, 2]
result = solution.majorityElement(nums)
print("Majority Element:", result)
```

This will print the majority element, which is the number that appears more than `n // 2` times in the given array.
