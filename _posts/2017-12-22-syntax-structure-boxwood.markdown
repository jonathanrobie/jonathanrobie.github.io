---
layout: post
title: "Showing Syntactic Structure with Boxwood"
date: 2017-12-20 15:46
comments: true
external-url:
categories:
- greeksyntax package for Jupyter Notebooks
---

I recently added [Context Sensitive English Glosses and Interlinears](http://jonathanrobie.biblicalhumanities.org/blog/2017/12/21/english-glosses-interlinear/) to the `greeksyntax` package for Jupyter, but it's important to recognize the limitations of interlinears.  As [Barry Hofstetter likes to put it](http://www.ibiblio.org/bgreek/forum/viewtopic.php?f=28&t=2162&p=12700#p12700):

> There is not too much concerning which I am dogmatic. A few theological issues and the fact that interlinears are the spawn of the devil. They are the linguistic equivalent of brain eating zombies. They are the dark side, the power of which you don't want to experience...

The problem with interlinears is that they do not represent the syntactic structure of a Greek sentence at all.  Instead, the associate each word of the text with an English gloss and rely on your ability to connect English words to create meaning.  But the meaning of a Greek sentence cannot be accurately conveyed using English glosses.  Syntax diagrams do a much better job of that.

There are [many kinds of syntax diagrams](http://jonathanrobie.biblicalhumanities.org/blog/2017/12/20/treebanks-for-ancient-greek/). The `greeksyntax` package for Jupyter now supports Boxwood, a format designed to be simple and to avoid distracting readers with lots of overhead.  You can use the `q.boxwood()` method to display a sentence in this format:

```python
q.boxwood(milestone("Matt.1.20"))
```

For a fuller explanation of Boxwood and a comparison to interlinears, see this notebook:  [Boxwood - Displaying the Syntactic Structure of a Sentence](https://nbviewer.jupyter.org/github/biblicalhumanities/greek-new-testament/blob/master/labnotes/Boxwood%20-%20Syntax%20Structure.ipynb).  But for now, let me end this post with Matthew 1:20, a verse appropriate to the upcoming Christmas holiday:

> Matt.1.20 ταῦτα δὲ αὐτοῦ ἐνθυμηθέντος ἰδοὺ ἄγγελος Κυρίου κατ’ ὄναρ ἐφάνη αὐτῷ λέγων Ἰωσὴφ υἱὸς Δαυείδ, μὴ φοβηθῇς παραλαβεῖν Μαρίαν τὴν γυναῖκά σου, τὸ γὰρ ἐν αὐτῇ γεννηθὲν ἐκ Πνεύματός ἐστιν Ἁγίου· τέξεται δὲ υἱὸν καὶ καλέσεις τὸ ὄνομα αὐτοῦ Ἰησοῦν· αὐτὸς γὰρ σώσει τὸν λαὸν αὐτοῦ ἀπὸ τῶν ἁμαρτιῶν αὐτῶν.

The notebook mentioned in the last paragraph shows both an interlinear and the Boxwood representation of that verse, so take a look at it if you need help with the vocabulary it uses.  In this post, I will end by showing the Boxwood representation of the sentence:

![Matthew 1:20 (Boxwood)]({{ site.url }}/images/boxwood.png)
