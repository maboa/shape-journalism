2. Labels
=========

It's often not enough just to draw pretty pictures we usually need to label them.

2.1 One Dimensional
-------------------

`````html

<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="utf-8">
		<title>D3 Demo: Making a bar chart with value labels!</title>
		<script src='http://d3js.org/d3.v2.min.js'></script>
		<style type="text/css">
			/* No style rules here yet */		
		</style>
	</head>
	<body>
		<script type="text/javascript">

			//Width and height
			var w = 500;
			var h = 100;
			var barPadding = 1;
			
			var dataset = [ 5, 10, 13, 19, 21, 25, 22, 18, 15, 13,
							11, 12, 15, 20, 18, 17, 16, 18, 23, 25 ];
			
			//Create SVG element
			var svg = d3.select("body")
						.append("svg")
						.attr("width", w)
						.attr("height", h);

			svg.selectAll("rect")
			   .data(dataset)
			   .enter()
			   .append("rect")
			   .attr("x", function(d, i) {
			   		return i * (w / dataset.length);
			   })
			   .attr("y", function(d) {
			   		return h - (d * 4);
			   })
			   .attr("width", w / dataset.length - barPadding)
			   .attr("height", function(d) {
			   		return d * 4;
			   })
			   .attr("fill", function(d) {
					return "rgb(0, 0, " + (d * 10) + ")";
			   });

			svg.selectAll("text")
			   .data(dataset)
			   .enter()
			   .append("text")
			   .text(function(d) {
			   		return d;
			   })
			   .attr("text-anchor", "middle")
			   .attr("x", function(d, i) {
			   		return i * (w / dataset.length) + (w / dataset.length - barPadding) / 2;
			   })
			   .attr("y", function(d) {
			   		return h - (d * 4) + 14;
			   })
			   .attr("font-family", "sans-serif")
			   .attr("font-size", "11px")
			   .attr("fill", "white");

		</script>
	</body>
</html>

`````

Note that the origin of an SVG context is the top,left and that is why we have to subtract the height when we plot the y dimension.

2.2 Two Dimensional
-------------------

So that's how we can label a bar chart, let's see how we can label a scatterplot.


`````html

<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="utf-8">
		<title>D3 Demo: Making a scatterplot with SVG</title>
		<script type="text/javascript" src="http://d3js.org/d3.v2.min.js"></script>
		<style type="text/css">
			/* No style rules here yet */		
		</style>
	</head>
	<body>
		<script type="text/javascript">

			//Width and height
			var w = 500;
			var h = 100;
			
			var dataset = [
							[5, 20], [480, 90], [250, 50], [100, 33], [330, 95],
							[410, 12], [475, 44], [25, 67], [85, 21], [220, 88]
						  ];
	
			//Create SVG element
			var svg = d3.select("body")
						.append("svg")
						.attr("width", w)
						.attr("height", h);

			svg.selectAll("circle")
			   .data(dataset)
			   .enter()
			   .append("circle")
			   .attr("cx", function(d) {
			   		return d[0];
			   })
			   .attr("cy", function(d) {
			   		return d[1];
			   })
			   .attr("r", function(d) {
			   		return Math.sqrt(h - d[1]);
			   });

			svg.selectAll("text")
			   .data(dataset)
			   .enter()
			   .append("text")
			   .text(function(d) {
			   		return d[0] + "," + d[1];
			   })
			   .attr("x", function(d) {
			   		return d[0];
			   })
			   .attr("y", function(d) {
			   		return d[1];
			   })
			   .attr("font-family", "sans-serif")
			   .attr("font-size", "11px")
			   .attr("fill", "red");
			
		</script>
	</body>
</html>
`````
All we do is alter the Y dimension.

---
Based on [AlignedLeft Tutorials](http://alignedleft.com/tutorials/d3/)

[<< previous 1. Introduction to D3.js ](01-d3-intro.md) | 	[next 3. D3 Scales >>](03-d3-scales.md)
