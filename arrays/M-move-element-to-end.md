## Move Element to End
- 题目：You're given an array of integers and an integer. Write a function that moves all intances of that integer in the array to the end of the array and returns the arrays.
- The function should **perform this in place**(i.e, it should mutate the input array) and doesn't need to maintain the order of the other integers.

- **Sample Input**
```python
array = [2, 1, 2, 2, 2, 3, 4, 2] 
toMove = 2
```
- **Sample Output**
```python
[1, 3, 4, 2, 2, 2, 2, 2] # the numbers 1, 3 and 4 could be ordered differently.
```

### Solutions
#### Solution 1, 首尾双指针，找到头部第一个是toMove和尾部第一个不是toMove，然后进行原地交换，如此重返，直到首尾指针相遇则结束。
- Time : O(n) | Space : O(1)
```python
def moveElementToEnd(array, toMove):
    # Write your code here.
    head, tail = 0, len(array) - 1
    while head < tail:
        while array[head] != toMove and head < tail:
            head += 1
        while array[tail] == toMove and head < tail:
            tail -= 1
        array[head], array[tail] = array[tail], array[head]
    return array
```
