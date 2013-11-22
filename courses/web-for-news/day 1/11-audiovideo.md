11. Audio and Video
===================

Audio and Video on the web currently tend to take the form of black boxes, but there is so much more that we can do to create richer experiences using the audio and video elements.

Browser support for `<audio>` and `<video>` elements are good.

11.1 Desktop Support
--------------------

* Chrome 10+
* Firefox 3.6+
* Internet Explorer 9+
* Opera 10+
* Safari 5+

11.2 Mobile Support
-------------------

* Android 2.3+
* Blackberry 6+
* Firefox Mobile
* Chrome Mobile
* Internet Explorer Mobile
* Opera Mobile 11+
* Mobile Safari 4+

11.3 Codec Support
------------------

Up until very recently no one codec was supported by all browsers. This is changing rapidly.

###Audio

`````
                 Audio                           Video
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Browser         || Ogg | MP3 | AAC | PCM | Opus || Ogv | WebM | H264 ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Firefox 3.5+    || Y   | 26+ |     | Y   | 14+  || Y   | 4+   | 26+  ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Safari 5+       ||     | Y   | Y   |     |      ||     | Y    | Y    ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Chrome 6+       || Y   | Y   | Y   | 9+  |      || Y   | Y    | Y    ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Opera 10.5+     || Y   |     |     | Y   |      || Y   |      | Y    ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|IE 9+           ||     | Y   | Y   |     |      ||     |      | Y    ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Firefox Mobile  || Y   | Y   | Y   | Y   | Y    || Y   | Y    | Y    ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Safari iOS3+    ||     | Y   | Y   | 4.2+|      ||     |      | Y    ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Chrome Mobile   ||     | Y   | Y   | Y   |      ||     | Y    | Y    ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Opera Mobile    || Y   | Y   | Y   | Y   |      ||     | Y    | Y    ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|IE Mobile       ||     | Y   | Y   |     |      ||     |      | Y    ||
+----------------++-----+-----+-----+-----+------++-----+------+------++
|Android 2.3+    || Y   | Y   | Y   | Y   |      ||     | Y    | 4.4  ||
+----------------++-----+-----+-----+-----+------++-----+------+------++

`````
Note that most mobile browsers support whatever the underlying operating system supports, this is the approach that Firefox desktop also takes, which means that support may vary as they transition.

Note also MP4/H.264/AAC is currently shipping in Firefox on Windows Vista and later. It will ship on Linux (with GStreamer+codecs enabled) in Firefox 26. MacOSX will probably come in Q1 or Q2 next year. WinXP is work in progress.

11.4 Simple Audio Example
-------------------------

`````html
<audio controls>
   <source src="elvis.mp3" type="audio/mpeg" >
   <source src="elvis.oga" type="audio/ogg" >
</audio>
`````


11.5 Simple Video Example
-------------------------

`````html
<video width="320" height="240" controls>
   <source src="elvis.mp4" type="video/mp4" >
   <source src="elvis.webm" type="video/webm" > 
</video>
`````

11.6 Fallbacks
--------------

`````html
<video width="320" height="240" controls>
   <source src="elvis.mp4" type="video/mp4" >
   <source src="elvis.ogv" type="video/ogg" >
   <source src="elvis.webm" type="video/webm" >
   <!-- add your fallback solution here -->
</video>
`````
See also: [Simple HTML5 video player with Flash fallback and custom controls](http://dev.opera.com/articles/view/simple-html5-video-flash-fallback-custom-controls/)

11.7 HTML5 Media Attributes
---------------------------

* src - url of media
* autoplay*
* loop
* controls - display the controls
* muted
* preload* | none | metadata | auto |
* type
* height / width (video only)

*often disabled on mobile.

11.8 Exercise
-------------

Embed video and audio into a web page with maximum cross-browser compatibilty and a simple fallback (just a link to the media file will do) Media files are provided. Create the minimal possible markup for an HTML5 web page that contains both audio and video.

* http://jPlayer.org/audio/ogg/Miaow-01-Tempered-song.ogg
* http://jPlayer.org/audio/mp3/Miaow-01-Tempered-song.mp3
* http://jPlayer.org/video/webm/Big_Buck_Bunny_Trailer.webm
* http://jPlayer.org/video/m4v/Big_Buck_Bunny_Trailer.m4v

([solution](http://jsbin.com/AdiFeWo/8/))

11.9 Introduction to the Media API
----------------------------------

You can do a lot in JavaScript without using any markup.
Let's take a look at a few of the methods:

`````javascript
var myAudio = document.createElement('audio');
	
if (myAudio.canPlayType('audio/mpeg')) {
   myAudio.setAttribute('src',
    'http://jPlayer.org/audio/mp3/Miaow-07-Bubble.mp3');
}

if (myAudio.canPlayType('audio/ogg')) {
   myAudio.setAttribute('src',
    'http://jPlayer.org/audio/ogg/Miaow-07-Bubble.ogg');
}

alert('play');
myAudio.play();
alert('stop');
myAudio.pause();
`````
11.10 Creating Your First Audio Player
--------------------------------------

HTML:

`````html
<audio id="my-audio">
   <source src="http://jPlayer.org/audio/mp3/Miaow-07-Bubble.mp3" >
   <source src="http://jPlayer.org/audio/ogg/Miaow-07-Bubble.ogg" >
<!-- place fallback here as <audio> supporting browsers will ignore it -->
   <a href="elvis.oga">http://jPlayer.org/audio/ogg/Miaow-07-Bubble.ogg</a>
</audio>

<!-- we create our play and pause button next -->
<a id="play" href="#">play</a>
<a id="pause" href="#">pause</a>
`````

JavaScript:
`````javascript
window.onload = function(){
   var myAudio = document.getElementById('my-audio');
   var play = document.getElementById('play');
   var pause = document.getElementById('pause');
	
   // associate functions with the 'onclick' events
   play.onclick = playAudio;
   pause.onclick = pauseAudio;
	
   function playAudio() {
      myAudio.play();
   }
	
   function pauseAudio() {
      myAudio.pause();
   }
}
`````

11.11 Excercise
---------------

1. Create a custom video and audio player with play and pause buttons.
2. Do not use the controls attribute.
3. Try and create with maximum x-browser compatibilty and simple links to your media as fallbacks.

[solution](https://gist.github.com/anonymous/7293594)

###Further Info

[HTML5 Audio - The State of Play](http://html5doctor.com/html5-audio-the-state-of-play/)
[HTML5 ROCKS - HTML5 Video](http://www.html5rocks.com/en/tutorials/video/basics/)

---

[<< previous 10. Semantic Markup](10-semantic.md)