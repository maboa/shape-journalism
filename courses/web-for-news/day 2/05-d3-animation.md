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




