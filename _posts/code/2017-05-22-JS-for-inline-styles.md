---
layout: blog-article
title: How to use JavaScript to write dynamic inline styles
meta: I'll show how to use JS to write CSS styles
category: code

---
<p>Using JavaScript, we can programmatically change our webpage's style and presentation. One way to do this is to use JS to select an element and give it an inline style.<br> First we'll need to select an element. Let's assume we have an HTML element with the ID of "mainContent"</p>


{% highlight javascript linenos %}

var mainContent = document.getElementById("mainContent"); 

{% endhighlight %}


<p>Once we have selected the element that we want to style, we can use the same styles that we would use in CSS. For example, to change font color:</p>

{% highlight javascript linenos %}
mainContent.style.color="#ff0000"; //changes font color to red
{% endhighlight %}

<p>Or to add 50 pixels of margin around the selected element</p>

{% highlight javascript linenos %}
mainContent.style.margin="50px";
 {% endhighlight %}

<p>Any style property that can be written usng CSS can also be dynamically written using JavaScript as a string. JS uses the same pixel units as CSS. Just make sure the semicolon is outside of the string quotes. <br>
One important difference between style properties written in JavaScript vs CSS is that JavaScript uses camelCase, while CSS uses hyphen-spaced-text. for example, in CSS we would write this:</p>


{% highlight css linenos %}
#mainContent{
    background-repeat: repeat-x;
}
 {% endhighlight %}

 <p>While in JavaScript, we would write that same line in CamelCase:</p>


{% highlight javascript linenos %}
mainContent.style.backgroundRepeat = "repeat-x";  
 {% endhighlight %}


<p>This is not just an arbitrary quirk of JS. In JS, any "-" would be interpreted as "minus" <br>for example, saying "background minus repeat" which wouldn't make any sense. <br> Keep in mind that we obviously will still want to keep most of our styles seperate in our CSS file, away from our .js file. This method is only useful if we NEED to have a style property changed dynamically in a way that CSS alone wouldn't be capible of by it's self.</p>