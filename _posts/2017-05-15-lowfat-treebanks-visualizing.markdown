---
layout: post
title: "Lowfat Treebanks: Visualizing Sentences"
date: 2017-05-12 15:46
comments: true
external-url:
categories: Treebanks
---

In 2013, Randall Tan of the Asia Bible Society (now known as the [Global Bible Initiative](http://www.globalbibleinitiative.org/)) was able to provide me with some of the treebank data he had developed together with Andi Wu. When I asked, they decided they were willing to let Randall and me publish this data [on Github](https://github.com/biblicalhumanities/greek-new-testament). These treebanks are based on the [Head-Driven Phrase Structure Grammar (HPSG)](http://hpsg.stanford.edu/) model, and now support both [SBLGNT](https://github.com/biblicalhumanities/greek-new-testament/tree/master/syntax-trees/sblgnt) and [Nestle1904](https://github.com/biblicalhumanities/greek-new-testament/tree/master/syntax-trees/nestle1904).  Well before that, Dag Haug published the [PROIEL treebank](https://github.com/proiel/proiel-treebank/), a dependency treebank.  These are both high-quality open treebanks that I recommend. The [OpenText.org](http://opentext.org/) syntax trees are also high-quality, but less open than originally intended because of their dependence on the Nestle Aland. The [Cascadia Syntax Graphs](https://www.logos.com/resources/CSGNT/cascadia-syntax-graphs-of-the-new-testament) are commercial syntax trees that are also excellent.

But I wanted syntax trees that met a particular set of needs:

- Easy to visualize, emphasizing the most important relationships as simply as possible.
- Easy to query.
- Designed for use with XML technologies like CSS, XQuery, XSLT.
- Easy to relate to other resources in the [open biblical data community](biblicalhumanities.org/dashboard).
- Supports asking and answering questions about a sentence in the classroom setting.

In 2015, Micheal Palmer and I created the first Lowfat Syntax Trees for [Nestle1904](https://github.com/biblicalhumanities/greek-new-testament/tree/master/syntax-trees/nestle1904-lowfat) and [SBLGNT](https://github.com/biblicalhumanities/greek-new-testament/tree/master/syntax-trees/sblgnt-lowfat) to support our work teaching Greek as a living language.

In today's post, I will focus on visualizing sentence structure, showing three ways of displaying this structure and how they are implemented using CSS.  I will also explore some ways these treebanks are being improved to allow better visualization.  In future posts, I will explore other aspects of the requirements listed above.

## Thinking Clearly about Sentence Structure

The right notation makes it easier to think clearly.  The wrong notation can lead people to wrong conclusions. In languages, the relationships among words are at least as important as the words themselves.  We need notations that make it easy to think about these relationships. Interlinears, which are widely used, describe the morphology of individual words, but not the structure of phrases, clauses and sentences.  For instance, here is John 1:1 in the [BibleHub Interlinear](http://biblehub.com/interlinear/john/1-1.htm):

![BibleHub]({{ site.url }}/images/john.1.1.interlinear.png "John 1:1 in BibleHub Interlinear")

Should this be translated "the Word was God" or "God was the Word"? If you don't know how to read the Greek clause, the interlinear does not help you answer the question because it does not identify the subject, verb, and predicate of the clause.  Both subject and predicate are nominative, so the morphology does not answer the question, but a simple label does:

predicate | verb | subject
----------|------|--------
θεὸς      | ἦν   | ὁ λόγος  
God       | was  |the Word

This works well for this simple example, but complex sentences have a nested structure that cannot easily be represented in tables.  To represent sentences in general, we need a notation that can handle nested structures well. Most treebanks have a way of doing this, but many people complain that these displays are too complex.  Can we do better?  Can we come up with simpler notations that help us think more clearly about the syntax of a sentence?

## Visualizing Sentences: Brackets and Labels

The first notation I tried for this, several years ago, used brackets and labels much like those found on [Eliran Wong's site](http://eliranwong.com) for linguistic annotations.  This works quite well for this particular sentence:

![John 1:1]({{ site.url }}/images/john.1.1.eliran.greek.png "John 1:1 in Brackets (Greek)")

Here are the labels used above:

- *s* - subject
- *vc* - "verbal copula" - a verb that links a subject to a predicate
- *p" - predicate

This representation works quite well for most sentences, but it does have a few limitations. For complex sentences, I find myself counting brackets to make sure I understand the overall structure - this is particularly annoying when marking up a sentence in a text processor. For sentences with certain word order issues, it needs to be extended to allow a subject or predicate to be interrupted.  I tried several variations on this using indentation and aligning opening and closing brackets in the same column, but I have not found an approach along these lines that works well for all sentences.

There is another problem that involves word order.  In Greek, a constituent like the subject or predicate can be interrupted for several reasons. To work well, this notation needs to be extended to handle these cases, and the Lowfat treebank needs to be restructured to support it.  This issue is somewhat complex, and best left for another post.

For most sentences though, this is a good representation.  Ideally, an environment should allow a sentence to be visualized in more than one way, and this is one that I would use frequently.

## Visualizing Sentences: Treedown

Like the bracket notation, Treedown is a simple notation that can be written with any text editor, and can easily be exchanged as text.  To show the overall structure of a sentence, Treedown uses indentation instead of brackets. This makes it easier to see the levels of nesting and to grasp the overall structure of a complex sentence. Many people have independently discovered that sentences are much easier to understand if you just add a little whitespace to show the hierarchical structure, so I started by looking for a way to do just that. I quickly realized that it was very helpful to label the role of each part of a clause.  Here is an example of Treedown, showing John 1:1 in Greek and in English. 

![John 1:1]({{ site.url }}/images/john.1.1.treedown.greek.png "John 1:1 in Treedown (Greek)") | ![John 1:1]({{ site.url }}/images/john.1.1.treedown.english.png "John 1:1 in Treedown (English)")

Let's compare Treedown to more traditional syntax trees. Here is the same sentence in the Cascadia Syntax Graphs mentioned above, as shown in [Logos 7](https://www.logos.com/).  I added the green box, which shows the portions of the structure that are represented in Treedown:

![John 1:1]({{ site.url }}/images/john.1.1.cascadia.png "John 1:1 in Cascadia Syntax Graphs")

Internally, Lowfat trees have a representation for most of the nodes in the Cascadia graph, and they are available for queries, but Treedown does not display them all. The nodes on the left-hand side of the green box are present in every syntax tree, so they are redundant.  The syntax of noun phrases and prepositional phrases is not difficult for most human beings, so Treedown simplifies the display by not showing those nodes.

## Visualizing Sentences: Brackets


## Visualizing Sentences: Boxwood


## More Complex Examples

