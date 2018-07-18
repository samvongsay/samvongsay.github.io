---
layout: post
title: Connecting to websites using Python
categories: python
---

<h2>Introduction</h2>
<p>
Although I have connected to websites to using REST API, but with Javascript's AJAX. This time, I needed to do this in Python since I am aiming to streamline my workflow by using one language. For such a easy language to learn (Python), the process to connect to a website requires more parameters than AJAX. All this learning is to use Apache Spark streaming by acquiring data from the Twitter API. 
</p>

<h2>The beginning</h2>
<p>
My first hurdle was that requests and requests_oauthlib were libraries not natively included with the base install of Python which was annoying compared to AJAX which is built-in. A problem I have not encountered in a long time was the mistyping of requests_oauthlib.OAuth1() as requests.oauthlib.OAuth1(). Since I do not use an IDE (a personal choice because I love VIM and not relying on intellisense lets me learn methods/functions), it took me a few minutes to realize my mistake.
</p>

<p>
As with learning anything new, I like to look at tutorials that fully cover from beginning to end. In this case, I Google'ed "apache spark streaming twitter" and found a perfect learning resource immediately in the first page. It went through setting up the Twitter API, the Python code to get tweets from Twitter and sending it to Apache Spark. I skimmed through the tutorial and decided to follow it. However, as I type each line, I would look at the documentation on each method and parameters to see why certain things were used. For example, the function "socket.socket(socket.AF_INET, socket.SOCK_STREAM)" is used to define the type of address family the socket will be using. AF_INET relates to IPV4 and SOCK_STREAM relates to TCP. Luckily, I have heard and am familiar with IPV4 and TCP, so I guess my class in Unix systems was actually useful. 
</p>


<h2>Conclusion</h2>
<p>
I wanted to learn Apache Spark streaming by processing real data. My criteria required I need a constant data generation so downloading a set of data was out of question. Since Twitter had an API, I could use it instead of web scraping which can be illegal depending on the website and I had no time for that.
</p>
