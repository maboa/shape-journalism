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

`````xml
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

SVG can be a little bit 'old school' when it comes to things like xmlns - (XML namespacing) and that's why we have defined it here. The latest version is 1.1 so we define that and baseProfile specifies the minimum language SVG language profile you need to correctly render content, but this is just meta-data. You can leave this as full or miss it out. So these three lines are extra default stuff that in theory we should put into our code to ensure maximum compatibility. In practice you may need it for some older browsers but in the interest in keeping our code clean we're going to omit these parts in future.

For more info check out the [W3C spec](http://www.w3.org/TR/SVG/struct.html)

The rest is more dynamic, and is actually pretty self-explanatory. (Rect stands for rectangle). All co-ordinates are defined in pixels and are relative to the top left of the defined area (like Canvas). Text-anchor is a property that defines where the midpoint of it should be (in this case 150,125).

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

`````xml
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

5.4 Polygons, Lines, Polyline and Paths
---------------------------------------

Here's an example using all these elements:

`````xml
<svg width="200" height="250">
  <line x1="10" x2="50" y1="110" y2="150" stroke="orange" fill="transparent" stroke-width="5"/>
  <polyline points="60 110 65 120 70 115 75 130 80 125 85 140 90 135 95 150 100 145"
      stroke="orange" fill="transparent" stroke-width="5"/>

  <polygon points="50 160 55 180 70 180 60 190 65 205 50 195 35 205 40 190 30 180 45 180"
      stroke="green" fill="transparent" stroke-width="5"/>

  <path d="M20,230 Q40,205 50,230 T90,230" fill="none" stroke="blue" stroke-width="5"/>

</svg>
`````
[see it working](http://jsbin.com/oJIcASu/3/edit)

###Polyline and Polygons

You define a series of points as x y, x y, x y. With a Polygon the difference is it joins the last point to the first.

###Paths

*M - Move to (Mx y)
*L - Line to (L x y)
*H - Horizontal Line (eg H 10)
*V - Vertical Line (eg V 10)
*Z - Close Path (eg Z)

Note : Use lower case to denote relative distance rather than absolute.

###Curves

SVG allows you to define [Bézier curves](http://en.wikipedia.org/wiki/B%C3%A9zier_curve)

*C - Cubic Bezier (C x1 y1, x2 y2, x y (or c dx1 dy1, dx2 dy2, dx dy))
*S - Shorthand Cubic Bezier (S x2 y2, x y (or s dx2 dy2, dx dy) - only two - coordinates required as first is reflected)
*Q - Quadratic Bezier (Q x1 y1, x y (or q dx1 dy1, dx dy))
*T - Shorthand Quadratic Bezier (T x y (or t dx dy))

Try this :

`````xml
<svg width="190px" height="160px" version="1.1" xmlns="http://www.w3.org/2000/svg">
  <path d="M10 80 C 40 10, 65 10, 95 80 S 150 150, 180 80" stroke="black" fill="transparent"/>
</svg>
`````

![the second control point is a reflection of the last](https://developer.mozilla.org/@api/deki/files/363/=ShortCut_Cubic_Bezier.png)

###Arcs

*A rx ry x-axis-rotation large-arc-flag sweep-flag x y
*a rx ry x-axis-rotation large-arc-flag sweep-flag dx dy

The sweep-flag makes this very powerful.

Try this out:

`````xml

<svg width="325px" height="325px">
  <path d="M80 80
           A 45 45, 0, 0, 0, 125 125
           L 125 80 Z" fill="green"/>
  <path d="M230 80
           A 45 45, 0, 1, 0, 275 125
           L 275 80 Z" fill="red"/>
  <path d="M80 230
           A 45 45, 0, 0, 1, 125 275
           L 125 230 Z" fill="purple"/>
  <path d="M230 230
           A 45 45, 0, 1, 1, 275 275
           L 275 230 Z" fill="blue"/>
</svg>
`````

[see it working](http://jsbin.com/UtUcalov/1/)


5.4 Exporting SVG
-----------------

SVG is capable of rendering very complex forms and this can be useful for creating visually complex pieces. The following popular applications support SVG:

* Adobe Illustrator (Can import from Photoshop)
* Adobe Fireworks ([SVG for web plugin](https://github.com/joshje/svg-for-web))
* [Sketch](http://www.bohemiancoding.com/sketch/) 
* [Inkscape](http://inkscape.org/) 

Note Illustrator adds a lot of unnecessary code to the file.

You can also grab SVG from pages using [SVG Crowbar](http://nytimes.github.io/svg-crowbar/) from the New York Times.

5.5 Exercise
------------

1. Create a file with one of the above graphics packages and export as SVG.
2. Open the file and inspect it.
3. Open in a browser and use your web development tools to inspect it and adjust the values.

5.6 Reducing File Size
----------------------

As you've probably noticed some files become unnecessarily large. You can use the following tools to reduce their size:

* [svgo](https://github.com/svg/svgo) (Node Plugin)
* [svgo-gui](https://github.com/svg/svgo-gui)
* [grunt-svgmin](https://github.com/sindresorhus/grunt-svgmin) (uses svgo)

You can also zip up SVG files and give them the extension .svgz

5.7 Exercise
------------

1. Take your exported SVG from exercise 5.5 and reduce it's size.
2. Place them side by side in a web-page and compare visually.
3. Compare the file size.

As we can change values dynamically you can imagine that animation is possible. There's a lot more to SVG but hopefully this has given you an idea. 


###Further Info
[SVG Primer (published by the W3C)](http://www.w3.org/Graphics/SVG/IG/resources/svgprimer.html#SVG_in_HTML)
[Learning how to write SVGs](http://everydaydesigner.net/design/get-started-with-scalable-vector-graphics)
[SVG Filters (W3C)](http://www.w3.org/TR/SVG/filters.html)
