3. D3 Scales
============

Sometimes we don't want to map things to pixels but something more flexible. We want to scale things or create a scale. 

Note : Scales are related to axis but is not actually the axis.

3.1 Domain and Ranges
---------------------

A scale's input domain is the range of possible input data values.

A scale's output range is the range of possible output values.

Example:

`````
          Input domain
100-----------300------------500

10------------180------------350
          Output range
`````

3.2 Creating a Scale
--------------------

We are going to start with linear scales, but you can imagine we can have all sorts of scales.

So let's take a look at creating a scale:

`````javascript
var rScale = d3.scale.linear()
                     .domain([0, d3.max(dataset, function(d) { return d[1]; })])
                     .range([2, 5]);

`````

and let's apply it to our scatterplot

`````javascript
.attr("r", function(d) {
    return rScale(d[1]);
});
`````

So as we can see we are forcing our values to fit between radii of 2 and 5.

3.2 Exercise
------------

1. Apply a scale to your scatterplot example.
2. Add [600, 150] to your data and not what happens.

3.3 Other Methods
-----------------

There are a few helpful methods we can add to ```d3.scale.linear()```.

* [```nice()```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-linear_nice) - This tells the scale to take whatever input domain that you gave to range().
* [```rangeRound()```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-linear_rangeRound) - Use instead of ```range()``` to round the output.
* [```clamp()```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-linear_clamp) - clamps values to within the specified range

3.4 Other Scales
----------------

* [```identity```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-identity) — A 1:1 scale, useful primarily for pixel values
* [```sqrt```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-sqrt) — A square root scale
* [```pow```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-pow) — A power scale (good for the gym)
* [```log```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-log) — A logarithmic scale
* [```quantize```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-quantize) — A linear scale with discrete values for its output range, for when you want to sort data into “buckets”
* [```quantile```](https://github.com/mbostock/d3/wiki/Quantitative-Scales#wiki-quantile) — Similar to above, but with discrete values for its input domain (when you already have “buckets”)
* [```ordinal```](https://github.com/mbostock/d3/wiki/Ordinal-Scales) — Ordinal scales use non-quantitative values (like category names) for output; perfect for comparing apples and oranges

3.5 Exercise
------------

Try out all of these scales and see how they affect your scatterplot.

---
Based on [AlignedLeft Tutorials](http://alignedleft.com/tutorials/d3/)

[<< previous 2. D3 Labels](02-d3-labels.md) | 	[next 4. D3 Axes >>](04-d3-axes.md)