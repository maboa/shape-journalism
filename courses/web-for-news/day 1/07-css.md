7. CSS 
======

Cascading Style Sheets (CSS) is a style sheet language used for describing the presentation semantics (the look and formatting) of a document written in a markup language, such as HTML, XHTML, XML, SVG and XUL.

Designed to enable the separation of document content from document presentation.

### 7.1 History

SGML (Standard Generalized Markup Language, 1986) part of a trio of standards for electronic documents:

* SGML, reworked in 1998 into XML
* DSSSL, reworked into XSLT, XSL-FO
* HyTime, partially reworked into XLink

SGML sample
```html
<QUOTE TYPE=example> 
  typically something like <ITALICS>this</> 
</QUOTE>
```

DSSSL sample
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

CSS (Level 1 1996) unlike existing style languages like DSSSL, CSS allowed a document's style to be influenced by multiple style sheets. 

One style sheet could inherit or "cascade" from another, permitting a mixture of stylistic preferences controlled equally by the site designer and user.

### 7.2 Syntax

A _style sheet_ consists of a list of _rules_. Each _rule_ consists of one or more _selectors_, and a _declaration block_. 


**Selectors** are used to declare which part of the markup a style applies to. They usually apply to:

* all elements of a specific type `h1, h2`
* elements specified by an attribute, usually **id** `#content` and **class** `.author, p.small`
* structures based on the document tree `footer small, header > h1` 

```css
html, body {
	width: 100%;
	font-size: 12px;
}

p.info {
	font-size: 10px;
	color: blue;
} 

a {
	text-decoration: none;
}

a:hover {
	border-bottom: 1px solid blue;	
}
```

**Pseudo-classes** are used in CSS selectors to permit formatting based on information that is _outside the document tree_. 

### 7.3 Capabilities

#### CSS Level 1 (1996)

* Font properties such as typeface and emphasis
* Color of text, backgrounds, and other elements
* Text attributes such as spacing between words, letters, and lines of text
* Alignment of text, images, tables and other elements
* Margin, border, padding, and positioning for most elements

#### CSS 2 (1998)

* absolute, relative, and fixed positioning of elements and z-index
* float, clear http://css-tricks.com/all-about-floats/
* media types

```css
@media print {
	body { font-size: 10pt }
}
@media screen {
	body { font-size: 13px }
}
@media screen, print {
  body { line-height: 1.2 }
}
```

* bidirectional text
* new font properties (shadows)

#### CSS 2.1 (2004-2007-2009)

Fixes errors in CSS 2 spec, adds already-implemented browser extensions to the specification.

#### CSS 3

Unlike the large CSS 2.1 spec, this is divided into modules (around 50), the most known and stable ones are:

* media queries

```css
@media (max-width: 600px) {
  .sidebar {
    display: none;
  }
}
```

Note: Responsive Design, see examples:
- http://mediaqueri.es 
- BBC Responsive News blog http://responsivenews.co.uk
- ProPublica http://www.propublica.org/nerds/item/how-we-made-propublica.org-look-better-on-your-smartphone-adaptive see http://projects.propublica.org/docdollars/ and http://projects.propublica.org/redistricting-maps/protect-your-vote

There are various approaches in having not only the layout responsive, but also responsive images, videos, etc.

* selectors Level 3 (:empty, :target, :checked, :lang(fr), :not(selector))
* backgrounds and borders
* multi-column layout

```css
.article {
  column-count: 2;
  column-gap: 20px;
}
```

See example at http://www.webdesignerdepot.com/2013/03/how-to-use-css3-columns/

#### CSS4

Some modules are "level 4", collectively they are referred as "CSS4."

### sss

- paged media, page breaks
- CSS3 shapes for content
- typography, hypens
- 3D
- animation
- translation vs positioning


---

[<< previous 6. WebGL](06-webgl.md) | [next 8. Web Fonts >>](08-webfonts.md)