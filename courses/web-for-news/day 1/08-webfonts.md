8. Web Fonts
============

Up until very recently there has only be a handful of fonts we could safely use on the web. We depend on browsers to render fonts and it's only in newer browsers can we start to support a newer technology known as Web Fonts.

Web Fonts give us design choices that print publications and native applications have had for years. In this module we're going to look at ways we can do this and the issues inherent in the system.

Note: that very few news sites are using web fonts on their main pages right now, although some are using them for their interactives.

8.1 Compatibility
-----------------

Fortunatley many browser makers realised that something like Web Fonts was required, unfortunately they didn't come to any concensus on how to do this and several font formats emerged:

`````
* EOT :       IE 6+
* WOFF :      IE 9+  Ffx 3.6+  Chm 5+  Saf 5.1+  Op 11.1+  iOS 5+   And 4.4  BB 7+  Chm m  Ffox m  IE m
* SVG fonts :                  Chm 4+  Saf 3.2+  Op 9+     iOS 3.2+ And 3+   BB 7+  Chm m
* TTF/OTF :   IE 9+  Ffx 3.5+  Chm 4+  Saf 3.1+  Op 10+    iOS 4.2+ And 2.2+ BB 7+  Chm m  Ffox m

`````

Spotty support as you can see and to cover all your bases you need to provide all four!

8.2 @font-face
--------------

@font-face is a new CSS rule that allows us to define a custom font. For now you will typically see it used like this:

`````css
@font-face {
    font-family: 'BebasNeueRegular';
    src: url('BebasNeue-webfont.eot');
    src: url('BebasNeue-webfont.eot?#iefix') format('embedded-opentype'),
         url('BebasNeue-webfont.woff') format('woff'),
         url('BebasNeue-webfont.ttf') format('truetype'),
         url('BebasNeue-webfont.svg#BebasNeueRegular') format('svg');
    font-weight: normal;
    font-style: normal;
}
`````
Then you can reference your new font similar to as you would any other:

`````css
body { font-family: "BebasNeueRegular", serif }
`````

8.3 Font Generating Services
----------------------------

Luckily there are services out there that will generate all the fonts you need, they also often provide handy example snippets of how to use them.

I can currently recommend [FontSquirrel @font-face generator](http://www.fontsquirrel.com/fontface/generator) if you want to take control fo your fonts and not rely on a third party.

Many people use [Google Fonts](http://www.google.com/fonts) which requires one stylesheet link.



8.4 Flash of Unstyled Text
--------------------------

This what you often see when your browser renders a web font for the first time. Essentially you see the text with the browser font applied, then you see the text Flash as the web font finishes loading and is applied.

There are a couple of ways of getting around this, one is to use something like [Web Font Loader](https://github.com/typekit/webfontloader) and wait for the font to be loaded before displaying text.


8.5 Icon Fonts
--------------



---

### Further info

[Quick guide to webfonts via @font-face](http://www.html5rocks.com/en/tutorials/webfonts/quick/)

