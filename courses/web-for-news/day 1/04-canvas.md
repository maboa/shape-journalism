4. Canvas
=========

You can think of canvas as a drawing surface for a web-page. If you knew HTML pre-canvas you'll this was difficult to do without using plugins like Flash. Canvas offers a way of writing pixels, lines and shapes to the screen in an intuitive way. You can read and write all the pixels of a particular canvas, you can even apply canvases to other HTML5 elements.

Although Canvas may look vector-based, it is actually rasterised, which means if you zoom in, you'll start to see the pixels.

Ok the best way to get an idea of a technology is to play with it, so let's dabble with Canvas.

Somewhere inside your ```<body>``` you'd write something like this:

`````html
<canvas id="chart" width="150" height="150"></canvas>
`````

This will effectively reserve a space for your canvas in pixels. You'll notice that we give the element an id, this is so we can reference it from JavaScript or CSS.

###Fallback

For many HTML elements there is a way of displaying content should the tag not be supported. The good news is it is really straightforward. Place text or images between the tag and this will only display if the tag isn't recognised by the browser.

For example:

`````html
<canvas id="chart" width="150" height="150">
  <img src="images/chart.png" width="150" height="150" alt=""/>
</canvas>
`````

4.1 A bit of JavaScript
-----------------------

This course is intended to be practical and followed sequentially, so it's at this juncture (when we need it) that we start to touch on JavaScript.

So here goes:

`````javascript
var canvas = document.getElementById('chart');
var ctx = canvas.getContext('2d');
`````

Here two very separate things are going on. First we grabbing a hook into our canvas object via it's id and then we are obtaining what's known as a context. Notcie the '2d' parameter - we are working in two dimensions for now.


4.2 Putting the Pieces Together
-------------------------------

`````html
<!DOCTYPE html>
<html>
<head>
    <meta charset=utf-8 />
    <title>Canvas tutorial</title>
    <script>

    function draw() {
      var canvas = document.getElementById("canvas");
      if (canvas.getContext) {
        var ctx = canvas.getContext("2d");

        ctx.fillStyle = "rgb(200,0,0)";
        ctx.fillRect (10, 10, 55, 50);

        ctx.fillStyle = "rgba(0, 0, 200, 0.5)";
        ctx.fillRect (30, 30, 55, 50);
      }
    }

    window.onload = draw;

    </script>
 </head>
 <body>
   <canvas id="canvas" width="150" height="150"></canvas>
 </body>
</html>
`````

[See it working](http://jsbin.com/iwIleWi/1/edit)

4.3 Exercise
------------
Create a canvas chart with an image fallback.

Note: the origin (0,0) of a Canvas is in the top left corner.

### Further Info

[Canvas on MDN](https://developer.mozilla.org/en/docs/HTML/Canvas)

---

[<< previous 3. HTML5 Getting Started](03-html5-getting-started.md) | [next 5. SVG >>](05-svg.md)