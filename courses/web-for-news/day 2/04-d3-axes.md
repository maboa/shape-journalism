4. Axes
=======

Axes are similar to scales but they don't return values, but visual axis.

First you set up an aix like so :

`````javascript
var xAxis = d3.svg.axis()
                  .scale(xScale)
                  .orient("bottom");
`````

Then you have to call the axis - let's do this at the end:

`````javascript
svg.append("g")
    .call(xAxis);
`````
The g is our reference for the next link in the chain.

Actually, we can chain this all together like so:

`````javascript
svg.append("g")
    .call(d3.svg.axis()
                .scale(xScale)
                .orient("bottom"));
`````
4.1 Exercise
------------

Add this axis to your scatterplot. How does it look?

4.2 Cleaning Up
---------------

As you can probably see the axis doesn't look that great. Time for a bit of CSS cleanup.

First let's give it a class:

`````javascript
svg.append("g")
    .attr("class", "axis")  //Assign "axis" class
    .call(xAxis);
`````

Then we reference it with some CSS:

`````css
.axis path,
.axis line {
    fill: none;
    stroke: black;
    shape-rendering: crispEdges;
}

.axis text {
    font-family: sans-serif;
    font-size: 11px;
}
`````
The [shape-rendering property](https://developer.mozilla.org/en/SVG/Attribute/shape-rendering) is an SVG attribute, that lines things up so we don't have blurry lines.

4.3 Exercise
------------

Add the CSS styling.


4.4 Lining Things Up
--------------------

Ok that's better, but we can push the whole thing down, to better line up.

`````javascript
svg.append("g")
    .attr("class", "axis")
    .attr("transform", "translate(0," + (h - padding) + ")")
    .call(xAxis);
`````
We use the ```translate``` transform.

[This is what you should have now](http://jsbin.com/aYElOmaQ/1/edit)

4.4 Ticks
---------

Ticks on the axes will appear auttomatically using the scale as reference, if you want more control you can define these implicitly.

You can suggest number of ticks like this:

`````javascript
var xAxis = d3.svg.axis()
                  .scale(xScale)
                  .orient("bottom")
                  .ticks(5);  //Set rough # of ticks
`````
Note D3 takes this as a suggestion but tidies things up for you, which in theory makes things scaleable.

4.5 Vertcial Axis
-----------------

First near the top of our code we add:

`````javascript
//Define Y axis
var yAxis = d3.svg.axis()
                  .scale(yScale)
                  .orient("left")
                  .ticks(5);
`````
and near the bottom:

`````javascript
//Create Y axis
svg.append("g")
    .attr("class", "axis")
    .attr("transform", "translate(" + padding + ",0)")
    .call(yAxis);
`````

Excercise 4.6
-------------

Add the Y axis. You may have to increase the padding (try 30).

[Solution here](http://jsbin.com/uWuZuDu/1/edit)

4.7 Stress Testing
------------------

A nice way of testing is to use random numbers.

`````javascript
//Dynamic, random dataset
var dataset = [];
var numDataPoints = 50;
var xRange = Math.random() * 1000;
var yRange = Math.random() * 1000;
for (var i = 0; i < numDataPoints; i++) {
    var newNumber1 = Math.round(Math.random() * xRange);
    var newNumber2 = Math.round(Math.random() * yRange);
    dataset.push([newNumber1, newNumber2]);
}
`````
Excersise 4.8
-------------

1. Add stress testing
2. Comment out the red numbers

[Solution](http://jsbin.com/ARAQAbE/1/edit)

4.8 A note about Formatting
---------------------------

There is something called [```tickFormat()```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-linear_tickFormat) which allows to format your labels.

For example:

`````javascript
var formatAsPercentage = d3.format(".1%");
`````
then
`````javascript
xAxis.tickFormat(formatAsPercentage);
`````

---
Based on [AlignedLeft Tutorials](http://alignedleft.com/tutorials/d3/)

[<< previous 3. D3 Scales](03-d3-scales.md) 