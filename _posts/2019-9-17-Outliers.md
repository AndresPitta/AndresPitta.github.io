---
layout: post
title: Outliers
---

<h1 style="font-size:200%;text-align:center">A Quick Explanation on Outliers and Why We Should Care About Them</h1>

Hola everyone, I decided to write my first post about outliers. This is a very common concept when handling data and it can, often times, be problematic when building predictive models. On this post I am going to explain what an outlier is and how they can affect our results. In addition, I am going to explain briefly the concept behind finding outliers. So, I hope you enjoy: 

![alt text](https://i.makeagif.com/media/8-18-2017/S_jkMJ.gif "Me Typing - not me, really")

[source](https://i.makeagif.com/media/8-18-2017/S_jkMJ.gif)

<h2 style="text-align:center">What is an outlier?</h2>

Imagine having a group of 10 friends and all of you are the almost the same height (five of you are 5'5" and five of you are 5'7"). For your group of friends, the average height would be 5'6" and the distance between each individual person and the average is not higher than 1 inch. For this distribution, it seems like there is no height value that behaves differently from the other values.

Now, imagine that you meet someone called _Bob_ on your vacations to <b>Colombia</b> and it turns out that your new friend is from the same city as you are. When you come back to your city, you introduce _Bob_ to your friends and they all like him - he is a cool guy. Now that you have a new friend, you want to know your group of friend's height distribution again. As you already noticed, _Bob_ is really tall, so you ask him and he tells you that he is 120' (<i><b>Bob doesn't like it when you question his height</b></i>). You then proceed to check your new distribution and you realize that your group's average height changed to 14'11" (Also, the highest distance to the average becomes 105').

<b>Amazing, isn't it?</b>

Well, in this example _Bob's_ height might be considered to be an <b>outlier</b>. According to wikipedia, an [outlier](https://en.wikipedia.org/wiki/Outlier) is a "data point that differs significantly from other observations". So, given that your and your friend's height is around 5'6", _Rob's height seems be differing significantly from other observations_.

<h2 style="text-align:center">Why should we care about them?</h2>

Say, for example, that you want to guess one of your friend's height based on your other friends. One safe bet is to guess her height as the average height of the group. Based on your group of friends before you met _Bob_, you would guess that your other friend is 5'6". This is a pretty close guess because her possible height can be either 5'5" or 5'7". Using the average height to predict your friend's height worked for this scenario. 

On the opposite case of the example, you can guess her height after you met _Bob_. For this scenario, your guess would be 14'11". When comparing the possible outcomes to your new results, it seems like you think she is way taller than she really is.  

In statistics, the exercise I tried to replicate with the example is called _prediction_ (or in a more technical way a [prediction](https://stats.oecd.org/glossary/detail.asp?ID=3792) is the process of estimating an outcome in a future point in time). So, having an outlier in your dataset can lead to overestimation problems or underestimation problems or, in general, to misleading results.

<h2 style="text-align:center">What could be a problem handling outliers?</h2>

Up to this point, we decided that _Bob_ is 120' tall. This is, undoubtedly, a very tall person. But what happens if _Bob_ now is 6'5"? 

<b>Is he still an outlier?</b>

Defining the correct "threshold" for what an outlier is or is not considered can be a very complicated task. It depends mostly on the type of data you are handling. For some people, 6'5" can be a close number to the distribution. For others, it can be an outlier. Learning some methods to identify outliers is not going to be discussed on this post, but I hope the explanation I just gave you helps you to understand the concept behind it.

<h2 style="text-align:center">In conclusion</h2>

Outliers is a concept to consider when doing a prediction. Having an extremely high (or low value) can affect some measures such as the mean or the variance of a distribution. This can end up in having misleading conclusion in your results. So, next time you read me, I hope you have taken care of those outliers.

<h2 style="text-align:center">Reference</h2>

https://en.wikipedia.org/wiki/Outlier
https://stats.oecd.org/glossary/detail.asp?ID=3792














