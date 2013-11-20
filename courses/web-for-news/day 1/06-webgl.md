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
	    gl.clearColor(0.0, 0.0, 0.0, 1.0);                      // Set clear color to black, fully opaque
	    gl.enable(gl.DEPTH_TEST);                               // Enable depth testing
	    gl.depthFunc(gl.LEQUAL);                                // Near things obscure far things
	    gl.clear(gl.COLOR_BUFFER_BIT|gl.DEPTH_BUFFER_BIT);      // Clear the color as well as the depth buffer.
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



There are other ways to represent data in three dimensions which we'll come to later. For now lets look at some examples to get an idea of potential.

[Digital Landscapes](http://www.littleworkshop.fr/landscapes/)

### Further Info

[MDN WebGL](https://developer.mozilla.org/en-US/docs/Web/WebGL)
[HTML5 Rocks](http://www.html5rocks.com/en/tutorials/webgl/webgl_fundamentals/)

