---
layout: post
title: "TOC2: Organizing Long and Complex Notebooks"
date: 2017-12-20 17:00
comments: true
external-url:
categories:
- greeksyntax package for Jupyter Notebooks
---

When I first started working with Jupyter Notebooks, I was amazed that it was so easy to pull together large amounts of useful information.  But within a few hours, I was frustrated that it was difficult to organize and navigate in long and complex notebooks, and I was also frustrated with the difficulty of publishing them for others.

Fortunately, Jupyter also has [notebook extensions](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest), including an excellent [Table of Contents](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/nbextensions/toc2/README.html) extension that also creates a left-hand navigation bar, automatically numbers sections, and makes it much easier to work with long and complex notebooks.  I used it to organize a tutorial I posted here earlier, here is a screenshot:

![greeksyntax tutorial]({{ site.url }}/images/jupyter-toc.png)

The frame on the left is a navigation bar that contains a table of contents. If you click on an item, the right hand frame navigates to the corresponding heading.

Even better: if you also add the [Export Embedded HTML](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/nbextensions/export_embedded/readme.html) extension, the navigation window and most other features of the table of contents are preserved.  You can see the result in this newly formatted version of the tutorial:

[Tutorial: Greek Syntax Queries using Lowfat and Jupyter Notebooks](http://jonathanrobie.biblicalhumanities.org/assets/greeksyntax-tutorial.html)

The easiest way to install these extensions is to use the [Jupyter Nbextensions Configurator](https://github.com/Jupyter-contrib/jupyter_nbextensions_configurator). Follow the link and follow the instructions.
