# 34. Finfd First and Last Position of Element in Sorted Array

**Date Solved:** 2025-01-07  
**Difficulty:** Medium  
**Category:** Binary Search  

---

## Problem Screenshot
![Problem Screenshot](../images/33_problem_2.png)

---

## Reflection

lower_bound 函数寻找有序数组里第一个大于等于 target 的下标  
二分范围 [0, n - 1]

设 nums 为递增数组，长度为 n  

- >= target 的第一个元素的下标：`lowerBound(nums, x)`
- > target 的第一个元素的下标：`lowerBound(nums, x + 1)`
- < target 的第一个元素的下标：`lowerBound(nums, x) - 1`
- <= target 的第一个元素的下标：`lowerBound(nums, x + 1) - 1`

- < target 的元素个数：`lowerBound(nums, x)`
- <= target 的元素个数：`lowerBound(nums, x + 1)`
- >= target 的元素个数：`n - lowerBound(nums, x)`
- > target 的元素个数：`n - lowerBound(nums, x + 1)`

在 search 函数内，要先判断 start 是否满足条件，
即二分的结果是否超出数组长度，或者不等于 target。

在同一个类里调用函数，前面要加 self。
