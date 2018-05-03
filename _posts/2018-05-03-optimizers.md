---
layout: post 
title: Optimizers
categories: keras
---

<h2>Introduction</h2>
As a refreasher, optimizers are used to minimize an error function (also commonly known as objective function). This process is used in the learning phase of the neural network which is known as backpropagation. Let's learn more of some aspects with optimization. 

<b>Momentum</b>
<p>
First, let's discuss momentum. In physics, it is the quantity of motion of a moving body, measured as a product of its mass and velocity. How does this definition relate to minimizing an error function?Think of an error function as a geometric plane (Side note: Error functions are not necessarily two dimensional, and so we would instead minimize the hyper-plane). 
</p>
<p>
Let a ball roll down the plane to the lowest point following the steepest path (imitating the back propagation technique). Physics guarentees the ball will pass the lowest point (either the local or global minima) and continue to find another steep path to go down. We might be lucky and the shape of the plane declares that the ball will converge onto the global minima. More likely that would happen is that the minima is completely passed and will converge much later or not at the global minima. 
</p>
<p>
This problem is why a researcher, Yurii Nesterov sought to remedy the problem. The method is essentially calculating the gradient (curve) with respect to an approximate position the parameters would have taken the ball. 
</p>

<b>Learning Rate</b>
<p>
In the error function, there are costs which we must minimize. To illustrate the cost, let's use the previous example from the momentum section. If the geometric plane is the error function, the cost is the value of the coefficients of the function at a specific point of the plane. So if the point is at the highest point of the plane, the set of coefficients would be the least optimimal. Therefore, the point at the lowest point of the plane is the set of coefficients that is the most optimal   
</p>

<h3>Stochastic Gradient-Descent</h3>
<p>
This is a mouthful to say isn't it? Instead let's deconstruct it. First, let's tackle gradient descent. It is a process where in the backpropagation phase of neural networks, the cost of the error function is changed based on the error of the prediction of the output given an input. 
</p>
<p>
Within gradient descent, there is a method called batch gradient descent. It is gradient descent, but with the caveat that an update to the model occurs only at the end of an epoch. The cost is still calculated for every input and output. However, it is all combined and used to change the error function at the end of an epoch. This method is used for small datasets or large datasets with low amounts of redundancy.
</p>
<p>
Now for the final piece of the puzzle. Stochastic in this context just means we are updating the costs after every pass(one iteration of one data) of the neural network. However, this makes high variance since the loss function will always be changing based on a single input.  
</p>
<p>
As an important aside, there is another version of gradient descent called mini-batch descent which takes the positives of stochastic and batch gradient descent. This is used for big datasets.
</p>

<h3>RMSprop</h3>
<p>
As per Keras' website, it is recommended to leave the parameters at the default value except for learning rate. It is also a good choice for recurrent neural networks.

Conceptually, RMSprop is mini-batch gradient descent that updates parameter based on if a parameter has a big effect on getting to the minima. If a parameter has a big influence on the discovery of the minima, the update has a big effect. Conversely, if a parameter has a low influence, the update will have a small effect and essentially dampening the update. The math and further explanation can be found from Geoffrey Hinton's lecture notes on the topic for the University of Toronto's CSC 321.

Learning rate can be bigger since updates to unimportant parameters will be dampened and therefore can converge faster. 
</p>

<h3>Adagrad</h3>
<p>
It is recommended to leave the parameters at their default values.

AdaGrad (<b>Ada</b>ptive <b>Grad</b>ient) is used on datasets with features that are rare, but impactful or features that are irrelevant. It is adaptive because the learning rate is based on accumulating all past squared gradients. 
</p>

<h3>Adadelta</h3>
<p>
It is recommended to leave the parameters at their default values.

Adadelta is AdaGrad, but allows past gradients within a certain window size. A key feature with this optimizer is the absence of a learning rate because it is not used in the update rule.
</p>

<h3>Adam</h3>
<p>
Adam (<b>Ada</b>ptive <b>m</b>oment estimation) is basically RMSprop with momentum applied to it. It is also like AdaGrad, but doesn't factor in past gradients.
</p>

<h3>Adamax</h3>
<p>
It is a variant of Adam based on the infinity norm. So instead of L1 or L2, we can have L3, L4, ... Lp where p is infinity. Mathematically, Beta_2 is close to 1 coming from 0 in factor of infinity (eg. 0.9999999). This is important because if bias-correction isn't done, then the bias and parameter updates will be infinitely large. 
</p>

<h3>Nadam</h3>
<p>
Put simply, Nadam is just Adam with Nesterov momentum applied to it.
</p>

<h3>TFOptimizer</h3>
<p>
Listed on Keras' website, it is a wrapper class for native TensorFlow Optimizers. Therefore, I will not be using this optimizer since I mainly want to simplify my process of mastering machine learning to native Keras features. 
</p>

<h2>Conclusion</h2>
<p>
Obviously, we can create our own optimizers instead of using Keras' built-in optimizers. For my journey, I will use Keras' because it is meant to be the general solution to most machine learning problems and I will most likely not be tackling problems that require niche knowledge of optimizers. 
</p>
<p>
A struggle I had with this section of machine learning is that most of these optimizers are available as academic papers with little to no material to explain the concept in simplier terms. It should also be noted that some of these optimizers were recently published ranging from a couple of years to one year ago. 
</p>
<p>
Apart from Andrew Ng going over Adam and RMSprop optimizer, I had to read papers written for graduate students, professors and researchers. With that, I will not say I completely understood what was written (especially since there is heavy usage of mathematical notations). Instead, I understand the motivation for each optimizer and why it was created.
</p>
