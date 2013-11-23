5. Animation
============

Animation can not only give data visualisations extra pizzazz, but it can also impart added meaning. This is the part of the course where we spend some time looking at how we can make our data visualisations less static. Transitions are a good way of achieving this we've already looked briefly at them. Let's take a further look and introduce the aspects of movement and time.

5.1 First Movement
------------------

Let's try creating something from scratch and then apply what we learn to the scatterplot.

`````javascript
var mySquare = svg.append("rect")
  .attr("x",60)
  .attr("y",60)
  .attr("width",60)
  .attr("height",60);
`````
[try it out](http://jsbin.com/ATUJANE/1/edit)

To animate this - all we need do is invoke a transition.

`````javascript
mySquare
  .transition()
  .attr("x",320);
`````
If you add this to your code you'll see the rectangle move.

Note that there are sensible defaults built into D3 so the value changes over time to produce animation.

5.2 Animating Attributes
------------------------

You can transition or animate virtually any attribute of an element.

5.3 Excercise
-------------

1. Try the following effects.
2. Can you chain them?

`````javascript 

mySquare
  .transition()
  .attr("width",120); // will make it bigger
 
mySquare
  .style("fill","white") // if the fill is originally left blank and comes
                         //  from a style sheet, it will start as black 
  .transition()
  .style("fill","blue");
 
mySquare
  .transition()
  .style("opacity",0);

`````

5.4 Timing
----------

If it was all a bit quick for you, that's because D3 chooses 250ms as a default time to transition.

Let's take control of the timing.

There are essentially to variables we can change:

* ```duration``` - how long it takes in milliseconds for the transition to take place
* ```delay``` - the time in milliseconds before the transition takes place

Try altering your code to incorporate these new methods:

`````javascript
mySquare.transition()
  .attr("x",320)
  .duration(1000) // this is 1s
  .delay(100)     // this is 0.1s
`````

You have may have tried to include more than one ```transition()``` in the previous example, in an attempt to play the transitions simultaneously, however things occur in parallel so to set off events one after the other you will need to pay careful attention to timings.

5.5 Exersise
------------

1. Change the duration to half a second.
2. Play the effects one after the other.

5.6 Easing
----------

So far we have animated things in a certain way, you may have noticed that theing start moving slowly, speed up and then slow down at the end. This is another of D3's defaults. However, there are many different equations we can use and we apply the using the ```ease``` method.

Here's a list of easin equations we can use with D3:

* cubic-in-out (default)
* elastic
* linear
....

5.7 Sequences
-------------

Earlier we looked at events occurring in parallel and found a simple but crude work-around. There are actually more flexible ways of achieving the same result.

So let's move our humble rectangle in two different directions, one after the other:

`````javascript
mysquare
  .transition()
  .attr("x",320)
  .each("end",function() { // as seen above
    d3.select(this).       // this is the object 
      transition()         // a new transition!
        .attr("y",180);    // we could have had another
                           // .each("end" construct here.
   });
`````

What we are doing here is introducing the concept of events. When one transition has ended it fires the 'end' event and we can react to this.

In many ways this is a better way to control sequential animation, because if we change one of the timings we don't have to go through and adjust all the other timings. Although you could assign variables to each timing at which point you'd have a more flexible system.

5.8 Exercise
------------

Use the end event to make your animation sequential.

5.9 Remove
----------

A quick note about making things more efficient. If you no longer need an element (for example when its opacity has become zero never to return), you can remove it.

Here's an example:

`````javascript
mysquare
  .transition()
  .attr("x",320)
  .each("end",function() { 
    d3.select(this).       // so far, as above
      remove();            // we delete the object instead 
   });
`````

5.10 Exercise
-------------

Remove the object at the end.

---
Based on [Creating Animations and Transitions With D3](http://blog.visual.ly/creating-animations-and-transitions-with-d3-js/)

[<< previous 4. D3 Axes](04-d3-axes.md) | [next 6. D3 Interaction >>](06-d3-interaction.md)










