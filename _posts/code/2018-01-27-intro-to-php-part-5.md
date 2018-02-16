---
layout: blog-article
title: Intro to PHP Part 5, Forms and user input
meta: Using variables in PHP scripts
category: code
---

<p>In this post, we'll create an HTML form and use PHP to handle submitted values. Understanding how to handle forms is important for developing most websites. The first we'll write the HTML form it's self. Then, we'll write a PHP program that will receive and process the resulting form input. To create the HTML form, start with the <em> form tags </em> which look like this:</p>


{% highlight php linenos %}

<form action="process_form.php" method="post">

</form>

{% endhighlight %}

<p>Notice the <strong>action="process_form.php"</strong> part of the form tag. This controls which PHP file will be processing the HTML form. You'll also notice the <strong>method="post"</strong>. There are two different form "methods" that are commonly used. There is <strong>method="post"</strong> and there is <strong>method="get"</strong>. A "get" method means that the user input will be visible in the URL, for example <strong>http://something.com/script.php?name=Miles&gender=M</strong> The advantage of a "get" method is that the form's inputed values can easily be bookmarked by the user. The major disadvantage of the "get" method is security. anybody could just change those form values to whatever they wanted, and get around any input validation you may have set up to protect yourself from hacks. We'll get into input validation later on, but for the purposes of this series, I'll always lean toward the "post" method unless I have a very good reason not to.
<br>
Anyway, to get started, just make a new file called <strong>form.html</strong>
</p>


{% highlight php linenos %}

<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf8">
    <title>form</title>
  </head>
  <body>
  <form action="process_form.php" method="post">
  	  <fieldset>
  	  	<legend>Tell us about yourself!</legend>
  	  	<p><label>Name: <input type="text" name="name" size = "20" maxlength="40"></label></p>
  	  	<p><label>Email: <input type="email" name="email" size="40" maxlength="50"></label></p>
  	  	<p><label for="os">What's your favorite operating system?</label><input type="radio" name="os" value="Windows">Windows
  	  	<input type="radio" name="os" value="Mac">Mac
  	  	<input type="radio" name="os" value="Linux">Linux</p>
  	  	<p><label>What's your favorite browser?
  	  	  <select name="browser">
  	  	  	<option value="chrome">Chrome</option>
  	  	  	<option value="firefox">FireFox</option>
  	  	  	<option value="safari">Safari</option>
  	  	  	<option value="other">Other</option>
  	  	  </select>
  	  	</label>
  	  </p>
  	  <p><label>Message to us: <textarea name="message" rows="3" cols="40"></textarea></label></p>
  	  </fieldset>
  	  <p align="center"><input type="submit" name="submit" value="Send my information"></p>
  	</form>
  </body>
</html>

{% endhighlight %}


<a href="https://c7.staticflickr.com/1/257/31756713710_9d3efdc971_z.jpg" title="form" data-lity> <img src="https://farm5.staticflickr.com/4622/39267429764_c4c0b3a317_z.jpg" width="600" alt="form">
</a>



<h2>Break it down!</h2>
<p>Once again, I'll break this code into small chunks, and discuss them in detail.</p>

{% highlight php linenos %}
	<form action="process_form.php" method="post">
{% endhighlight %}
<p>This form's action attribute points to a file called <strong>process_form.php</strong>, which we will create in the next step.</p>
<br>

{% highlight php linenos %}
	<fieldset>
  	  	<legend>Tell us about yourself!</legend>
  	  	...
{% endhighlight %}

<p>The <strong>fieldset</strong>tags help group the form's content and add a box around it. This is optional, but I like the way it looks.</p>
<br>

{% highlight php linenos %}
		<p><label>Name: <input type="text" name="name" size = "20" maxlength="40"></label></p>
  	  	<p><label>Email: <input type="email" name="email" size="40" maxlength="50"></label></p>
{% endhighlight %}
<p>These are textarea boxes for users to enter their name and emails. The label tags are used to associate each text label with it's corresponding input area</p>
<br>

{% highlight php linenos %}
	<p><label for="os">What's your favorite operating system?</label><input type="radio" name="os" value="Windows">Windows
  	  	<input type="radio" name="os" value="Mac">Mac
  	  	<input type="radio" name="os" value="Linux">Linux</p>
{% endhighlight %}

<p>Radio buttons can only be selected one at a time. since these radio buttons all have the same "name" then only one can be seleced at a time.</p>
<br>

{% highlight php linenos %}
  	  	<p><label>What's your favorite browser?
  	  	  <select name="browser">
  	  	  	<option value="chrome">Chrome</option>
  	  	  	<option value="firefox">FireFox</option>
  	  	  	<option value="safari">Safari</option>
  	  	  	<option value="other">Other</option>
  	  	  </select>
  	  	</label>
  	  </p>
{% endhighlight %}
<p>Here's a <strong>pull down menu</strong>, which starts with a select tag, and each option tag stands for a new line in the pull down menu. Here, four options are avalible. Similar to a radio button, only one option can be selected at a time.</p>
<br>

{% highlight php linenos %}
		<p><label>Message to us: <textarea name="message" rows="3" cols="40"></textarea></label></p>
{% endhighlight %}
<p>Here's a <strong>textarea</strong>, which are just another form of text input, which allow users to enter in much more information. Textareas are presented as a box, instead of a single line.</p>
<br>

{% highlight php linenos %}
</fieldset>
  	  <p align="center"><input type="submit" name="submit" value="Send my information"></p>
  	</form>
{% endhighlight %}
<p>Finally, this submit button is what actually sends the user's unput to the PHP file that we are about to create. All of the data that the user entered will be accessable to PHP. The PHP program will store the user's data into variables, and then output those variables back to the browser. So far this post has only been about HTML, but not it's time to <em>finally</em> write some PHP to process this form! And at the same time, I'll introduce a new programming concept called <strong>conditionals</strong>, which we will use to process our form.</p>

<h2>Conditionals</h2>
<p>Conditionals allow for the execution of sections of code depending on whether or not a certain <em>condition</em> is true or not. For example:</p>

{% highlight php linenos %}
	$a = 1;
	$b = 2;
	if ($a > $b) {
	    echo "a is bigger than b";
	} elseif ($a == $b) {
	    echo "a is equal to b";
	} else {
	    echo "a is smaller than b";
	}
{% endhighlight %}
<p>The above code will output "<strong>a is smaller than b</strong>"</p>
<br>
<p>Now back to our form. Since the HTML form above says "form action="<strong>process_form.php</strong>" we'll have to also name our new PHP file <strong>process_form.php</strong> and enter the following code.</p>


