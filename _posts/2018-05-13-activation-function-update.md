---
layout: post
title: Activation Functions (Update)
categories: keras 
---

<p>
Just a quick update to a previous blog post I made on activation functions. Here, I will note which functions to use and which ones are outdated.
</p>

<h2>Usfeful</h2>
<p>
<ul>
    <li>RELU</li>
        <p>
            A caveat with this activation function is that it must only be used in the hidden layers. Should dead neurons be observed, another activation function should be taken since RELU is prone to dead gradients. The benefits to using RELU outweighs most reasons to go with another choice. It is computationally cheaper and solves many problems that older activation functions had such as the vanishing gradient problem. 
        </p>
    <li>Softmax</li>
        <p>
            This activation function should be used on classification problems since it transforms inputs to a percentage value.
        </p>
    <li>Linear</li>
        <p>
            This one is useful for regression problems because it maintains the correlation to the original function.
        </p>
    <li>SELU</li>
        <p>
            With RELU being in this list, SELU must also be in here. The choice to use this is unclear at the moment when to use this as a replacement to RELU. Although, tests have shown that the accuracy is higher and converges earlier on some datasets. For now, unless more experiments are done, go with using RELU. 
        </p>
    <li>ELU</li>
        <p>
            As with RELU and SELU being on this list, ELU also deserves to be on here because it can incorporate negative values unlike RELU. I would prefer to go with RELU unless negative outputs are needed which would mean ELU is suddenly useful.
        </p>
</ul>
</p>

<h2>Outdated</h2>
<p>
<ul>
    <li>Sigmoid</li>
        <p>
            This is an old activation function that is rarely, if ever, used today in deep learning. There are numerous problems that coincides with its usage that other activation functions are preferrable.
        </p>
    <li>Hard Sigmoid</li>
        <p>
            It is self explainatory that since sigmoid is outdated, hard sigmoid is also outdated. Hard sigmoid is just a more efficient sigmoid function so it will follow whatever category sigmoid ends up at.
        </p>
    <li>Tanh</li>
        <p>
            Tanh suffers to the same problem as sigmoid and should also be avoided.
        </p>

    <li>Softsign</li>
        <p>
            Similar in its function to sigmoid and tanh, we will also avoid using this function. 
        </p>
    <li>Softplus</li>
        <p>
            Unlike the others in this list, softplus is here because RELU is the more efficient function. They both follow the same general path, but softplus requires computation using log() and exp() which are more computationally costly. 
        </p>
</ul>
</p>
