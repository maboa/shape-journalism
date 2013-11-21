6. WebGL
========

WebGL builds upon Canvas to provide advanced graphics processing by taking advantage of GPU (Graphics Processing Unit) to perform accelerated instruction execution. In other words it allows us to carry out an enormous amount of operations at high speed, this makes WebGL and ideal technology for 3D graphics manipulation as well as intensive 2D effects.

On this course we're going to look at the capabilities of WebGL but not the details of implementation. Although potentially WebGL could be used to create a new breed of interactives, it is a low-level technology which is more suited to writing games or creating artistic pieces than for data visualisation. Instead we'll look at the fundamental concepts.

6.1 WebGL Setting the Scene
---------------------------

WebGL is based on OpenGL - a native Graphics Library used for many a PC game. 

The first thing we need to do is set up our canvas:

`````html
  <canvas id="glcanvas" width="640" height="480">
    Your browser doesn't appear to support canvas.
  </canvas>
`````
Next we create a context.

`````javascript

window.onload = function {
	var gl; // A global variable for the WebGL context

	function start() {
	  var canvas = document.getElementById("glcanvas");

	  gl = initWebGL(canvas);      // Initialize the GL context
	  
	  // Only continue if WebGL is available and working
	  
	  if (gl) {
	    gl.clearColor(0.0, 0.0, 0.0, 1.0);                 // Set clear color to black, fully opaque
	    gl.enable(gl.DEPTH_TEST);                          // Enable depth testing
	    gl.depthFunc(gl.LEQUAL);                           // Near things obscure far things
	    gl.clear(gl.COLOR_BUFFER_BIT|gl.DEPTH_BUFFER_BIT); // Clear the color as well as the depth buffer.
	  }
	}	
}

`````

Then we intialise our WebGL context 

`````javascript
function initWebGL(canvas) {
  gl = null;
  
  try {
    // Try to grab the standard context. If it fails, fallback to experimental.
    gl = canvas.getContext("webgl") || canvas.getContext("experimental-webgl");
  }
  catch(e) {}
  
  // If we don't have a GL context, give up now
  if (!gl) {
    alert("Unable to initialize WebGL. Your browser may not support it.");
    gl = null;
  }
  
  return gl;
}
`````
and finally we resize the viewport to be the size of our canvas

`````javascript
gl.viewport(0, 0, canvas.width, canvas.height);
`````
Now that's the context set and we're ready to draw something.

Shaders
-------

There are two main things that WebGL cares about, clipspace co-ordinates and colours. Clipspace defines the area within which the parts of the shapes will be drawn. To do this we have two 'shaders':

1. Vertex Shader - to calculate clipspace coordinates*
2. Fragment Shader - to calculate the colour of a given pixel

*clipspace co-ordinates range from -1 to +1.

This are what shaders look like:

`````html
<script id="2d-vertex-shader" type="x-shader/x-vertex">
attribute vec2 a_position;

void main() {
  gl_Position = vec4(a_position, 0, 1);
}
</script>

<script id="2d-fragment-shader" type="x-shader/x-fragment">
void main() {
  gl_FragColor = vec4(0,1,0,1);  // green
}
</script>
`````
We're looking at these to get an idea how low-level WebGL is. This isn't JavaScript it's GLSL - a specific shading language.

Working with WebGL
------------------

As you can see there is a significant amount of investment required to learn WebGL, but the good news is that there are tools available to make things easier for you.

* [Blender](http://www.blender.org/)
* [CopperCube](http://www.ambiera.com/coppercube/)
* [AutoDesk Maya](http://www.autodesk.com/products/autodesk-maya/overview)

There's also a powerful JavaScript library called [http://threejs.org/](Three.js) that makes using WebGL a lot easier for developers. We'll look at that later.

There are other ways to represent data in three dimensions which we'll come to later. For now lets look at some examples to get an idea of potential.

[CopperCube Demo](http://www.ambiera.com/coppercube/demo.php?demo=backyard&mode=webgl)
[Google Zeitgeist](http://www.google.com/zeitgeist/2012/#explore)
[360gigapixels](http://360gigapixels.com/tokyo-tower-panorama-photo/?v=-166.3,-0.6,1)
[Digital Landscapes](http://www.littleworkshop.fr/landscapes/)

### Further Info

[MDN WebGL](https://developer.mozilla.org/en-US/docs/Web/WebGL)
[HTML5 Rocks](http://www.html5rocks.com/en/tutorials/webgl/webgl_fundamentals/)
[Wikipedia](http://en.wikipedia.org/wiki/WebGL)

---

[<< previous 5. SVG](05-svg.md) | [next 7. CSS >>](07-css.md)