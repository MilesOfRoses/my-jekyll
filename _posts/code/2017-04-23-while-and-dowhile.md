---
layout: blog-article
title: What's the difference between a "do...while" loop and a "while" loop in JavaScript?
meta: They seem similar, but there is an important functional difference 
category: code
---
<p>So, JavaScript has a "while" loops and a "do... while" loops. sure, they're written a little bit differently, but ther're mostly the same right?<br>
Wrong!<br>
Here is the syntax for a while loop:</p>

{% highlight javascript linenos %}
 var a = 1; //initialize a counter
 while (a < 10) { //sets the loop's condition
 	console.log(a); //code block to execute for each iteration of the loop
 	a++; //increment the counter by 1 for each iteration of the loop
 }
 //outputs 1 2 3 4 5 6 7 8 9
 {% endhighlight %}

<p>And here is the syntax for a do... while loop:</p>

{% highlight javascript linenos %}
 var a = 1; //initialize a counter
 do { 
 	//code block to execute for each iteration of the loop
 	console.log(a);
 	a++;  //increment the counter by 1 for each iteration of the loop
 } while (a < 10); //sets the loop's condition
 //outputs 1 2 3 4 5 6 7 8 9
 {% endhighlight %}

<p>The most important difference to note here is that in a "while" loop, the loop's condition is checked <i>before</i> the code block within the curly braces is able to be executed. <br>
So if the condition of a "while" loop is false, the code block won't be executed.
<br><br>
In contrast, in a "do... while" loop, the loop's condition is checked <i>after</i> the first iteration of the code block within the curly braces has already been executed. 
This is an important distinction, because a "do... while" loop's code block is always executed at least once, regardless of whether it's condition is true or false. 
<br><br>
However, a "while" loop's code is only executed if the loop's condition is true. 
<br>
"while" loops are used far more often than "do... while" loops because you would typically want to check whether a loop's condition is true before you execute the first iteration of it's code block. I also find "while" loops to be easier to read.</p>