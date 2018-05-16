---
layout: post
title: Loss functions 
categories: keras 
---

<h2>Introduction</h2>
<p>
Loss functions are generally straight forward. Its purpose is to minimize the amount of error rate. There are multiple ways to do this, and they are all just simple functions.
</p>

<h2>Loss functions</h2>
<ul>
    <li>Mean squared error</li>
        <p>
            This is the difference of the predicted value and the true value. It is then squared and factored into the mean.
        </p>
    <li>Mean absolute error</li>
        <p>
            This is the difference of the predicted value and the true value. It then takes the absolute value and then factored into the mean.
        </p>
    <li>Mean absolute percentage error</li>
        <p>
            This is mean absolute error, but with the caveat that it is in percentage form.
        </p>
    <li>Mean squared logarithmic error</li>
        <p>
            This is the difference of the logarithmic versions of the predicted value and true value. It is then squared and factored into the mean.
        </p>
    <li>Squared hinge</li>
        <p>
            This is a difference between 1 with the product of the true and predicted values. The squared value of the higher value between the result and 0 is then factored into the mean.
            <br />Psuedo code: 
                <br />mean(square(maximum(1 - true * predict, 0)))
        </p>
    <li>Hinge</li>
        <p>
            It is squared hinge without squaring the value.
        </p>
    <li>Categorical Hinge</li>
        <p>
            This is the higher value between 0 and the equation "neg - pos + 1". "pos" is the sum of the values in the tensor and the product of true values with predicted values. "neg" is the max value in the tensor after finding "(1 - true) * predict".
            <br />Pseudo code: 
                 <br />pos = sum(true * predict)
                 <br />neg = max( (1 - true) * predict)
                 <br />return maximum(0, neg - pos + 1)
        </p>
    <li>Logcosh</li>
        <p>
            Taken from the source code, it is the logarithm of the hyperbolic cosine of the prediction error. A closer look at the equation can be found at <a href="https://github.com/keras-team/keras/blob/master/keras/losses.py">loss</a>.
        </p>
    <li>Categorical crossentropy</li>
        <p>
            Crossentropy is the comparison between the true and predicted values. For values that are close to each other has a lower loss. For values that are far apart has a higher loss. Therefore, the correct label would result in a loss closer to 0 and an incorrect label would result to a loss closer to 1. It is the negative sum of the true value multiplied with log(predict). Thereby, categorical crossentropy is crossentropy used for multiple labels. 
        </p>
    <li>Sparse categorical crossentropy</li>
        <p>
            This loss function is crossentropy used for labels that are sparse in distribution.
        </p>
    <li>Binary crossentropy</li>
        <p>
            This loss function is crossentropy used for two labels.
        </p>
    <li>Kullback leibler divergence</li>
        <p>
            Clip the values of true and predicted values between epsilon and 1. Then sum the values of the tensor and the result from "true * log( true/predict )". 
        </p>
    <li>Poisson</li>
        <p>
            This is a mean of "predict - true * log( predict + epsilon)".
        </p>
    <li>Cosine proximity</li>
        <p>
            First, normalize both true and predicted values with respect to L2. Then the cosine proximity is the sum of the tensor with the product between normalized values. 
        </p>
</ul>
<h2>Conclusion</h2>
<p>
    There are many methods to simply minimize the difference between the predicted values given by a neural network and the true value. Keras natively has the popular methods built into the library. Each loss function had less than 10 lines of code with the majority being a simple formula to execute.
</p>
