6. Interaction
==============

So far we've looked at how we can represent things passively on the screen.

Next we're going to look at interaction.

Consider the following code:

`````javascript
//Width and height
var w = 1000;
var h = 500;
			
//Create SVG element
var svg = d3.select("body")
  .append("svg")
  .attr("width", w)
  .attr("height", h);
      
  var myCircle = svg.append("circle")
    .attr("cx",500 )
    .attr("cy",250 )
    .attr("r", 50)
    .attr("fill","orange");

`````
Remember how we applied styles in the previous exercise? We added extra class attributes.

`````javascript
.attr("class","circ")
`````
Once we have done this we have a handle on our objects. We can then react to events like so:

`````javascript
  d3.select(".circ").on("click", function() {
    myCircle
      .transition()
      .attr("r",100);
  });

  d3.select(".circ").on("mouseover", function() {
    myCircle
      .transition()
      .attr("fill","yellow");
  });

  d3.select(".circ").on("mouseout", function() {
    myCircle
      .transition()
      .attr("fill","orange");
  });
  `````


