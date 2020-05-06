## Three Numbers Sum
- 题目：Write a function that takes in a non-empty array of distinct integers and an integer representing a target sum. The function should **find all triplets in the array** that sum up to the target sum and **return a two-dimensional array of all these triplets**. The numbers in **each triplet should be ordered in ascending order**, and the **triplets themselves should be ordered in ascending order** with respect to the numbers they hold.
- If no three numbers sum up to the target sum, the function should return a empty array.

- **Sample Input**
```python
array = [12, 3, 1, 2, -6, 5, -8, 6]
targetSum = 0
```
- **Sample Output**
```python
[[-8, 2, 6], [-8, 3, 5], [-6, 1, 5]]
```

### Solutions
#### Solution 1, 先对列表排序，然后暴力破解
- Time : O(n^3) | Space : O(n)
```python
def threeNumberSum(array, targetSum):
    # Write your code here.
    array.sort()
    ans = []
    ll = len(array)
    for i in range(ll-2):
		  firstNum = array[i]
		  for j in range(i+1, ll-1):
			  secondNum = array[j]
			  for k in range(j+1, ll):
				  thirdNum = array[k]
				  if firstNum + secondNum + thirdNum == targetSum:
					  ans.append([firstNum, secondNum, thirdNum])
	return ans
```
#### Solution 2, 先对列表排序，然后选定第一个数字，后两个数字在后面排序列表中用二分法求解
- Time : O(n^2) | Space : O(n)
```python

```
