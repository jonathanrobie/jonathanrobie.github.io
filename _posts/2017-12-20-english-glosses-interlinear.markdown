---
layout: post
title: "Context Sensitive English Glosses and Interlinears"
date: 2017-12-21 12:30
comments: true
external-url:
categories:
- greeksyntax package for Jupyter Notebooks
---

I am working on making the `greeksyntax` package for Jupyter more user-friendly in various ways, and one of the obvious ways to do that is to provide English glosses.

Contextual glosses in English are now available in the Nestle 1904 Lowfat trees. These glosses have been available in the [Nestle1904 repository](https://github.com/biblicalhumanities/Nestle1904), where they were extracted from the [Berean Interlinear Bible](http://interlinearbible.com/) with their generous permission.  I merged them into the Nestle 1904 Lowfat treebank using [this query](https://github.com/biblicalhumanities/greek-new-testament/blob/master/syntax-trees/xquery/add-berean-glosses.xquery).  And now they are available whenever you use this treebank.

In a Jupyter notebook, the easiest way to use these glosses is to wave your mouse over a word that you need a gloss for.  The gloss is displayed along with morphological information:

![Glosses in Tooltips]({{ site.url }}/images/tooltip.png)

There is also an `interlinear()` method that displays interlinear information for every word element in a query result:

![Interlinear method]({{ site.url }}/images/interlinear.png)

And you can also use glosses as data.  For instance, this query shows all of the words translated 'out of' in their declined form, with normalized accents:

```xquery
distinct-values(//w[@gloss = 'out of']/@normalized)
```

And this query shows all of glosses given for the word κατά:

```xquery
distinct-values(//w[@normalized = 'κατά']/@gloss)
```

You can see these queries and their results in this Jupyter Notebook: [English Glosses](https://github.com/biblicalhumanities/greek-new-testament/blob/master/labnotes/English-Glosses.ipynb)
