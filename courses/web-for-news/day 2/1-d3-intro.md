1. Introduction to D3.js 
========================

D3.js (Data Driven Documents) was created by Mike Bostock at the New York Times to help him creat more interactive visualisations using web technologies.

D3 takes advantages of base technologies we've already explored a little - namely JavaScript, HTML, CSS3, Canvas and SVG.

As you can probably tell by it's name D3 is heavily data oriented. It's aim is to make it easier for us to visualise data on the web, whether that is through HTML tables or SVG.

D3 is fast and flexible and provides several helper methods for dealing with the DOM.

The best way to learn is to get stuck in, so lets look at simple example:

1.1 Hello World
---------------

Let's look at one of the simplest possible examples we can create with D3:

`````html
<!DOCTYPE html>
<html>
<head>
<title>D3 Test</title>
 <script src='http://d3js.org/d3.v2.min.js'></script>
</head>
<body>
  <script type="text/javascript">
    d3.select("body").append("p").text("New paragraph!");
  </script>
</body>
</html>
`````
Here we see that D3 provides a convenient way to select elements and append other elements to it.

[http://jsbin.com/inuher/1/edit](http://jsbin.com/inuher/1/edit)


1.2 First Contact with Data
---------------------------

`````html
<!DOCTYPE html>
<html>
<head>
<title>D3 Test</title>
 <script src='http://d3js.org/d3.v2.min.js'></script>
</head>
<body>
  <script type="text/javascript">
    var dataset = [ 5, 10, 15, 20, 25 ];
    d3.select("body").selectAll("p")
    .data(dataset)
    .enter()
    .append("p")
    .text("New paragraph!");
  </script>
</body>
</html>
`````

[http://jsbin.com/inuher/4/edit](http://jsbin.com/inuher/4/edit)

The main bit to notice here is the ```enter()``` this checks the DOM and if not enough elements exist for the data, it creates the appropriate amount.

If you try this you'll see we still haven't displayed any data.

So let's do something with tha data:

`````html
<!DOCTYPE html>
<html>
<head>
<title>D3 Test</title>
 <script src='http://d3js.org/d3.v2.min.js'></script>
</head>
<body>
  <script type="text/javascript">
    var dataset = [ 5, 10, 15, 20, 25 ];
    d3.select("body").selectAll("p")
    .data(dataset)
    .enter()
    .append("p")
    .text(function(d) { return d; })
    .style("color", function(d) {
      if (d > 15) {   //Threshold of 15
          return "red";
      } else {
          return "black";
      }
    });
  </script>
</body>
</html>
`````
If you try this you'll see that we're passing each piece of data through as d. That variable can be called anything, it will always get populated with each piece of data. This leaves you free to do all sorts of things. Here we are manipulating the colour which is a style attribute. 

Inspect the source to see what actually happened.

1.3 Our First Bar Chart
-----------------------

`````html
<html lang="en">
	<head>
		<meta charset="utf-8">
		<title>D3 Demo: 5-div bar chart</title>
 		<script src='http://d3js.org/d3.v2.min.js'></script>
		<style type="text/css">
		
			div.bar {
				display: inline-block;
				width: 20px;
				height: 75px;	/* Gets overriden by D3-assigned height below */
				margin-right: 2px;
				background-color: teal;
			}
		
		</style>
	</head>
	<body>
		<script type="text/javascript">
		
			var dataset = [ 5, 10, 15, 20, 25 ];
			
			d3.select("body").selectAll("div")
				.data(dataset)
				.enter()
				.append("div")
				.attr("class", "bar")
				.style("height", function(d) {
					var barHeight = d * 5;
					return barHeight + "px";
				});
			
		</script>
	</body>
</html>
`````

Makes sense right? 

The only part that may confuse, if you haven't used a lot of CSS, is the inline-block - here's [an explanation](http://dustwell.com/div-span-inline-block.html) if you need it.

1.4 Our First SVG Example
-------------------------

`````html
<!DOCTYPE html>
<html>
  <head>
	<title>D3 Demo: Scatterplot</title>
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
       .attr("r", 5);
			
	</script>
  </body>
</html>
`````

Above we're using SVG to create circles and alter their positions, but we can take things further.

`````html
<!DOCTYPE html>
<html>
  <head>
	<title>D3 Demo: Scatterplot</title>
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
			
	</script>
  </body>
</html>
`````
We've changed the radius of the circle depending on the height.

Exercise 1.5
------------

Here's a data set :

`````javascript
	  var dataset = [
                [5, 20, 0], [480, 90, 1], [250, 50, 0], [100, 33, 0], [330, 95, 0],
                [410, 12, 0], [475, 44, 1], [25, 67, 1], [85, 21, 0], [220, 88, 1]
              ];
`````
Alter the colour of the circle depending on third entry in each array (0,1).

---

Based on [AlignedLeft Tutorials](http://alignedleft.com/tutorials/d3/)

[next 2. Further D3 >>](02-further.md)
