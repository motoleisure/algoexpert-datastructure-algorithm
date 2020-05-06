## Monotonic Array(单调数组)
- 题目：Write a function that takes in an array of integers and returns a boolean representing whether the array is monotonic.
- An array is said to be monotonic if its elements from left to right, are entirely non-increasing or entirely non-decreasing.

- **Sample Input**
```python
array = [-1, -5, -10, -1100, -1100, -1101, -1102, -9001]
```
- **Sample Output**
```python
true
```

### Solutions
#### Solution 1, 相邻两个元素相互比较，确定当前的数组是单调递增还是单调递减，如果中间有相反的例子，则返回false, 否则返回true.
- 需要注意的是如果相邻两个数字相同，则这样难以判定是递增还是递减。所以遇到这种情况，我们直接continue到下一步。
- Time : O(n) | Space : O(1)
```python
def isMonotonic(array):
    # Write your code here.
    ll = len(array)
    if ll < 3:
        return True
    trend = array[1] - array[0]

    for i in range(ll - 1):
        current = array[i]
        next_ele = array[i + 1]
        if trend == 0:
            trend = next_ele - current
            continue
        if breaktrend(trend, current, next_ele):
            return False
    return True

def breaktrend(trend, cur, nex):
    diff = nex - cur
    if trend > 0:
        return diff < 0
    return diff > 0
```

#### Solution 2, 这种做法有点取巧，定义两个表示递增和递减的变量，然后从头开始遍历数组，比较相邻两个元素，如果递增，则把递减变量赋予false，反之，把递增变量赋予false。最后饭后递增变量和递减变量的或结果。
- Time : O(n) | Space : O(1)
```python
def isMonotonic(array):
    # Write your code here.
    isNonDecreasing = True
    isNonIncreasing = True

    for i in range(1, len(array)):
        if array[i] < array[i - 1]:
            isNonDecreasing = False
        if array[i] > array[i - 1]:
            isNonIncreasing = False

    return isNonDecreasing or isNonIncreasing
```
