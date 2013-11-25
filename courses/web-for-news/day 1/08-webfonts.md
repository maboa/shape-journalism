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

With the advent of retina screens and the requirement to create web pages that look good on all screens, it seems that the age of the bitmap -- for icons at least -- is coming to an end.

For bitmapped icons to look good on all screens you need to create at least two different versions and create some clever mechanism to serve the correct one to the requesting browser.

Add to all that, the inflexibility of having a fixed colour bitmapped icon and the idea of an icon font starts to sound very attractive.

The two main advantages then:

* Looks perfect on every screen
* Colours and relative sizes can be changes easily

You can create your own fonts or grab one that's been already made. [Fontello](http://fontello.com/) is a great service that allows you to choose from a large selection of fonts and create a download with just those fonts included. You can also upload your own SVGs and create your own fonts. It also creates the CSS and everything you need to get going with your icon fonts.

You can imagine a newsroom having it's own set of standard fonts.

To get rid of the flash of unstyled text there is another trick.

### Data URIs

Data URI's have a number of advantages, one of them is that the data is inlined into the page. If we base64 encode our fonts then we ensure they are loaded before the interactive is loaded. In some ways this is a simpler and lighter method than relying on events.

8.6 Iconfonts Fallback
----------------------

* Create bitmap images for fallbacks
* Treat as optional enhancements
* Use [Grunticon](https://github.com/filamentgroup/grunticon) Fallback

[Filament Group Research and Solution](https://t.co/iDQrFBfmPh)

8.7 Exercise
------------

1. Create a page with content styled in a non-standard browser font. 
2. Add icon font navigation.


### Other

- proper fonts for indices http://www.typography.com/fonts/whitney/features/whitney-indices
- for tabular figures http://www.typography.com/fonts/whitney/features/whitney-numerics
- accessible icon fonts http://symbolset.com
- fonts for datavisualisation FF Chartwell https://vimeo.com/41772735
- **responsive typography** http://ia.net/blog/responsive-typography-the-basics/ and http://www.awwwards.com/responsive-typography-a-roundup-of-the-best-articles-and-tutorials.html


---

### Further info

[Quick guide to webfonts via @font-face](http://www.html5rocks.com/en/tutorials/webfonts/quick/)
[flaticon icon fonts](http://www.flaticon.com/)
[fontastic](http://fontastic.me/)
[CSS Tricks - 5 Use Cases for Icon Fonts](http://css-tricks.com/five-use-cases-for-icon-fonts/)

---

[<< previous 7. CSS](07-css.md) | 	[next 9. New Form Elements >>](09-forms.md)
