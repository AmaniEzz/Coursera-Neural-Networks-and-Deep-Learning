# Neural Networks

<img src="https://www.researchgate.net/profile/Facundo_Bre/publication/321259051/figure/fig1/AS:614329250496529@1523478915726/Artificial-neural-network-architecture-ANN-i-h-1-h-2-h-n-o.png" width="500">

##  1) Logistic Regression

    In logistic regression, our output Y hat equals the sigmoid function applied to this (wTx+b) quantity.

    The function sigmoid of Z goes smoothly from zero up to one it crosses the vertical axis as 0.5 (S shaped)

<img src="https://miro.medium.com/max/570/1*50TdLe6f_AW8wnBBkyLYgw.png" width="500">

> logistic regression job is to try to learn parameters `W` and `B` so that `Y hat` becomes a good estimate of the chance of `Y = 1`.


## 3) Logistic Regression cost function

- **loss function:**
    - is a function you'll need to define to measure how good our output y-hat is when the true label is y.
    - It measures how well you're doing on a single training example.


- **Cost function:**
    -  the average with one over the m of the sum of the loss function applied to each of the training examples and turn.
    - Measures how well you're doing an entire training set

<img src="https://miro.medium.com/max/1352/1*HKC6eKQgfgAJRu_rmF5TRQ.png" width="550">

> our goal is to minimzie this the overall cost function

---

## 4) Gradient Descent

     gradient descent will make the algorithm slowly decrease the parameter (W and B) if started with this large value of w and b.
     to find w and b that make the cost function J(w, b) as small as possible, bcz cost function J is a convex function.


## Logistic Regression Gradient Descent

<img src="https://i.stack.imgur.com/zgdnk.png" width="600">

-  `alpha: `
    - is the learning rate, and controls how big a step we take on each iteration or gradient descent.

- `cost function's derivative term:`
    - This is basically the update or the change you want to make to the parameters `w`.

---
                                                                                                                                                                                                        
## 5) Computation graph 

    The computation graph comes in handy when there is some special output variable that you want to optimize.
    (i.e. the derivative of our output with respect to one of our inputs).

    To create a computational graph, we make each operation, along with the input variables, into nodes.
    When one node’s value is the input to another node, an arrow goes from one to another.


#### Computations of a neural network are organized in terms of: 

- **forward pass or a forward propagation step:** 
    - in which we compute the output of the neural network, 

- **backward pass or back propagation step:**
    - which we use to compute gradients or compute derivatives.

---

## 6) Derivatives on Computational Graphs

#### What if we want to understand how nodes that aren’t directly connected affect each other?
- The general rule is to sum over all possible paths from one node to the other, multiplying the derivatives on each edge of the path together.

#### How e is affected by a?
<img src="https://colah.github.io/posts/2015-08-Backprop/img/tree-eval-derivs.png" width="500">

> If we change `a` at a speed of `1`, `c` also changes at a speed of `1`.
>  In turn, `c` changing at a speed of `1` causes `e` to change at a speed of `2`. 
>  So `e` changes at a rate of `1∗2` with respect to a.


### Logistic Regression Backpropagation (for a single training example)

<img src="https://gogul.dev/images/software/logistic-regression/computation-graph-1.jpg" width="600">

---


## 7) Vectorization

```
     Foor loops are very slow in deep learning era, so we need other faster solution. 
     Instead, we will use vectorization offered by numpy to speed up the computations.
```
```
     Vectorization is the process of converting an algorithm from operating on a single value at a time
     to operating on a set of values at one time. 

     Modern CPUs provide direct support for vector operations where a single instruction is applied to multiple data (SIMD).
```
```
     the dot product is done by taking the transpose of first matrix and then mathematical matrix multiplication 
     of a’(transpose of a) and b is followed as shown in the figure below.
```

<img src="https://gogul.dev/images/software/logistic-regression/dimensions.jpg" width="500">


- **Other standard function:**
    - `outer(a, b)`: Compute the outer product of two vectors.
    - `multiply(a, b)`: Matrix product of two arrays.
    - `zeros((n, m))`: Return a matrix of given shape and type, filled with zeros.
    - `process_time()`: Return the value (in fractional seconds) of the sum of the
    - `np.maximum(v , 0)`: take the max of every element of v with 0.
    - `np.log(v)`: element-wise log of vector v
    - `np.abs(v)`: element-wise absolute value of vector v
    -


### Take aways:
- Don't use rank 1 arrays. 
- Always use either n by one matrices, basically column vectors, or one by n matrices, or basically row vectors.
- Always use numpy functions.


2- What’s new for you ?
-


3- Resources ? 
-
- [logistic_regression_derivative](http://ronny.rest/blog/post_2017_08_12_logistic_regression_derivative/)
- [Backprop](https://colah.github.io/posts/2015-08-Backprop/)
- [https://gogul.dev/software/neural-nets-logistic-regression](https://gogul.dev/software/neural-nets-logistic-regression)
- [Derivation of DL/dz](https://www.coursera.org/learn/neural-networks-deep-learning/discussions/weeks/2/threads/ysF-gYfISSGBfoGHyLkhYg)
- [Vectorization in Python](https://www.geeksforgeeks.org/vectorization-in-python/)
- [Vectorization](https://www.quantifisolutions.com/vectorization-part-2-why-and-what)