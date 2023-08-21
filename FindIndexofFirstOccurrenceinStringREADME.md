# leet-day38

# String Matching in Haystack (Implement strStr())

## Problem Description

You are given two strings, `haystack` and `needle`. You need to find the index of the first occurrence of the `needle` in the `haystack`. If the `needle` is not part of the `haystack`, return `-1`.

## Example

### Input

```
haystack = "sadbutsad"
needle = "sad"
```

### Output

```
0
```

Explanation: "sad" occurs at index 0 and 6 in `haystack`. The first occurrence is at index 0, so we return 0.

## Approach

We can solve this problem using a brute force approach. We iterate through the `haystack` string using two nested loops. The outer loop runs from 0 to `m - n`, where `m` is the length of `haystack` and `n` is the length of `needle`. This is because if the remaining length of `haystack` is less than `n`, we can't find a match.

In the inner loop, we compare characters of the `haystack` and `needle`. If a character mismatch is found, we break out of the inner loop and continue with the next iteration of the outer loop. If the inner loop completes without any mismatches, it means we have found a substring in `haystack` that matches `needle`, so the index of the starting position of this substring is returned.

If no such substring is found, the function returns `-1`.

## Complexity Analysis

The worst-case time complexity of this approach is O((m - n + 1) * n), where `m` is the length of `haystack` and `n` is the length of `needle`. In the worst case, we need to compare all possible substrings of length `n` in `haystack` with the `needle`.

The space complexity of this approach is O(1), as we are not using any additional data structures that grow with the input size.

## Usage

You can use this solution to implement the `strStr()` function and solve the given problem on platforms like LeetCode or in your own coding environment. Just copy the provided code and adapt it according to the requirements of the platform.
