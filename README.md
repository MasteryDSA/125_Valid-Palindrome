# 125. Valid Palindrome

## Problem

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters,
it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

### Example 1:

Input: s = "A man, a plan, a canal: Panama"

Output: true

Explanation: "amanaplanacanalpanama" is a palindrome.

### Example 2:

Input: s = "race a car"

Output: false

Explanation: "raceacar" is not a palindrome.

### Example 3:

Input: s = " "

Output: true

Explanation: s is an empty string "" after removing non-alphanumeric characters.

Since an empty string reads the same forward and backward, it is a palindrome.

---

## Approach: Two Pointers

Instead of creating a new cleaned string, I use two pointers:

* `left` starts at the beginning.
* `right` starts at the end.
* Skip any character that is **not** alphanumeric.
* Compare both characters in lowercase.
* If they differ, return `False`.
* Continue until the pointers meet.

### Algorithm

1. Initialize `left = 0` and `right = len(s) - 1`.
2. While `left < right`:

   * Move `left` forward until it points to an alphanumeric character.
   * Move `right` backward until it points to an alphanumeric character.
   * Compare `s[left].lower()` and `s[right].lower()`.
   * If they are different, return `False`.
   * Move both pointers inward.
3. Return `True` if all comparisons match.

---

## What I Learned

* The **two-pointer technique** efficiently compares characters from both ends.
* `isalnum()` helps ignore spaces and punctuation without manually checking ASCII values.
* This approach is optimal because it avoids creating an additional filtered string, achieving **O(1)** extra space.
