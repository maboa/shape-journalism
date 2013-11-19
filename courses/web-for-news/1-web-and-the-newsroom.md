1. The Web and the Newsroom
===========================

World wide web started as interconnected platform for documents. Slowly richer content became available, mainly through plugins such as Adobe's Flash.

Flash is no longer supported on many platforms. What can we use instead?

HTML, JavaScript and CSS
------------------------

There are many technologies that are built into browsers. Browsers generally adhere to standards. Standards that are established by the World Wide Web Consortium (W3C).

This means that you can write applications once and run them on a number of platforms. Perfect for journalistic application.

Web based content is created with three principal technologies:

### HTML

HTML (HyperText Markup Language) allows developers to define the structure of the page or application using what's known as markup. Over the last few years a new standard has emerged known as HTML5. HTML5 provides extra elements that greatly enhance capabilities of web based content and makes it more accessible and in some ways simpler than previous versions.

### JavaScript

JavaScript (is unrelated to Java aside from syntax) is a language that can be used to manipulate web content. It is the lingua franca of the web and all browsers. Those of you that have used ActionScript will already be familiar with many of the features of JavaScript (They are both based on the ECMAScript language standard).

JavaScript is an interpreted language and it was written in a hurry and so has good parts and bad parts. Overall though it is a very powerful language and has been proven to be extremely flexible. It's even being run on servers now.

Current efforts are being made to make the language even better (ES6/ES7), introducing new syntax for complex applications.

### CSS

CSS (Cascading Style Sheets) is a language used to define the presentation of various markup, such as HTML. CSS can be used to define anything from colours to positioning and in the latest version CSS3, you can even create animations and more complex interactions.


Between these three technologies we can build almost anything we can imagine for the web. 


Basic Concepts of the Web
-------------------------

The web as a platform is very popular and always increasing in popularity despite competition from things like native apps.

There are many reasons the web is a winning platform:

1. It's cross platform - it works almost anywhere
2. You can view the source - people can easily learn from example
3. You do not need specialised tools to get going - notepad will do
4. It's an open standard and so not dominated by commercial pressure
5. It has a very strong community
6. Browser functionality does a lot of the work for you
7. Accessibility is built in
8. It's easy to debug - the tools come with browsers
9. Security comes as standard
10. It's not that complicated - anyone can learn it



The Web Landscape
-----------------

When writing for the web platform, or many different platforms, it's important to have an idea of what your users are using and what their connection speed is.

### Mobile

Mobile web traffic will overtake desktop in 2014 or 2015. [Some recent stats](http://www.insidemobileapps.com/wp-content/uploads/2013/07/mobile_visits.jpg)

### Browsers

It is best to get stats from the domains you are working on, but to give you an idea of how things stand right now you can visit sites like [StatCounter](http://gs.statcounter.com/#browser_version_partially_combined-ww-monthly-201210-201310-bar). 

### Connection Speeds

Another variable that can effect your user's experience is connection speeds and these may vary greatly. One good report to study to get a feel of what's going on is [Akamai's regular report](http://www.akamai.com/dl/documents/akamai_soti_q213.pdf?WT.mc_id=soti_Q213)

As a general rule of thumb we try and make web sites and applications as efficient as possible!



The Semantic Web
----------------

You may think that the web pages you create are to be consumed by people but HTML is also designed to be read (and understood) by machines. The idea is that by using certain tags automated agents can make sense of the content of web pages, this promotes interoperability. 


Responsive Web Design
---------------------

Responsive Web Design (RWD) is the practice of designing web sites and applications to work on various platforms using one client-side code base. It can be difficult to master and can provide sub-optimal experiences if not done correctly. An alternative method is detect the browser on the server and serve up different HTML and related assets, this technique known as RESS (responsive web design with server-side components).

A good example of a RWD site and framework in action is [Bootstrap](http://bootstrap.com), if you're interested in this concept check out [Zurb's Foundation Framework](http://foundation.zurb.com/). Note also that the latest versions of Bootstrap are designed with mobile first in mind.


Accessibility
-------------

Web Accessibility is the practice of making websites usable by people of all abilities and disablities. This means taken into account people with aural or visual weaknesses as well as those with learning difficulties. Marking things up semantically helps as tools such as screenreaders can provide better context, but paying attention to the colours you are using, text size and contrast are all part and parcel of making things accessible. In many ways visualising data is an exercise in making your data accessible.


HTML5
=====

HTML5 has become shorthand for HTML5, related new web technologies and JavaScript APIs. For short, HTML5 and friends. We're going to break each of these pieces down a bit so that we get a good overview of what is possible.

Defining an HTML5 document. We're going to be using a collaborative coding environment called [JS Bin](http://jsbin.com/) on this course, so click on that link now and lets take a look at what a skeleton HTML5 web-page looks like.



Canvas
------

You can think of canvas as a drawing surface for a web-page. If you knew HTML pre-canvas you'll this was difficult to do without using plugins like Flash. Canvas offers a way of writing pixels, lines and shapes to the screen in an intuitive way. You can read and write all the pixels of a particular canvas, you can even apply canvases to other HTML5 elements.

Although Canvas may look vector-based, it is actually rasterised, which means if you zoom in, you'll start to see the pixels.




---
Tools
Preproccessors
