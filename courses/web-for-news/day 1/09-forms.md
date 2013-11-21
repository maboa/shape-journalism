9. HTML5 Forms
==============

With the advent of HTML5 we've seen an increase of default form elements available to us by the browser. Browser form elements are useful as we delegate the input mechanism to the browser and hence the user's device.

You've probably noticed that various form inputs are different on mobile to desktop.

9.1 Compatibility
-----------------

Unfortunately compatibility is not great as Internet Explorer 9 and below don't support these new elements.

However there are ways we can mitigate this by using Polyfills and other techniques.


9.2 Polyfills
-------------

Now's a good time to talk about Polyfills. Polyfills are bits of code that patch a browser's missing feature. Usually these pieces of code are only needed when required. Here's a list of [HTML5 Cross browser Polyfills](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-browser-Polyfills) Notice those dedicated to 'web forms'.

Libraries like [Modernizr](http://modernizr.com/) allow you to detect missing features easily. As we move forward of course, non-supporting browsers will drop off the radar and we won't need to use polyfills any more.

9.3 Search
----------

The good old search box. If you want a quick way of improving the user experience use:

`````html
<input type="search" name="search">
`````

You'll get an cross in the field that will allow you to clear quickly and on mobile devices with software keyboards a 'search' button will appear.

Note If a browser doesn’t understand type="search", it will default to type="text", this is sometimes known as progressive enhancement, or garceful degradation, depending on your perspective.


9.4 Email, URL and Tel
----------------------

Email and url are other input types that will produce a customised software keyboard, also if you add a 'required' attribute, you should get some automatic validation.

`````html
<input type="email" name="email" required>
<input type="url" name="url" required>
<input type="tel" name="tel" id="tel" required>
`````

9.5 Number and Range
--------------------

Number and Range types are great if you are trying to constrain input to a certain set of numbers.

For example :

`````html
<input type="number" min="5" max="18" step="0.5" value="9" name="shoe-size">
<input id="skill" type="range" min="1" max="100" value="0">
`````

9.6 Dates and Times
-------------------

Try these out:

`````html
<input id="dob" name="dob" type="date">
<input id="startdate" name="startdate" min="2012-01-01" max="2013-01-01" type="date">
<input id="expiry" name="expiry" type="month" required>
<input id="vacation" name="vacation" type="week">
<input id="exit-time" name="exit-time" type="time">
<input id="entry-day-time" name="entry-day-time" type="datetime">
`````

Colour
------

Colour pickers are difficult to get working on all platforms. Help is hand with the color type.

`````html
<input id="color" name="color" type="color">
`````

9.6 Exercise
------------

1. Create a form using all the above new inputs.
2. Try them out on various browsers.


### Further info

[HTML5 forms input types](http://html5doctor.com/html5-forms-input-types/)

[HTML5 forms introduction and new attributes](http://html5doctor.com/html5-forms-introduction-and-new-attributes/)

[Dive into HTML5 - Forms](http://diveintohtml5.info/forms.html)

[The Current State of HTML5 Forms](http://www.wufoo.com/html5/)

---

[<< previous 8. Web Fonts](08-webfonts.md) | [next 10. Semantic Markup >>](10-semantic.md)
