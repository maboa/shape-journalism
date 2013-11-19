3. HTML5
========

HTML5 has become shorthand for HTML5, related new web technologies and JavaScript APIs. For short, HTML5 and friends. We're going to break each of these pieces down a bit so that we get a good overview of what is possible.

Defining an HTML5 document. We're going to be using a collaborative coding environment called [JS Bin](http://jsbin.com/) on this course, so click on that link now and lets take a look at what a skeleton HTML5 web-page looks like.

`````html
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8 />
<title>JS Bin</title>
</head>
<body>
  
</body>
</html>
`````

<a class="jsbin-embed" href="http://jsbin.com/uSoyAGUw/1/embed?html">JS Bin</a><script src="http://static.jsbin.com/js/embed.js"></script>

Lets analyse this a little, but not overly.

```<!DOCTYPE html>``` just tells the browser that we are using the latest version of HTML, in the ```<meta>``` tag we define the charset (it is usually utf-8 which represents unicode). You may be able to imagine how the rest of this structure works. Safe to say most of the content will reside between the ```<body>``` tags.



3.1 Canvas
----------

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

2.2 A bit of JavaScript
-----------------------

This course is intended to be practical and followed sequentially, so it's at this juncture (when we need it) that we start to touch on JavaScript.

So here goes:

`````javascript
var canvas = document.getElementById('chart');
var ctx = canvas.getContext('2d');
`````

Here two very separate things are going on.

---

[previous 2. Tools of the Trade](02-tools-of-the-trade.md)
