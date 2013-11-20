5. SVG
======

SVG (Scaleable Vector Graphics) actually substantially pre-dates HTML5 and is a separate specification. At first glance the output of SVG may look like Canvas but it is a very different beast.

SVG is not pixel based, rather it is vector based and hence scaleable. (You can zoom in as much as you like without seeing the pixels). Another difference is that is XML based and like HTML has its own Document Object Model (DOM). Because it has a DOM it means we can listen to events on certain elements, this means SVG is so much more powerful than Canvas, in that we can easily react to users clicking on elements!

You can also export to SVG from various packages such as Adobe Illustrator and Inkscape.

5.1 The DOM
-----------

This is a good time to go over what the DOM actually is. Essentially the DOM is a group of relationships between elements on the page. We can 'traverse' these elements by using relationships such as:

*parent
*child
*sibling

Unfortunately the way that the DOM is structured makes this a little clunky. Get out you Web Developer tools and click on any element in a web page to find out why (or use console.dir).

5.2 The SVG Way
---------------

Note: As SVG is based on XML it is a little stricter than HTML, there used to be a version of HTML called XHTML but that's another story!

`````svg
<svg version="1.1"
     baseProfile="full"
     width="300" height="200"
     xmlns="http://www.w3.org/2000/svg">

  <rect width="100%" height="100%" fill="red" />

  <circle cx="150" cy="100" r="80" fill="green" />

  <text x="150" y="125" font-size="60" text-anchor="middle" fill="white">SVG</text>

</svg>
`````
[See it working](http://jsbin.com/aYUQiFel/1/edit)

SVG can be a little bit 'old school' when it comes to things like xmlns - (XML namespacing) and that's why we have defined it here. The latest version is 1.1 so we define that and baseProfile specifies the minimum language SVG language profile you need to correctly render content. Leave this as full, always. So these three lines are what developers call 'boilerplate' - extra default stuff we need to put into our code to get it to work.

The rest is more dynamic, and is actually pretty self-explnatory. (Rect stands for rectangle). All co-ordinates are defined in pixels and are relative to the top left of the defined area (like Canvas). Text-anchor is a property that defines where the midpoint of it should be (in this case 150,125).

Note also that the order in which you define the elements, is the order in which they are drawn.

Colours can be defined using a [their names](http://en.wikipedia.org/wiki/Web_colors) but is recommended you use hexidecmal format (#rrggbb) or RGB (rgb(r,g,b)).

With SVG you things differently to how you normally would with HTML and CSS, for example to create a red rectangle with a blue border, you might create a div and give it the following CSS:

`````css
width:300px;
height:200px;
border:1px solid #0000ff;
background-color:#ff0000;
`````
in SVG it would look more like:

`````svg
<rect x="0" y="0" width="300" height="200" fill="#ff0000" stroke="#0000ff" stroke-width="1" />
`````

5.3 Embedding SVG
-----------------

There are three key ways in which we can insert SVG files into our page.

Using Object:

`````html
<object data="image.svg" type="image/svg+xml" />
`````

Using iFrame:

`````html
<iframe src="image.svg"></iframe>
`````

Using an image tag:

`````html
<img src="image.svg">
`````
Note - will not work in IE < 9 and Firefox < 3.5

The recommended way you should do this:

`````html
<object data="image.svg" type="image/svg+xml">
  <img src="yourfallback.jpg" />
</object>
`````
That way you can easily build in a fallback.



###Further Info
[SVG Primer (published by the W3C)](http://www.w3.org/Graphics/SVG/IG/resources/svgprimer.html#SVG_in_HTML)
[Learning how to write SVGs](http://everydaydesigner.net/design/get-started-with-scalable-vector-graphics)
