## Two Number Sum
- 题目：Write a function that takes in a non-empty array of distinct integers and an integer representing a target sum. If any 
two numbers in the input array sum up to the target sum, the function should return them in an array, in any order. If no two
numbers sum up to the target sum, the function should return an empty array.

- Node that the target sum has to be obtained by summing two different integers in the array, you can't add a single integer to 
itself in order to obtain the target sum.
- You can assume that there will be at most one pair of numbers summing up to the target sum.

- **Sample Input**
```python
array = [3, 5, -4, 8, 11, -1, 6]
targetSum = 10
```
- **Sample Output**
```python
[-1, 11] # the numbers could be in reverse order
```

### Solutions
#### Solution 1, 暴力破解法，利用2个for循环遍历列表，查看所有2个数字的组合是否满足targetSum的条件。
- Time : O(n^2) | Space : O(1)
```python
def twoNumberSum(array, targetSum):
    # Write your code here.
	# time : O(n^2), space : O(1)
	ll = len(array)
	for i in range(ll):
		diff = targetSum - array[i]
		for j in range(i+1, ll):
			if diff == array[j]:
				return [array[i], array[j]]
	return []
```

#### Solution 2，遍历一遍列表，利用字典的key值存储还没paired的数字，当前的diff = targetSum - num, 然后去查找diff是否在字典的keys中，如果在，那么就找到了一对。
- Time : O(n) | Space : O(n)
```python
def twoNumberSum(array, targetSum):
    # Write your code here.
	# time : O(n), space : O(n)
    nums = {}
	for num in array:
		potentialMatch = targetSum - num
		if potentialMatch in nums:
			return [potentialMatch, num]
		else:
			nums[num] = True
	return []
````

#### Solution 3，先对列表排序，然后用二分法求解。
- Time : O(nlog(n)) | Space : O(1)
```python
def twoNumberSum(array, targetSum):
    # Write your code here.
    array.sort()
	left, right = 0, len(array) - 1
	while left < right:
		currentSum = array[left] + array[right]
		if currentSum == targetSum:
			return [array[left], array[right]]
		elif currentSum < targetSum:
			left += 1
		else:
			right -= 1
	return []
````
