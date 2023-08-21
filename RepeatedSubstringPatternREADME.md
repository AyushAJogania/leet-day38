# leet-day38

## Problem Description

Given a string `s`, the task is to check if it can be constructed by taking a substring of it and appending multiple copies of the substring together.

## Examples

### Example 1

Input:
```
s = "abab"
```
Output:
```
true
```
Explanation:
The string "abab" can be formed by repeating the substring "ab" twice.

### Example 2

Input:
```
s = "aba"
```
Output:
```
false
```
Explanation:
The string "aba" cannot be formed by repeating any substring.

### Example 3

Input:
```
s = "abcabcabcabc"
```
Output:
```
true
```
Explanation:
The string "abcabcabcabc" can be formed by repeating the substring "abc" four times or the substring "abcabc" twice.

## Approach

The optimized approach to solving this problem is by using the Knuth-Morris-Pratt (KMP) pattern matching algorithm. The KMP algorithm helps us find the longest proper prefix of the string that is also a suffix of the string. If such a substring exists and the remaining length is a multiple of the length of the original string, then the original string can be constructed by repeating this substring.

1. Initialize an array `lps` (Longest Proper Prefix which is also a Suffix) of length `n` (length of string `s`).
2. Iterate through the string using the KMP algorithm to populate the `lps` array.
3. The value at `lps[n - 1]` represents the length of the longest proper prefix that is also a suffix.
4. Calculate the length of the repeated substring using `repeatedLen = n - lps[n - 1]`.
5. If the longest proper prefix's length is greater than 0 and `n` is divisible by `repeatedLen`, then return `true`.

## Complexity Analysis

- Time Complexity: O(n), where `n` is the length of the input string `s`.
- Space Complexity: O(n), where `n` is the length of the input string `s` due to the `lps` array used for the KMP algorithm.

## How to Use

1. The code is written in C++.
2. Replace the input string `s` with the desired string to check if it can be formed by repeating a substring.
3. Compile and run the code.
4. The program will output `true` if the string can be formed by repeating a substring, and `false` otherwise.
