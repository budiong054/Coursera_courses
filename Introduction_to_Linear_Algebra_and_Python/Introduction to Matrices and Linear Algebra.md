# Introduction to Matrices and Linear Algebra

## Using Numpy and Sympy to create Matrices


```python
import numpy as np
import sympy as sy
import random
```

## Create matrices manually 

- **Numpy**


```python
np.array([[1, 2],[4, 5]])
```




    array([[1, 2],
           [4, 5]])




```python
np.array([[1],[2],[3]])
```




    array([[1],
           [2],
           [3]])



- **Sympy**


```python
sy.Matrix([[1,2], [4,5]])
```




$\displaystyle \left[\begin{matrix}1 & 2\\4 & 5\end{matrix}\right]$




```python
sy.Matrix([[1],[2],[3]])
```




$\displaystyle \left[\begin{matrix}1\\2\\3\end{matrix}\right]$




```python
sy.Matrix([4,5,6])
```




$\displaystyle \left[\begin{matrix}4\\5\\6\end{matrix}\right]$




```python
sy.Matrix([[4,5,6]])
```




$\displaystyle \left[\begin{matrix}4 & 5 & 6\end{matrix}\right]$



## Generating matrices using the random library

- **Numpy**


```python
np.random.randint(2, 8, size=(2, 2))
```




    array([[2, 3],
           [5, 4]])




```python
np.random.randint(-2, 4, size=(1, 5))
```




    array([[ 1,  1, -1,  0,  2]])




```python
np.random.randint(-2, 4, size=(5, 1))
```




    array([[-1],
           [-2],
           [ 3],
           [ 1],
           [ 1]])



- **Sympy**


```python
sy.Matrix(np.random.randint(2, 8, size=(2, 2)))
```




$\displaystyle \left[\begin{matrix}6 & 7\\2 & 3\end{matrix}\right]$




```python
sy.Matrix(np.random.randint(-2, 4, size=(1, 5)))
```




$\displaystyle \left[\begin{matrix}1 & 1 & -2 & -2 & 2\end{matrix}\right]$




```python
sy.Matrix(np.random.randint(-2, 4, size=5))
```




$\displaystyle \left[\begin{matrix}0\\-2\\1\\0\\-1\end{matrix}\right]$



### Creating special matrices

 - **Identity matrix**

 - **Numpy**


```python
np.eye(2, dtype=int)
```




    array([[1, 0],
           [0, 1]])




```python
np.eye(3, 4, dtype=int)
```




    array([[1, 0, 0, 0],
           [0, 1, 0, 0],
           [0, 0, 1, 0]])




```python
np.eye(3, 4, dtype=int, k=1)
```




    array([[0, 1, 0, 0],
           [0, 0, 1, 0],
           [0, 0, 0, 1]])



- **Sympy**


```python
sy.eye(2)
```




$\displaystyle \left[\begin{matrix}1 & 0\\0 & 1\end{matrix}\right]$




```python
sy.eye(2, 3)
```




$\displaystyle \left[\begin{matrix}1 & 0 & 0\\0 & 1 & 0\end{matrix}\right]$




```python
sy.eye(4)
```




$\displaystyle \left[\begin{matrix}1 & 0 & 0 & 0\\0 & 1 & 0 & 0\\0 & 0 & 1 & 0\\0 & 0 & 0 & 1\end{matrix}\right]$




```python
sy.eye(3, 4)
```




$\displaystyle \left[\begin{matrix}1 & 0 & 0 & 0\\0 & 1 & 0 & 0\\0 & 0 & 1 & 0\end{matrix}\right]$



 - **Zeros Matrix**

- **Numpy**


```python
np.zeros((4, 4))
```




    array([[0., 0., 0., 0.],
           [0., 0., 0., 0.],
           [0., 0., 0., 0.],
           [0., 0., 0., 0.]])




```python
np.zeros((4, 4), dtype=int)
```




    array([[0, 0, 0, 0],
           [0, 0, 0, 0],
           [0, 0, 0, 0],
           [0, 0, 0, 0]])




```python
np.zeros((4, 5), dtype=int)
```




    array([[0, 0, 0, 0, 0],
           [0, 0, 0, 0, 0],
           [0, 0, 0, 0, 0],
           [0, 0, 0, 0, 0]])



- **Sympy**


```python
sy.zeros(2)
```




$\displaystyle \left[\begin{matrix}0 & 0\\0 & 0\end{matrix}\right]$




```python
sy.zeros(3,4)
```




$\displaystyle \left[\begin{matrix}0 & 0 & 0 & 0\\0 & 0 & 0 & 0\\0 & 0 & 0 & 0\end{matrix}\right]$



 - **Ones Matrix**

- **Numpy**


```python
np.ones(4, dtype=int)
```




    array([1, 1, 1, 1])




```python
np.ones((4,1), dtype=int)
```




    array([[1],
           [1],
           [1],
           [1]])




```python
np.ones((4, 4),dtype=int)
```




    array([[1, 1, 1, 1],
           [1, 1, 1, 1],
           [1, 1, 1, 1],
           [1, 1, 1, 1]])



- **Sympy**


```python
sy.ones(4)
```




$\displaystyle \left[\begin{matrix}1 & 1 & 1 & 1\\1 & 1 & 1 & 1\\1 & 1 & 1 & 1\\1 & 1 & 1 & 1\end{matrix}\right]$




```python
sy.ones(2, 3)
```




$\displaystyle \left[\begin{matrix}1 & 1 & 1\\1 & 1 & 1\end{matrix}\right]$



- **Diagonal Matrix**

- **Numpy**


```python
np.diag([1, 3, 6])
```




    array([[1, 0, 0],
           [0, 3, 0],
           [0, 0, 6]])




```python
x = np.arange(2, 10).reshape(2,4)
print(x)
np.diag(x)
```

    [[2 3 4 5]
     [6 7 8 9]]
    




    array([2, 7])



- **Sympy**


```python
sy.diag(1, 2, 3)
```




$\displaystyle \left[\begin{matrix}1 & 0 & 0\\0 & 2 & 0\\0 & 0 & 3\end{matrix}\right]$




```python
sy.diag([1, 2, 3])
```




$\displaystyle \left[\begin{matrix}1\\2\\3\end{matrix}\right]$




```python
sy.diag(*[1, 2, 3])
```




$\displaystyle \left[\begin{matrix}1 & 0 & 0\\0 & 2 & 0\\0 & 0 & 3\end{matrix}\right]$




```python
sy.diag([1, 2, 3], unpack=True)
```




$\displaystyle \left[\begin{matrix}1 & 0 & 0\\0 & 2 & 0\\0 & 0 & 3\end{matrix}\right]$


