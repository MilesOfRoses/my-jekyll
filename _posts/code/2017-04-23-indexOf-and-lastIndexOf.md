---
layout: blog-article
title: How does the JavaScript method "indexOf" and "lastIndexOf" work?
meta: In this article, we'll learn how "indexOf" and "lastIndexOf" work in javascript
category: code

---
<p>The indexOf method will index a string to find whether or not a particular term or word appears in a string or not, and it also indicates what character position that term or word appears. 

For example, we have a string that says "Hail to the king, baby!"
and we want to find out what character position the word "king" appears at. </p>
<p>

{% highlight javascript linenos %}

var phrase = "Hail to the king, baby!";
var position = phrase.indexOf("king");
console.log("That word appears at character position " + position); 
//outputs "That word appears at position 12"

{% endhighlight %}


<p>But what if we try to find the index of a word that doesn't appear in the string, like the word "prince"? By default, the indexOf method will return "-1" if a word is not found.</p>

{% highlight javascript linenos %}

  var phrase = "Hail to the king, baby!";
  var position = phrase.indexOf("prince");
  console.log(position); 
  //outputs -1 
{% endhighlight %}

<p>But that "-1" isn't very informative unless you already know what it means, so it would be more useful to set up an if statement to handle cases where the word is not found.</p>

{% highlight javascript linenos %}
 var phrase = "Hail to the king, baby!";
 var position = phrase.indexOf("prince");

 if (position === -1) {
 console.log("That word isn't here!");
 } else {
 console.log("That word appears at character position " +position); 
 //outputs "That word isn't here!"
 {% endhighlight %}

<p>But what if you have multiple occurances of the same word or term, and you want to find the last occurance?
The method "lastIndexOf" would be useful for that.
For example, if you have the string that has the same word twice, like "Hail to the king, baby! I'm the king!"
and you want to find the position of the last occurance of the word "king" you could use the following code</p>

{% highlight javascript linenos %}
 var phrase = "Hail to the king, baby! I'm the king!";
 var position = phrase.lastIndexOf("king");
 console.log("That word appears at character position " +position); 
 //outputs "That word appears at character position 32"
 {% endhighlight %}
 
 <p>
 This is just one simple example of a use-case for the built in JavaScript methods "indexOf" and "lastIndexOf"
</p>

