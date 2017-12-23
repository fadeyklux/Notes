Numpy
=================
notes from [Scipy Lecture Notes](http//www.scipy-lectures.org/index.html)
**function list**
```python
np.array()
np.arange()
np.ones()
np.array_equal()
np.logical_or()
np.logical_and()
#math
np.sqrt()
np.sin()
np.log()
np.exp()
np.cusum()
np.sum()
np.triu()
np.tril()
np.allclose()
#random
np.random.rand()
np.random.randint()
np.all()
np.any()
np.median()
ndarray.T
#statistic
ndarray.sum()
ndarray.max()
ndarray.min()
ndarray.argmax()
ndarray.argmin()
ndarray.std()
ndarray.mean()

```
2.numerical operations on arrays
--------------------------------
--------------------------------
### 1.Elementwise operations
#### Basic operations
the operations are much faster than if you did them in pure python
```python
#with scalars:
a = np.array([1,2,3,4])
a + 1
2**a
#much fater than this
l = range(5)
[i+1 for i in l]
#all arithmetic operates elementwise
b = np.ones(4) + 1
a - b
#Array multiplication is not matrix multiplication
c = np.ones((3,3))
c * c #
c.dot(c)
```
#### Other operations
+ Comparisons:
    + elementwise comparisons
    ```python
    a = np.array([1, 2, 3, 4])
    b = np.array([4, 2, 2, 4])
    a == b
    a > b
    ```
    + array-wise comparisions
    ```python
    a = np.array([1, 2, 3, 4])
    b = np.array([4, 2, 2, 4])
    np.array_equal(a, b)
+ Logical operations:
    ```python
    a = np.array([1, 1, 0, 0], dtype=bool)
    b = np.array([1, 0, 1, 0], dtype=bool;)
    np.logical_or(a, b)
    np.logical_and(a, b)
    ```
+ Transcendental functions:
    ```python
    a = np.ararnge(5)
    np.sin(a)
    np.log(a)
    np.exp(a)
+ Transposition:
    **<font color=red>The transposition is a view**
    recommend use of *scipy.linalg* rather than *numpy.linalg*
    ```python
    a = np.triu(np.ones((3, 3)), 1)
    a.T
    #the following code is wrong and will not make a matrix symmetric
    a += a.T
### Basic reductions
#### Computing sums
```python
x = np.array([1, 2, 3, 4])
np.sum(x)
x.sum()
```
sum by rows and by columns：
```python
x = np.array([[1, 1], [2, 2]])
x.sum(axis=0) #columns
x[:, 0].sum()
x[:, 1].sum()
x.sum(axis=1) #rows
x[0, :].sum()
x[1, :].sum()
```
#### Other reductions
+ Extrema:
```python
x = n.array([1, 3, 2])
x.min()
x.max()
x.argmin()
x.argmax()
```
+ Logical operations:
```python
np.all([True, True, False])
np.any([True, True, False])
a = np.zeros((100, 100))
np.any(a != 0)
np.all(a == a)

a = np.array([1, 2, 3, 2])
b = np.array([2, 2, 3, 2])
c = np.array([6, 4, 4, 5])
((a <= b) & (b <= c)).al()
```
+ Statistics:
```python
x = np.array([1, 2, 3, 1])
y = np.array([[1, 2, 3], [5, 6, 1]])
x.mean()
np.median(x)
np.median(y, axis=-1) # last axis
x.std()          # full population standard dev.
0.82915619758884995