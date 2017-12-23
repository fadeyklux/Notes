Tutorial
===============
## list

### 1. Method
+ list.**append**(_x_)
+ list.**extend**(_iterable_)
    ```python
    equivalent to a[len(a):] = iterable
    ```
+ list.**insert**(_i, x_)
    ```python
    a.insert(0, x) a.insert(len(a), xa.append(x)
    ```
+ list.**remove**(_x_)
+ list.**pop**(_[i]_)
+ list.**clear**()
    ```python
    equivalent to del a[:]
    ```
+ list.**index**(_x, [,start[, end]]_)
+ list.**cout**(_x_)
+ list.**sort**(_key = None, reverse=False_)
+ list.**reverse**()
+ list.**copy()**
+ shallow copy equivalent to 
    ```python
    a[:]
    ```
### 2. Using Lists as Stacks
```python
list.pop()
list.append()
```
### 3. Usiing Lists as Queue
While appends and pops from the end of list are fast,
**doing inserts or pops from the beginning of a list is slow** (because all of the other elements have to be shifted by one).
不要用list来实现队列，应该用deque
```python
from collections import deque
queue = deque([1,2,3])
queue.append()
queue.popleft()
```
### 4. List Comprehensions
```python
squares = []
for x in range(10):
    squares.append(x**2)
```
Note that this creates (or overwrites) a variable named x that **still exists** after the loop completes.
If the expression is a tuple (e.g. the (x, y) in the previous example), it must be parenthesized.
```python
list(map(lambda x: x**2, range(10)))

[x**2 for x in range(10)]

[(x,y) for x in [1,2,3] for y in [2,3,4] if x!=y]

[e.dosomething() for e in element]

[(x, x**2) for x in range(6)] #()need!! in x, x**2

# flatten a list using a listcomp with two 'for'
vec = [[1,2,3], [4,5,6], [7,8,9]]

[num for elem in vec for num in elem]

# List comprehensions can contain complex expressions and nested functions:
from math import pi
>>> [str(round(pi, i)) for i in range(1, 6)]
```
### 5. Nested List Comprehensions
```python
matrix = 
[[1, 2, 3, 4],
 [5, 6, 7, 8],
 [9, 10, 11, 12],]
#transpose
[[row[i] for row in matrix] for i in range(4)]
```
