
# Deep L-layer neural network

<img src="http://media5.datahacker.rs/2018/09/imageedit_21_2055198684.jpg" width="600">

- L to denote the number of layers in a neural network
    - in this neural network `L=4`
- `n^[l]` to denote a number of layers in the lth layer
    - `n^[l]= 4`, there are four units in the first layer
    - `n^[2] = 4`, there are four units in the second layer
    - `n^[3] = 3`, there are three units in the thirs layer
    - `n^[4] = 1`, this neural network outputs a scalar value
    - `n^[l] = n^[x] = 3` because input vector, feature vector, has three features
- `a^[l]=g(z^[l])` to denote activation functions in the lth layer
    - `x=a[0]`
- `W^[l]` to denote weights for computing `z^[l]`
---

# Forward Propagation in a Deep Network


<img src="https://old.alexander-wong.com/img/deeplearning-ai/deep_neural_network_forward_propagation.png" width="600">

---
# Getting your matrix dimensions right
<img src="https://old.alexander-wong.com/img/deeplearning-ai/parameters_wl_and_bl.png" width="600">

<img src="https://old.alexander-wong.com/img/deeplearning-ai/vectorized_matrix_dimensions.png" width="600">

---
# Building blocks of deep neural networks

### **Forward** pass for layer ***l*** 

we get as we input activations from the previous layer and as the output we get activations of the current layer, layer ***l***.
<img src="http://media5.datahacker.rs/2018/09/Untitled-1.png">

***Equations for this calculation step are :***

         z[l]=W[l]a[l−1]+b[l]

         a[l]=g(z[l])


### **Backward** pass 

is done as we input **da[l]** and we get the output **da[l−1]**, as presented in the following graph. 

<img src="http://media5.datahacker.rs/2018/09/back_pass.png">

### In the following picture we can see a diagram of both a forward and a backward pass in the layer l.

<img src="http://media5.datahacker.rs/2018/09/forward_backward_pomereno.png">

> - to calulate values in the backward pass we need cached values.
> - Here we just draw z[l] as a cached value, but indeed we will need to cache also W[l] and b[l] as well as a[l−1].


### If we implement these two calculations as presented in a graph above, the computation for an L layer neural network will be as follows:

<img src="http://media5.datahacker.rs/2018/09/graphic_f_B.png" width="700">

### A 2-layer neural network is presented in the picture below:

<img src="http://media5.datahacker.rs/2018/09/graphic_f_B_three.png" width="700">

> with input feature vector  x=a[0]

---
# Forward and Backward propagation step equations

## 1) Forward propagation 
<img src="forward.png" width="600">


## 2) Backward propagation
<img src="backward.png" width="600">

---
# Parameters vs Hyperparameters

- The parameters of our model are **W[1]**,**b[1]**,**W[2]**,**b[2]**,…

```
Hyperparameters are the variables that determines the network structure and the variables which 
determine how the network will be trained and controls our parameters.
```

- The Hyperparameters of our model are:
    - learning rate **α**
    - number of iterations
    - number of hidden layers L
    - number of hidden units per layer
    - choice of activation function per layer


- Later hyperparameters
    - momentum
    - minibatch size
    - regularizations

### Applied deep learning is a very empirical process.

```
Idea -> Code -> Experiment
<- Repeat <
```

---

# Summary

<img src="https://zmlhywphftkhiczjuaamit.labs.coursera.org/files/Week%204/Building%20your%20Deep%20Neural%20Network%20-%20Step%20by%20Step/images/final%20outline.png" width="700">

---
3- Resources ? 
-
- [https://old.alexander-wong.com/post/neural-networks-and-deep-learning-week4/#forward-propagation-in-a-deep-network](https://old.alexander-wong.com/post/neural-networks-and-deep-learning-week4/#forward-propagation-in-a-deep-network)
- [http://datahacker.rs/deep-layer-neural-network/](http://datahacker.rs/deep-layer-neural-network/)
- [https://old.alexander-wong.com/post/neural-networks-and-deep-learning-week4/#forward-propagation-in-a-deep-network](https://old.alexander-wong.com/post/neural-networks-and-deep-learning-week4/#forward-propagation-in-a-deep-network)
