---
layout: blog-article
title: Intro to PHP Part 1, Installation
meta: How to install PHP for local development, using Windows
category: code

---

<p>It's been a few months since my last post, and I've learned a lot about PHP programming during that time. So I've decided to create this series of articles explaining what I've learned so far in the world of PHP! 
<br>
PHP is a server-side web language, as opposed to JavaScript, which is a client-side language that runs in the browser. This means that in order to program in PHP, we will either need to connect to a server through a hosting company that already has PHP installed on it, or we can simply install our own server on our own computers for development / learning purposes. I'm not going to assume that everybody reading this has access to a hosting server, especially if you are just getting started, so the first thing I'll do is show you how to install an Apache server on your own computer so that you can run PHP locally. This is just one method of running PHP, but I think that it is the easiest method for beginners, and it doesn't involve spending any money! </p>

<h2>Installing PHP on Windows</h2>
<p>I'm using windows, so I'll focus on this OS in more detail. I installed PHP using software called <a class="redlink" target="blank" href="http://www.wampserver.com/en/">WampServer</a>. The acronym "WAMP" stands for "Windows", "Apache", "Mysql", and "PHP". This software will install PHP along with MySql, and Apache. This is useful, because chanses are, if you're learning PHP programming, you'll probably want to have MySql on your machine as well, as these technologies are often used together. The installation is fairly self explanatory, once it is finished you should see the icon for wampserver in your taskbar. Click this icon, and a small popup window will appear. Select "start all services" option, which will start the PHP and Apache servers. Then click "localhost", if everything is working, it should automatically open a browser window with the heading "Server Configuration" and information about your Apache and PHP versions. </p>

<h2>Installing PHP on Linux</h2>

<p>Linux is a great choice for running PHP, as both are open source. Here is a great simple article from <a class="redlink" target="blank" href="http://howtoubuntu.org/how-to-install-lamp-on-ubuntu">How To Ubuntu</a> that explains the process in detail.</p>
<h2>Installing PHP on Mac</h2>
<p>If you're running Mac, you probably alredy have PHP and Apache preinstalled! But you may want to update to the latest versions using <a class="redlink" target="blank" href="https://www.mamp.info/en/">MAMP</a> and be sure you are using port (80)</p>

<p>Now that everything is installed, it's time to write a simple webpage to test that Apache is working. Open your favorite text editor and type/paste the following to create a bare bones webpage:</p>

{% highlight php linenos %}
<html>
  <head>
    <title>Testing Apache</title>
  </head>
  <body>
    <h1>Testing</h1>
  </body>
</html>
{% endhighlight %}

<p>Save this as <strong>testing.html</strong> and save it in the root folder of the server. When you installed apache it comes with a default Web
site folder. If you're on Windows, your server's root folder should be something like <strong>C:\wamp\www</strong>
<br>
If you're on Ubuntu Linux, the server's root folder should be something like <strong>/var/www</strong>
<br>
If you're on Mac, and if MAMP was installed into the <strong>/Applications</strong> folder, then the root folder should be something like <strong>/Applications/MAMP/htdocs</strong>
<br>
Once you've saved <strong>testing.html</strong> to the right folder, then open a browser and type/paste the following: <strong>http://localhost/testing.html</strong> If everything worked out, this address should show your new web page! If it worked, congratz! You installed Apache! If it didn't, double check to make sure PHP and Apache are running, and double check that you saved into the right folder.
<br>
NOTE: If you're on a mac, and you didn't set apache to use port (80), it's probably still using it's default port of 8888. You'll just have to use this address instead <strong>localhost:8888/testing.html </strong> and it should work.
<br>
Now that Apache is working, we'll test PHP to make sure it's working right. Open your text editor again and make a new text file called <strong>testing.php</strong>. Save it in the same root folder, next to testing.html. Now type the following PHP code, which will display information about your PHP installation</p>

{% highlight php linenos %}
<html>
  <head>
    <title>Testing PHP</title>
  </head>
  <body>
    <?php
	phpinfo();
    ?> 
  </body>
</html>

{% endhighlight %}
<p>As you can see, PHP can be nested inside of the body tags of an html document.</p>

<p>One thing to note s that since the PHP code is being parsed by your apache server, you can only access the page through a URL like this:
<br>
<strong>http://localhost/testing.php</strong> (Windows) 
<br>or <br>
<strong>http://127.0.0.1/testing.php</strong> (Linux)
<br>or<br>
<strong>http://localhost/~&lt;user&gt;/testing.php</strong>(Mac) 
<br>
if you try to access this page through your file directory like any normal HTML file on your hard drive like this <strong>file:///C:/wamp64/www/testing.php</strong> then the PHP code will not work. It MUST be accessed through a URL.</p>

<p>Open your browser again and type <strong>http://localhost/testing.php</strong>. This should bring up a purple screen with text saying something like <strong>PHP Version 5.6.31</strong>(Newer versions will likely have been released since the writing of this post).
<br>
phpinfo(); is a usefull built in function that will display information about your version of PHP. If you've made it this far, then you've successfully installed both Apache and PHP! Now you're ready to start the next post in this series, where we'll actually get started programming in PHP!</p>

<br>
<p id="smallText">Special thanks to Larry Ullman, whose textbooks helped me learn PHP programming (no affiliation)</p>