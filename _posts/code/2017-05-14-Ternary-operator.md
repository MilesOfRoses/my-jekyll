---
layout: blog-article
title: What is the "Ternary" operator, and how is it used?
meta: In this article, we'll learn about the ternary operator
category: code

---
<p>As opposed to a Binary operator which focus on two elements (such as "foo > bar" or "dollars / hour) a Ternary operator instead focuses on 3 elements. 
The ternary operator has 2 symbols, the question mark "?" and the colon ":" the syntax looks like this  </p>


{% highlight javascript linenos %}

Condition ? true : false

{% endhighlight %}


<p>This is the equivilent of a mini if/else statement. For example, the following code with if/else statements could be refactored with the ternary operator.</p>

{% highlight javascript linenos %}
var playerOne = 500;
var playerTwo = 600;

 var highScore;
 if (playerOne > playerTwo){
 highScore = playerOne;
 } else {
 highScore = playerTwo
 }
{% endhighlight %}

<p>The above code is equivilant to the following code, which replaces if/else statements with a single ternary operator</p>

{% highlight javascript linenos %}
var playerOne = 500;
var playerTwo = 600;

var highScore = (playerOne > playerTwo) ? playerOne : playerTwo ;
 {% endhighlight %}

<p>The condition is "Is the value of playerOne greater than playerTwo?" The result can either be true or false. If it's true, we will assign the value of playerOne to the variable highScore.
If it's false, we will assign the value of playerTwo to the variable highScore.</p>


