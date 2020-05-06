## Smallest Difference
- 题目：Write a function that takes in two non-empty arrays of integers, finds the **pair of numbers (one from each array) whose 
absolute difference is closest to zero**, and returns an array containing these two numbers, **with the number from the first array
in the first position**.

- **Sample Input**
```python
arrayOne = [-1, 5, 10, 20, 28, 3]
arrayTwo = [26, 134, 135, 15, 17]
```
- **Sample Output**
```python
[28, 26]
```

### Solutions
#### Solution 1, 先排序，然后用两个指针指向两个列表的最左边，然后计算两个数字的绝对值，如果等于0，那么这就是最理想的答案，如果不等于0，那么比较
两个数字大小，小的数字往下移动一位，直到某一个指针遍历完成位置。在过程中，我们另外要保存一个最小差（不等于0）的数值的两个数字，最后返回这个数字pairs。
- Time : O(n^2) | Space : O(1)

#### Solution 2,
- Time : O(nlog(n)) + O(mlog(m)) | Space : O(1)
```python
def smallestDifference(arrayOne, arrayTwo):
    # Write your code here.
    arrayOne.sort()
    arrayTwo.sort()
    smallest = float("inf")
    current = float("inf")
    smallestPair = []
    ll_one = len(arrayOne) - 1
    ll_two = len(arrayTwo) - 1
    i, j = 0, 0
    while i <= ll_one and j <= ll_two:
        current = abs(arrayOne[i] - arrayTwo[j])
        if smallest > current:
            smallest = current
            smallestPair = [arrayOne[i], arrayTwo[j]]
        if current == 0:
            return [arrayOne[i], arrayTwo[j]]
        elif current > 0:
            if arrayOne[i] > arrayTwo[j]:
                j += 1
            else:
                i += 1
    return smallestPair
```
