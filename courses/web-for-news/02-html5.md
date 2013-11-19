2. HTML5
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

Lets analyse this a little but not overly.

```<!DOCTYPE html>``` just tells the browser that we are using the latest version of HTML, in the ```<meta>``` tag we define the charset (it is usually utf-8 which represents unicode). You may be able to imagine how the rest of this structure works. Safe to say most of the content will reside between the ```<body>``` tags.



2.1 Canvas
----------

You can think of canvas as a drawing surface for a web-page. If you knew HTML pre-canvas you'll this was difficult to do without using plugins like Flash. Canvas offers a way of writing pixels, lines and shapes to the screen in an intuitive way. You can read and write all the pixels of a particular canvas, you can even apply canvases to other HTML5 elements.

Although Canvas may look vector-based, it is actually rasterised, which means if you zoom in, you'll start to see the pixels.

---

[previous 1. The Web and the Newsroom](01-web-and-the-newsroom.md)
