---
layout: blog-article
title: console.log's friends, The four other types of JavaScript console messages
meta: An over view of the different types of console messages
category: code
---
<p>The most common type of console message is console.log() which simply logs the contents within the parentheses out to the browser's developer tools console section. However, there are additional console message types that could be useful in different situations.</p>

<a data-flickr-embed="true"  href="https://www.flickr.com/photos/146669889@N04/33388813124/in/dateposted-public/" title="console messages"><img src="https://c1.staticflickr.com/3/2939/33388813124_cc51ef2eb6_m.jpg" width="800" alt="console messages"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script><br>
<a href="http://blog.500tech.com/browser-console-tricks/" style="color:grey">image courtesy of 500Tech</a>
<br><br>

<p>The first is <span style="color:grey">console.debug</span>, which looks the same as a normal console.log() message, and is very useful for debugging code.</p>

<p>Then there is <span style="color:blue">console.info(),</span> which will make a little blue info icon appear next to the console message. This could be useful to help keep track of some status information in your code, and make it easy to distinguish from other console messages.</p>

<p>The next is <span style="color:orange">console.warn()</span> which will make a yellow warning icon with an exclemation mark next to the console message. The warning icon is useful to indicate that a potential error could occur, but has not yet happened.</p>

<p>The third is <span style="color:red">console.error()</span> which will make a red error icon next to the console mesage. An error counter will also appear in the status section of the browser's developer tools console. This message is useful to indicate that a problem has already occured. The message should describe what the error is, and ideally offer some solution. Creating custom error messages could be very useful for debugging, rather than only trying to interprit javadcript's default error messages.</p>

<p>It could be helpful to output different console message types for different situations. Their colors and icons make different console messages easy to spot while scanning through console output.</p>
