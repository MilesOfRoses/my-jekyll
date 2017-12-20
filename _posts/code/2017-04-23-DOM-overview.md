---
layout: blog-article
title: Document Object Model Overview
meta: A very brief overview of thd Document Object Model (DOM)
category: code
---


<p>"DOM" stands for Document Object Model.<br>
<b>Document</b> = A web page (Either viewed through the broweser, or the source code)<br>
<b>Object</b> = Any pieces of a HTML (titles, paragraphs, headings, lists, etc...)<br>
<b>Model</b> =  The relationship that different pieces of HTML have to each other, represented in a tree hierarchy.<br><br>

The DOM is an agreed upon set of terms that allows a JavaScript program to navigate an HTML document. The DOM allows a JS program to traverse into any webpage to manipulate elements of that page. So the DOM is more of a concept, rather than a language.<br><br>

For example, a JS program can traverce the DOM to get the text of the title, to get the second paragraph, even to get the third link in the menu and set it's CSS to display:none<br><br>

By traversing the DOM, a JS program could change the background color of all paragraphs with a class of "important", or change a link's behavior so that it performs a JS function when clicked.</p>


<p>The Document Object Model is the means by which a JacaScript program can interact with HTML on a webpage.
The DOM represents HTML elements in terms of "nodes" on a tree hierarchy structure. Every html page is made of these nodes. Look at the HTML code on the left, and compare it to the simple tree structure on the right.</p>

<a data-flickr-embed="true"  href="https://www.flickr.com/photos/146669889@N04/33844356290/in/dateposted-public/" title="nodes of the DOM"><img src="https://c1.staticflickr.com/3/2915/33844356290_71b41fe740_m.jpg" width="1000" alt="nodes of the DOM"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

<p>In this simplistic example, we can see a tree with one node per html element.
But an html file is more than just elements! There are attributes, text, comments etc. There is a lot of text in this example that isn't being represented on the DOM tree. Also, there are typically one or more attribures as part of an HTML element, as well as comments.<p>
<p>
All of those things are seen as different kinds of nodes in the DOM.
The reason for this is so that we can use javascript to get to them directly.
JS can target the text inside of the second paragraph, find the source attricute of an image tag, etc...

 So the real DOM diagram would be quite complex and crowded if we displayed ALL of the nodes. There would not only be nodes that represent elements, but also nodes for attributes, text, comments etc...</p>

<a data-flickr-embed="true"  href="https://www.flickr.com/photos/146669889@N04/33844356500/in/dateposted-public/" title="ALL THE NODES"><img src="https://c1.staticflickr.com/5/4172/33844356500_ce297ae542_m.jpg" width="650px" alt="ALL THE NODES"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>
<p>
There are 12 different types of nodes in total:<br>
1 element nodes,<br>
2 attribute nodes,<br>
3 text nodes<br>
4 CDATA (text that will NOT be parsed by a parser) nodes<br>
5 entity refrence nodes,<br>
6 entity nodes,<br>
7 processing instruction nodes,<br>
8 comment nodes,<br>
9 document nodes,<br>
10 documentType nodes,<br>
11 documentFragment nodes,<br>
12 notation nodes.<br>
</p>

<p>This has been only a general overview of the DOM. For more in depth knowledge about the DOM, check out <a href="https://www.guru99.com/how-to-use-dom-and-events-in-javascript.html" class="redlink" target="blank">this  article by Guru99</a></p>