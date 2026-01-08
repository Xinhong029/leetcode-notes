# 33. Search in Rotated Sorted Array 
**Date Solved:** 2025-01-07  
**Difficulty:** Medium  
**Category:** Binary Search  
## Problem Screenshot
![Problem Screenshot](../images/33_problem_2.png)
## Reflection
旋转后的有序数组会被分成两段，第一段的所有元素均大于第二段的所有元素  
把 mid 与最后一个数比大小，可以寻找到最小值(leetcode 153)  
二分范围[0, n-1]: 因为不用访问mid+1的值，所以要把最后一个放在搜索范围  

分类讨论：  
如果 x 和 target 在不同的递增段：  
-如果 target 在第一段，x 在第二段，说明 target 在 x 的左边。target > nums[-1] >= x: right = mid - 1  
-如果 x 在第一段，target 在第二段，说明 target 在 x 的右边。x > nums[-1] >= target: left = mid + 1  
如果 x 和 target 在相同的递增段：  
-比较 x 和 target 的大小移动left, right
-直到找到答案，mid的值为target
否则返回-1
