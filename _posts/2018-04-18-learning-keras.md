---
layout: post
title: Learning Keras
categories: keras 
---

<h2>Learning Keras with ancient memory</h2>
<p>
I am interested in aritificial intelligence and have tried to get into learning Google's Tensorflow with zero progress. The furthest I have gone was the installation of the GPU version of Tensorflow, which is a task in itself. This requires you to set-up the environment to utilize the GPU which is a multi-step process. It was only recently that I was told of Keras, an easier entry to machine learning. So setting an afternoon aside, I went in to reading the documentation on Keras' <a href="https://keras.io/">website</a>. This blog is mainly so I can organize how I am going to study the Keras library.
</p>

<b>Creating the model:</b>
<p>
We need to define the model with the number of layers and the number of units (nodes).
With regards to Professor Sheldon, we are to "err on the side of many" even though it
will make minimization harder. Historically, 2 layers were used (1 being the hidden layer). Nowadays,many are used (deep learning).
</p>

<p>
During each layer, we must also define which activation function to use.
</p>
Keras Activation functions:
<ul>
  <li>softmax</li>
  <li>elu (Exponential linear unit)</li>
  <li>selu (Scaled exponential linear unit)</li>
  <li>softplus</li>
  <li>softsign</li>
  <li>relu</li>
  <li>tanh</li>
  <li>sigmoid</li>
  <li>hard_sigmoid</li>
  <li>linear</li>
</ul>
<p>
More "advanced" activation functions can be found with Keras.
</p>

<b>Compiling the model:</b>
<p>
On the compile step, we can define the loss function, optimizer, and metrics. The loss function and optimizer are both required to compile the model.
Let's start with the optimizer. We are looking to minimize the error or variance(?) on the accuracy.
</p>
Keras Optimizers:
<ul>
  <li>SGD (Stochastic gradient-descent)</li>
  <li>RMSprop</li>
  <li>Adagrad</li>
  <li>Adadelta</li>
  <li>Adam</li>
  <li>Adamax</li>
  <li>Nadam</li>
  <li>TFOptimizer</li>
</ul>
<p>
Each optimizer has its own arguments you may tune to fit your project. Some could be left to the default to limit the amount of tuning you have to do. What seems to be common with all the optimizers is
the usage of lr (learning rate) and decay.
</p>

<p>
I have heard of loss functions before, but with no experience with handling it.
</p>
Keras Loss Functions: 
<ul>
  <li>mean_squared_error</li>
  <li>mean_absolute_error</li>
  <li>mean_absolute_percentage_error</li>
  <li>mean_squared_logarithmic_error</li>
  <li>squared_hinge</li>
  <li>hinge</li>
  <li>categorical_hinge</li>
  <li>logcosh</li>
  <li>categorical_crossentropy</li>
  <li>sparse_categorical_crossentropy</li>
  <li>binary_crossentropy</li>
  <li>kullback_leibler_divergence</li>
  <li>poisson</li>
  <li>cosine_proximity</li>
</ul>
<p>
Each loss function has two arguements, y_true and y_pred. The easier approach is to pass the name of the loss function (ie. 'mean_squared_error').
</p>

<p>
For metrics, according to the documentation, we set the metrics to 'accuracy' when encountering 
a classification problem. Metrics are essentially loss functions with results from "evaluating a metric are not used when training a model".
</p>
Keras Metrics:
<ul>
  <li>binary_accuracy</li>
  <li>categorical_accuracy</li>
  <li>sparse_categorical_accuracy</li>
  <li>top_k_categorical_accuracy</li>
  <li>sparse_top_k_categorical_accuracy</li>
</ul>
<p>
A custom metric may also be passed where y_true and y pred are the arguments and the return value is a single tensor value.
</p>

<b>Training the model:</b>
<p>
Now, we finally get to actually train the data. In the fit() function, we define the data to be passed and how to execute it. The arguments include the matrix of features as the input and an output matrix which checks for the accuracy of the result. Epochs is the number of times the whole dataset will be run over. For example, epoch = 1 will feed the dataset into the neural network once (aka each row will go through the neural network once) and epoch = 10 will feed the dataset into the neural network ten times. Batch size is the number of data (rows) will be fed before the gradient is updated.
My initial thought when I saw this function is that this is where we can modify the method of feeding the data, including parallel computation. This means we can spread the work across multiple processors such as CPU, GPU, and TPU.
</p>

<b>Conclusion:</b>
<p>I have only scratched the surface of Keras. I focused only on the "Sequential model" which is one of two ways to use Keras. The other being the "Functional API" which seems more complicated.</p> 

<p>
Every decision on how to develop the model is the struggle with machine learning. (Apart from data collection/cleaning). I have only a shallow knowledge of neural networks, exploring only one method of implementing a neural network. There are many combinations of designing the model. Knowing your data, your purpose of the project and the effects each algorithm/function have on the result is a step in truly mastering machine learning.
</p>

If anyone has any questions, concerns or corrections to anything I have written, please email me.

<p>
Disclaimer: Everything I wrote here is based on the knowledge I gained from my time at University of California: Riverside CS 171: Introduction to Machine Learning and Data Mining class by Professor Christian R. Shelton and from reading the documentation on Keras' website. Therefore, do not take my words as facts, but something to cross reference. The information may be skewed incorrectly which is normal since I took the class a year ago.
</p>
