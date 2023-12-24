---
layout: blog-article
title: Intro to PHP Part 4, Numbers and math operators
meta: Using variables in PHP scripts
category: code

---
<p>In this fourth post in the PHP series I'll go over numbers and math operators. There are two types of numbers, <strong>integers</strong>, which are whole numbers, and <strong>floats</strong> which are decimal numbers. These numbers never have quotation marks around them, the way that strings always do. You can perform math using the following operators:</p>



<ul class="blog">
	<li>+ (addition)</li>
	<li>- (subtraction)</li>
	<li>* (multiplication)</li>
	<li>/ (division)</li>
	<li>% (modulos)</li>
	<li>++ (increment)</li>
	<li>-- (decrement)</li>
</ul>

<p>PHP also has a number of built in functions for working with numbers. For example, there is the <strong>round()</strong> function, which will round a number to the desired decimals. Here's an example:</p>


{% highlight php linenos %}

$number = 3.141592;
$number = round($number, 2);
echo"$number";

{% endhighlight %}
<p>The following code will output <strong>3.14</strong> rather than 3.141592 because the round() function is rounding to 2 decimal places. Another useful number function is <strong>number_format()</strong> which will add commas to group numbers by thousands. Here's an example:</p>

{% highlight php linenos %}

$bigNumber = 100000000;
$bigNumber = number_format(bigNumber)
echo"$bigNumber";
{% endhighlight %}

<p>This will output <strong>100,000,000</strong> complete with those two commas, which makes the number much easier to read. 
<br>
Now to practice using math operators, let's make a new file called <strong>program3.php</strong> in which we'll perform some simple math operations that could apply to a retail store or ecomerce application. You'll notice that I use <em>comments</em> in this program, which are preceded by double slashes <strong>//</strong> This is simply to make the code more understandable for us programmers. The users will not be able to see any PHP comments.</p>

{% highlight php linenos %}

    <?php
    //defining the variables
    $quantity = 30; //buying 30 items
    $price = 5.99;
    $tax_rate = .05; //5% tax rate

    //calculate total at checkout
    $subtotal = $quantity * $price;
    $total = $subtotal + ($subtotal * $tax_rate); //calculate total and add tax

    //format the total
    $total = number_format($total, 2); 

    //print the results
    echo"<p>You are buying $quantity items at a price of $price each, for a total of $$total";
    ?>

{% endhighlight %}

<a href="https://c7.staticflickr.com/1/257/31756713710_9d3efdc971_z.jpg" title="program1" data-lity> <img src="https://farm5.staticflickr.com/4755/39247118574_6c79f5077a_z.jpg" width="600" alt="program1">
</a>
<h2>Break it down!</h2>
<p>This program is a fair bit longer than the other ones we've written together so far, so I'll break this one down into smaller pieces and explain each chunk in detail.</p>


{% highlight php linenos %}

    $quantity = 30; //buying 30 items
    $price = 5.99;
    $tax_rate = .05; //5% tax rate

{% endhighlight %}

<p>In the code above, I've defined three variables and <em>hard coded</em> their values in. Later on, I'll show how to use <em>user input</em> through an HTML form to generate these values instead, so that this program is more dynamic.</p>

<br>

{% highlight php linenos %}

    $subtotal = $quantity * $price;
    $total = $subtotal + ($subtotal * $tax_rate); //calculate total and add tax

{% endhighlight %}

<p>The above code is where the actual calculation takes place. The first line establishes the <em>subtotal</em> as being the number of items multiplied by the price of the items. The second line then adds the tax rate, by multiplying the tax rate by the subtotal, thereby finding the <em>total</em> cost.</p>
<br>

{% highlight php linenos %}

    $total = number_format($total, 2); 

{% endhighlight %}

<p>In the code above, I'm using the <strong>number_format()</strong> function that I mentioned earlier. This will round the output to two places after the decimal. If I hadn't used <strong>number_format()</strong> then the output would have been <strong> $188.685</strong> instead of <strong> $188.69</strong>.</p>

<br>

{% highlight php linenos %}

    echo"<p>You are buying $quantity items at a price of $price each, for a total of $$total";

{% endhighlight %}

<p>This last step just outputs the result into a sentence, using the methods discussed in the last post. That's all there is to it! You can experiment with different values for the first three variables. For example:</p>

{% highlight php linenos %}

    $quantity = 2340; 
    $price = 1319.45;
    $tax_rate = .05; //5% tax rate

{% endhighlight %}

<p>Plugging these numbers in will result in a total of <strong>$3,241,888.65!</strong> 
<br>
In the next post, we'll learn about <em>user input</em> and how to use them in your PHP programs to handle submitted values</p>

<br>
<p id="smallText">Special thanks to Larry Ullman, whose textbooks helped me learn PHP programming (no affiliation)</p>