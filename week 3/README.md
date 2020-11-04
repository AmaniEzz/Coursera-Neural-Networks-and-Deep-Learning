#  Neural Networks Representation

<img src="https://old.alexander-wong.com/img/deeplearning-ai/two_layer_neural_network_diagram.png" width="650">

>For a neural network, each layer is broken out into its respective nodes.

---
# Computing a Neural Network’s Output

<img src="https://old.alexander-wong.com/img/deeplearning-ai/logistic_regression_node.png">

> this last upper unit is a lot like logistic regression, except that instead of writing the parameters as w and b, we're writing them as w_[2] and b_[2], with dimensions one by four and one by one.

---
# Vectorizing single example

<img src="https://old.alexander-wong.com/img/deeplearning-ai/neural_network_calculation.png" width="650">

<img src="https://old.alexander-wong.com/img/deeplearning-ai/neural_network_calculation_2.png" width="650">

---

# Vectorizing across multiple examples

    Our training examples stacked up horizontally in the matrix x, so the matrices A,Z,W and X 
    goes horizontally over different training examples, and vertically over different hidden units.


<img src="https://old.alexander-wong.com/img/deeplearning-ai/recap_of_vectorized_approach.png" width="650">

---

# Activation functions

<img src="https://old.alexander-wong.com/img/deeplearning-ai/summary_activation_functions.png" width="650">

- The sigmoid function goes within zero and one.
- Tanh function goes between plus 1 and minus 1.


- Tanh (hyperbolic tangent) function almost always works better than the sigmoid function, except for the output layer.
- If y∈0,1 the sigmoid function might be better for the output layer. 

- one of the downsides of both the sigmoid function and the tanh function is that 
```
    If z is either very large or very small,then the gradient or the derivative 
    or the slope of this function becomes very small. And so this can slow down gradient descent.
```

- For all other units, ReLU (rectified linear unit) is best, tanh function is better, sigmoid is worst.

- Leaky ReLU might be better than ReLU for neural nets.
---

# Why do you need non-linear activation functions?

- If you do not use non-linear activation functions, you will end up with linear calculation of x→y^ . 

- Linear activation functions eliminate the benefit of hidden layers, 
  as the composite of two linear functions is a linear function.

- If you have a linear activation function followed by a sigmoid function,
  then this model is no more expressive than standard logistic regression without any hidden layer.
---

# Derivatives of activation functions

```
When we implement back propagation for our neural network, we need to either compute 
the slope or the derivative of the activation functions.

Derivatives of activation functions are used to calculate Gradient Descent for Neural Networks
```

---

# Random Initialization

```
If you initialize all your weights to zero, your neural network won’t work,s
because your hidden layer will effectively become a hidden node
```
```
If you initialize the weights to zero, then all of your hidden units are symmetric,
And no matter how long you're upgrading the center, all continue to compute exactly the same function.
```

<img src="https://old.alexander-wong.com/img/deeplearning-ai/reason_for_initialized_weights_to_zero.png" width="650">

`W_initial = np.random.randn((2, 2)) * 0.01`

`b_initial = np.zero((2, 1))`

<img src="https://old.alexander-wong.com/img/deeplearning-ai/reason_for_initialized_weights_to_rand.png" width="650">



---
#  Resources ? 
-
- [https://old.alexander-wong.com/post/neural-networks-and-deep-learning-week3/#neural-network-representation](https://old.alexander-wong.com/post/neural-networks-and-deep-learning-week3/#neural-network-representation)

