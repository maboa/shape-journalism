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
|Firefox 3.6+    || Y   | 26+ |     | Y   | 14+  || Y   | 4+   | 26+  ||
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
Note that most mobile browsers support whatever the underlying operating system supports, this is the approach that Firefox desktop also takes, which means that MP3 support may vary as they transition.


