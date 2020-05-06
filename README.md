# algoexpert course 1 datastructure and algorithm
- use language : **Python**
- [python基本数据类型的时间复杂度](https://www.jianshu.com/p/a8fa3d31aa40)

- **Python List**

|Operation|	Average Case|	Amortized Worst Case|
|--|--|--|
Copy|	O(n)|	O(n)|
Append[1]|	O(1)|	O(1)|
Insert|	O(n)|	O(n)|
Get Item|	O(1)|	O(1)|
Set Item|	O(1)|	O(1)|
Delete Item|	O(n)|	O(n)|
Iteration|	O(n)|	O(n)|
Get Slice|	O(k)|	O(k)|
Del Slice|	O(n)|	O(n)|
Set Slice|	O(k+n)|	O(k+n)|
Extend[1]|	O(k)|	O(k)|
Sort|	O(n log n)|	O(n log n)|
Multiply|	O(nk)|	O(nk)|
x in s|	O(n)	|
min(s), max(s)|	O(n)|	
Get Length|	O(1)|	O(1)|


- **Python Dictory**

Operation|	Average Case|	Amortized Worst Case|
|--|--|--|
Copy[2]|	O(n)|	O(n)|
Get Item|	O(1)|	O(n)|
Set Item[1]|	O(1)|	O(n)|
Delete Item|	O(1)|	O(n)|
x in s|	O(1)|	O(n)|
Iteration[2]|	O(n)|	O(n)|

- **Python Set**

Operation|	Average case|	Worst Case|
|--|--|--|
x in s|	O(1)|	O(n)|
Union s\|t|	O(len(s)+len(t))	|
Intersection s\&t|	O(min(len(s), len(t))|	O(len(s) * len(t))|
Multiple intersection s1&s2&..&sn	| |	(n-1)*O(l) where l is max(len(s1),..,len(sn))|
Difference s-t|	O(len(s))	|
s.difference_update(t)|	O(len(t))	|
Symmetric Difference s^t|	O(len(s))	|O(len(s) * len(t))|
s.symmetric_difference_update(t)|	O(len(t))|	O(len(t) * len(s))

