---
layout: post
title: Server Admin for free labor?  
categories: spark 
---

<h2>Fixed one problem</h2>
<p>
I spent a good afternoon figuring out why I cannot send out data. I learned after reading the python docs on sockets what each function did. For example, I found out that socket.accept() returns both a connection and address. I also learned that I should seperate my client python file with the server file since the server is constantly listening for another connection to be made to it. 
</p>

<h2>Found another problem</h2>
<p>
Now I need to see if the stream object is sending data over the connection. I tried sending a byte value and it worked. I'm not sure how to send a dictionary since that's what I get from twitter-python's GetStreamFilter function.
</p>

<h2>And another problem</h2>
<p>
SparkContext() does not work. This is disheartening because it is caused by my installation of pyspark. I assumed that installing through pip should be the easiest and less troublesome method. So far, I've had to add environment variables and I fear that I might need to do more.
</p>

<p>
A possible solution is to tackle each error that is returned. Another option is to install Spark using something other than pip. It seems like a lot of solutions got resolved by people using another installation method such as Anaconda and Jupyter notebook. 
</p>
