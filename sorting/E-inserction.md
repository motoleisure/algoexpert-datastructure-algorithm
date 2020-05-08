## Insertion Sort
- 题目：Write a function that takes in an array of integers and returns a sorted version of that array. Use the **Insertion Sort** algorithm to sort the array.
- If you are unfamiliar with insertion sort , I recommand you watching the visual gif algorithm of [Singapore National University](https://visualgo.net/zh/sorting)

- **Sample Input**
```python
array = [8, 5, 2, 9, 5, 6, 3]
```
- **Sample Output**
```python
[2, 3, 5, 5, 6, 8, 9]
```

### Solutions
#### Solution 1,
- Time : O(n^2) | Space : O(1)
```python
def insertionSort(array):
    # Write your code here.
    ll = len(array)
    for i in range(1, ll):
        j = i
        while j > 0 and array[j] < array[j - 1]:
            swap(array, j, j - 1)
            j -= 1
    return array

def swap(array, i, j):
    array[i], array[j] = array[j], array[i]
```

## 解题核心思想
### 把原数组分成2部分，第一部分是已排序的，第二部分是未排序的。然后取第二部分中的未排序的元素a和第一部分的元素由大到小逐个比较，如果a比当前比较的元素小，则交换位置，直到a比当前比较的元素大，这就是a在第一部分中的位置。如此重复，把所有未排序的元素全部变成已经排序的。
