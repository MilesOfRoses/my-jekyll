---
layout: blog-article
title: Using Super Mario Bros to learn about JavaScript Constructor functions and Prototypes
meta: Mario and Luigi can teach us a lot about coding!
category: code

---


<a href="https://c1.staticflickr.com/5/4220/34875075235_ca81d8ec12_z.jpg" data-lity data-lity-desc="step1"><img src="https://c1.staticflickr.com/5/4220/34875075235_ca81d8ec12_z.jpg" width="100%" alt="step1"></a>




<p>Today we'll use Nintendo characters to help us learn about JavaScript Constructor functions and Prorotypes! <br>
Creating objects in JavaScript is a very common task, but often times you'll want to define multiple objects that share the same properties and the same basic structure. For example, if I were programming a video game and I wanted to define some players as objects, I might do so like this:</p>


{% highlight javascript linenos %}

  var playerOne = {name: "Mario", coins: 55, lives: 3};

{% endhighlight %}


<p>And then after I defined player one, I want to define player two. Except the problem is that I unintentionally define player two in a slightly inconsistent way:</p>

{% highlight javascript linenos %}
var playerTwo = {name: "Luigi", score: 55, health: 3};
{% endhighlight %}

<p>See what's inconsistent here? The name property is the same in both player objects, but for playerOne's "coins" property, playerTwo has "score" instead!
And the players lives/health is stored inconsistently as well.

What we need is a way to easily formalize our objects, making it easy to create many different objects with the same properties, but with different values for each property.

<h2>Enter the constructor function!</h2>
<p>What's a constructor function? 
It's a function that can construct... Objects! Lots of objects!
The first step is to just make a function like normal with the name of the type of object that we want to construct, in this case Player:
</p>

{% highlight javascript linenos %}
function Player(){
	
};
 {% endhighlight %}

<p>(BTW, The tradition is to always capitalize the first letter for these constructor functions!)

Right now we'll leave the constructor function empty.
Now we'll create our object by declaring a new variable using the keyword "new" to create a new object from the Player constructor function.
</p>


{% highlight javascript linenos %}
function Player(){

};

 var mario = new Player();  

 {% endhighlight %}

 <p>This creates a new object, calling the Player constructor function to create the new object. Obviously there is still nothing inside the constructor function, so let's add some code. Let's try:</p>


{% highlight javascript linenos %}
function Player(){
	this.name = "mario";
};

 var mario = new Player();

 {% endhighlight %}


<p>Wait, that's no good… I want to be able to re-use this constructor function for multiple different players, and all of the players can't be named Mario! We need the constructor function to be able to take in a name parameter. When it is called, it will create a new player, passing in that name parameter for the current object that it is constructing.</p>



{% highlight javascript linenos %}

  function Player(n){
	this.name = n;
};

 var mario = new Player("Mario");

{% endhighlight %}


<p>So now that we have the basic constructor working, we can call it again passing in a new name</p>

{% highlight javascript linenos %}
var luigi = new Player("Luigi");
{% endhighlight %}

<p>This is how we can create many similar objects in a very standardized way.
So let's create some more properties in the constructor function. Let's give each player a number of collected coins, and a number of lives. For the parameters, we'll use the variables "c" and "l" respectively.
</p>

{% highlight javascript linenos %}
function Player(n,c,l){
	this.name = n;
	this.coins = c;
	this.lives = l;
};

 var mario = new Player("Mario",55,3);
 var luigi = new Player("Luigi",76,2);

 {% endhighlight %}



<p>This is a much more efficient way of creating many similar objects, but how to we display the data related to each object? </p>

<h2>Enter prototypes!</h2>

<p>Prototypes can allow us to attach new functions onto individual objects, rather than declaring functions inside of the constructor function, which would affect ALL of the constructor's objects at the same time. In this way, our prototype will just bolt a function onto an individual object. In this case, a function that outputs a console log about a player.
Every JavaScript object has a prototype.
Functions (including our player function) are also objects, and so they have prototypes too. We can use the prototype to get the player object to do things, like tell us the player's name

</p>

{% highlight javascript linenos %}
 Player.prototype.displayName = function(){
	    console.log("It’s a me," , this.name);
};

 {% endhighlight %}

<p>We use the keyword "this" to output the name property of whatever the current object is, because this prototype could be re-used on any player object we want.

The "displayName" part is just something made up, you could use anything that is descriptive of what the prototype is getting the object to do.

Now to have the Mario player output its name, we just type

</p>


{% highlight javascript linenos %}
 mario.displayName(); 

 {% endhighlight %}


<p>And it will log "It's a me, Mario" to the console!
We can do the same for Luigi, too.

</p>


{% highlight javascript linenos %}
function Player(n,c,l){
	this.name = n;
	this.coins = c;
	this.lives = l;
};

 var mario = new Player("Mario",55,3);
 var luigi = new Player("Luigi",76,2);

 Player.prototype.displayName = function(){
	console.log("It's a me," , this.name);
};

 mario.displayName(); //outputs "It's a me, Mario"
 luigi.displayName();  //outputs "It's a me, Luigi"


 {% endhighlight %}

 <p>And we can do more than just displaying information about the players, we can also use prototypes to bolt on new functions that actually change the values of the player objects too. For example, we can give each player a new 1UP like this:</p>


{% highlight javascript linenos %}
function Player(n,c,l){
	this.name = n;
	this.coins = c;
	this.lives = l;
};

 var mario = new Player("Mario",55,3);
 var luigi = new Player("Luigi",76,2);

 Player.prototype.displayName = function(){
	console.log("It's a me," , this.name);
};

Player.prototype.levelUp = function(){
	this.lives++;
	console.log("1UP! I now have" , this.lives +" lives" );
};

mario.displayName(); //outputs "It's a me, Mario"
luigi.displayName(); //outputs "It's a me, Luigi"
mario.levelUp(); //outputs "1UP! I now have 4 lives"
luigi.levelUp(); //outputs "1UP! I now have 3 lives"


 {% endhighlight %}


<p>The efficient thing about this code is that all of the properties are consistent and standardized, and the whole thing is scalable because I can add as many new players as I want without having to repeat any code! Each new player already knows about its properties while still acting independently of each other. 

Everything that each player can do is based on both the constructor function and the prototypes which have bolted new functions onto them after the fact.

Video games can be so informative ;)
</p>
