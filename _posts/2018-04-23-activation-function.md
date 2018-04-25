---
layout: post
title: Activation Functions
categories: keras 
---

<h2>Activation Functions</h2>

<p>
Let me preface this by stating that the information is 100% correct. 
All of the information I post from here on out are gathered from various sources online by a simple Google search. As such, I cannot guarantee that the information has been flushed out. This is a complex topic and I am not a prodigy that can pick up concepts the first time around. Having taken one class on machine learning does make it easier. However, it was only the basics of each concept. Let me remind you that much of the information is something extremely smart people have worked out for years. 
My process of picking up machine learning is to learn each aspect of neural networks one at a time. With that in mind, let's start with activation functions. Since this blog is not to be meant to teach, I will not be explaining concepts in such a way a beginner would understand. This blog is meant to be my journal of my journey to mastering (a man can dream) machine learning.
</p>

<h3>Why activation?</h3>
<p>
As we can guess from the word, we need to activate something. That something is the result from combining the input nodes with the weights and bias'. We activate it so that each output of the network is altered in a standardized way to determine the strength of the node. An important trait is that there is a set range for the strength so one node might not overpower all other nodes or vice versa. Each activation function has its pros and cons like everything in machine learning.  
</p>

<h3>Types of Keras Activation functions</h3>
<p>
The following activation functions are available for use by referencing the name as a parameter. 
</p>

<b>Softmax</b>
<p>
It is used for classification problems with multiple values. It will conform the input values to the range of 0 to 1 with the sum of the input values of 1.  
</p>

<b>Elu (Exponential Linear Unit)</b>
<p>
Exponential linear unit maintains a direct relation between the inputs and outputs if the input is greater than or equal to 0. If the input is x, the output will be x. However, if the input is less than 0, then the output bounded to a fixed value. 
</p>

<b>Selu (Scaled Exponential Linear Unit)</b>
<p>
This activation function is by far the most interesting, but also difficult to understand. The reason is that this was recently discovered in June 2017 by Klambauer, Unterthiner, Mayr and Hochreiter (Keras cites 'Klambauer et al., 2017) in their thesis "Self-Normalizing Neural Networks." This is my first time reading a paper written for academic purposes. By the time of writing this, the latest version was updated on September 2017. Another reason for the difficulty is that the paper is over 100 pages long with >50% of it dedicated to maths including various proofs. I will explore the concept in a later post as the paper is a substantial read. 
</p>

<b>Softplus</b>
<p>
Mathematically, the function is [ f(x) = ln(1 + e^x) ]. The bounds of the function is 0 to infinity. Ironically, the derivative (which we use in backpropagation) of the function is the sigmoid function. 
</p>

<b>Softsign</b>
<p>
The function is [ f(x) = x/(1 + |x| ]. It is bounded by -1 and 1, following a S-shaped curve. Softsign and tangent are similar, but the latter converges faster than the former. 
</p>

<b>ReLU</b>
<p>
Rectified linear units is simple [ f(x) = max(x, 0) ]. The output is 0 if the input is less than 0. Otherwise, the output is equal to the input. It is popular with deep learning in the hidden layers because of how fast it is and there is less errors on backpropagation since the derivative of a positive number is 1. However, the downside is that neurons may not activate at all (output is 0) and could affect further neurons, resulting in a percentage of dead neurons.
</p>

<b>Tanh</b>
<p>
The tangent activation function that shares close relationship with sigmoid. It maintains the S-shaped curve like the sigmoid, but instead maps the output values to the range of -1 to 1. That way, large positive numbers will be closer to 1 and large negative numbers are close to -1.
</p>

<b>Sigmoid</b>
<p>
This is the activation function I learned about in my class at UCR and with good reason. Mathematically, it is [ f(x) = 1 / (1 + e^(-x)) ] with x being the output of the network. Sigmoid is good for binary classification because the output will be in the range of 0 to 1. Two different output for classification of two items. A word of caution: it may get stuck in the training phase if a large negative input is used, the output will be close to 0, and the next layers will be impacted.  
</p>

<b>Hard Sigmoid</b>
<p>
For the activation function hard_sigmoid, it is implemented differently on the backend whether you are using Theano or Tensorflow. The reason why it is used is because it is faster since it is time costly to compute exp(). Hard sigmoid is not smooth like the sigmoid function (when looking at the graph), but still closely has comparable values to sigmoid. It is useful for "ballpark" estimation and should be done for classification problems. 
</p>

<b>Linear</b>
<p>
Linear regression, this activation is conceptually easy since it is a concept first learned when in algebra. Whether it is one or many inputs, linear regression will try to find a linear relationship with the inputs. In the case of multiple inputs, techniques such as least ordinary squares can be used. 
</p>

<h3>Conclusion</h3>
<p>
Learning of the different activation functions was an exciting process. I plan to put the knowledge I gained from what I researched into practice. Even though reading of the differences of each activation is helpful, it is hard to know the affects it can have on real life problems.   
</p>
