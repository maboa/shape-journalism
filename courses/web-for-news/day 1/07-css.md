7. CSS
======

### History

SGML (Standard Generalized Markup Language, 1986) part of a trio of standards for electronic documents:

* SGML, reworked in 1998 into XML
* DSSSL, reworked into XSLT, XSL-FO
* HyTime, partially reworked into XLink

```
<QUOTE TYPE=example> 
  typically something like <ITALICS>this</> 
</QUOTE>
```

```scheme
(element DIV
 (let ((align (attribute-string "align")))
  (make display-group
	quadding:
	  (case align
		(("LEFT") 'start)
		(("CENTER") 'center)
		(("RIGHT") 'end)
		(else 'justify))
	(process-children-trim))))
```

CSS (Level 1 1996) was based on 2 out of 9 proposals. Unlike existing style languages like DSSSL, CSS allowed a document's style to be influenced by multiple style sheets. 

One style sheet could inherit or "cascade" from another, permitting a mixture of stylistic preferences controlled equally by the site designer and user.

#### CSS 1

* Font properties such as typeface and emphasis
* Color of text, backgrounds, and other elements
* Text attributes such as spacing between words, letters, and lines of text
* Alignment of text, images, tables and other elements
* Margin, border, padding, and positioning for most elements

#### CSS 2 (1998)

* absolute, relative, and fixed positioning of elements and z-index
* media types
* aural style sheets 
* bidirectional text
* new font properties such as shadows

#### CSS 2.1 (2004-2007-2009)

Fixes errors in CSS 2 spec, adds already-implemented browser extensions to the specification.

#### CSS 3

Unlike the large CSS 2.1 spec, this is divided into modules (around 50), the stable ones are:

* media queries
* namespaces
* selectors Level 3
* colour
* backgrounds and borders
* multi-column layout

#### CSS4

Some modules are "level 4", collectively they are referred as "CSS4."

---

[<< previous 6. WebGL](06-webgl.md) | [next 8. Web Fonts >>](08-webfonts.md)