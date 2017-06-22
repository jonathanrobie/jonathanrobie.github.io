---
layout: post
title: A Lowfat Treebank Browser
date: 2017-05-22 15:00
comments: true
external-url:
categories: 
- Treebanks
- XML
---

## A Lowfat Treebank Browser

I wrote a simple Lowfat Treebank browser, which can now be found here:

[Lowfat Treebank Browser](http://www.ibiblio.org/bgreek/resources/syntax-trees/reader/)

The display shows only the syntactic relationships in a sentence, not the morphology (which can be seen in the source files).  I expect to provide a query interface to this, I need to clear a hurdle with my service provider first.

While writing this I hit an interesting issue when loading XML using HTML controls. I thought it might be worth posting about that in case someone else is facing the same issues.  I wanted to load an XML file with CSS styling, and hit several issues when I tried to use JQuery to do this.  I asked a few questions on Stack Exchange, and somone suggested that I use an iframe and change the `src` attribute to load the file.  Voila!  Iframes have gone out of style, but for loading XML with CSS, they work very well.

The code that does this is [in the syntax trees repo](https://github.com/biblicalhumanities/greek-new-testament/tree/master/syntax-trees/reader).  Here's the main body of the HTML page, with some text removed for the sake of brevity:

```html
<body>
	<div id="top">
	  	<h2>Lowfat Syntax Tree Browser</h2>
	
	  	<form action="javascript:loadPassage()">
		  <input type="text" name="passage" id="passage" value="John 3:16" autofocus>
		  <button>Go!</button>
	  	</form> 
	</div>	
	<iframe id="display" src=""></iframe> 
</body>
```

When a user types in a verse reference and hits the Go button, the `loadpassage()` function loads a passage by finding the right file and setting the name of the src attribute to point to that file:

```javascript
function loadPassage() {
    var passage = document.getElementById("passage").value;

    document.getElementById("display").src = treeFile(passage, "nestle1904");
}
```

The XML file already contains the CSS needed to format it.  I hit one other snag along the way:  on some browsers, the top window disappeared when this file was loaded.  The solution was to allocate a fixed size for the top window, and allocate the rest for the iframe.  Here is the CSS that does that:

```css
html, body, iframe {height: 100%}

#top {
	height: 120px;
}

iframe {
	overflow: scroll;
	background-color: antiquewhite;
	width: 100%;
	height: calc(100% - 120px);
}
```
