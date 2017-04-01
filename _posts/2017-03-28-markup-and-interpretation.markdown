---
layout: post
title: Markdown and Interpretation
date: 2017-03-30 15:46
comments: true
external-url:
categories: 
- XML, XPath, and XQuery
---

In a typical day, I use JSON, markdown, HTML, and XML. I generally use JSON for data that is naturally modeled as rows in a table or objects in a programming language.  I use markdown for blogging and Wikis.  I use HTML for web presentation.  But for representing biblical texts, lexicons, and treebanks I use XML, a markup language designed specifically for adding metadata to text so that text and metadata can be used together when querying or studying a text. For processing XML, I generally use XQuery and XPath, which natively understand XML. I have recently had quite a few long exchanges about this with my friend and colleague [Dirk Roorda](http://knaw.academia.edu/DirkRoorda), who uses Python almost exclusively and avoids XML when he can, and I thought it might be useful to write about the advantages of an XML toolchain for a variety of tasks that are central to the digital humanities.  As I continue to work and blog, I will show you examples of my work here, often in XML and XQuery, but also in other representations using other tools.

In this post, I explore XML as a form of interpretation for texts. I also explore the ways that XQuery and XPath can leverage this interpretation to do powerful queries using nothing more than the XML document.

## XML: The Native Language of Digital Humanities

Most people who have worked in digital humanities are familiar wth the [Text Encoding Initiative](http://www.tei-c.org/), which provides guidelines for representing texts in XML. A [wide variety of projects](http://www.tei-c.org/Activities/Projects/) use the TEI guidelines, and many others use other XML formats that are tailored to the need of a particular project. At [biblicalhumanities.org](), many of [the texts on our dashboard](http://biblicalhumanities.org/dashboard/) are represented in XML. XML is a great fit for digital humanities because it well suited to the kinds of documents and interpretation used in the humanities.  Here are a few key advantages of XML:

- *Exposing the logical structure of a document*.  Before markup languages, software generally treated documents as a black box, readable mainly by human beings. Markup languages expose the logical structure of a document so that it can be processed by software.
- *Reusability*.  By exposing the logical structure, markup languages allow software to reuse document data in ways not foreseen by the original creator.
- *Longevity*.  The binary formats of word processors change over time, and it is often very difficult to find software that can open a document written 10 years ago. Markup languages do not depend on binary formats. If an archaeologist were to discover an XML document 100 years from now, odds are that it could be interpreted without the software originally used to create it.

XQuery is a good fit for digital humanities because XML is the native language for both. In XQuery, XML is the fundamental data structure, and the language is designed to explore, create, and transform XML. Digital humanities is primarily about texts and many of these texts are in XML. 

Consider the following XML fragment, an excerpt from a [Wordhoard](http://wordhoard.northwestern.edu/userman/index.html) edition of Julius Caesar: 

```xml
<div xml:id="sha-juc103">
    <head>Act 1, Scene 3</head>
    <stage>The same. A street.</stage>
    <stage>Thunder and lightning. Enter from opposite sides, CASCA, with his sword drawn, and CICERO.</stage>
    <sp who="Cicero">
        <speaker>Cicero</speaker>
        <l xml:id="sha-juc103001" n="1"> Good even, Casca: brought you Caesar home? </l>
        <l xml:id="sha-juc103002" n="2"> Why are you breathless? and why stare you so? </l>
    </sp>
    <!-- !!! SNIP !!! -->
</div>
```

The XML markup tells you that there is a division called "Act 1, Scene 3", that two lines of this text are stage directions, and that there is a speech, given by Cicero, that contains two lines.  Each line has an topic to make it easy to refer to it in annotations. Because this information is marked up in XML, XQuery can easily perform queries based on the structure of the play.  For instance, a query can tell you which characters appear in the same scene, which characters speak the most line, or which characters are most frequently spoken about by whom.  Using XQuery, there is no need to map this information into another programming structure before querying it, all you need is XQuery and a marked-up text.  Looking at the XML gives you a pretty good idea how to write the query, and the results of the query are expressed in the same language as the input.

The play also starts with a list of personae that can be used to see who Cicero and Casca are:

```xml
<castGroup>
    <head>Senators</head>
    <castItem keyword="role">
        <role xml:id="Cicero">Cicero</role>
    </castItem>
    <!-- !!! SNIP !!! -->
</castGroup>

<castGroup>
    <head>Conspirators against Julius Caesar</head>
    <castItem keyword="role">
        <role xml:id="BrutusM">Marcus Brutus</role>
    </castItem>
    <castItem keyword="role">
        <role xml:id="Cassius">Cassius</role>
    </castItem>
    <castItem keyword="role">
        <role xml:id="Casca">Casca</role>
    </castItem>
    <!-- !!! SNIP !!! -->
</castGroup>
```

With this information, an XQuery can characterize each scene by the kinds of people who speak - in this case, a Senator is talking to a Conspirator. We could perform queries to search for other scenes where Cicero talks to a conspirator, other senators talk to a conspirator, conspirators talk to each other, etc.  Again, there is no need to transform this XML into any other form before querying to explore these relationships. XQuery treats an XML document or a collection of XML documents like a database. Queries can search based on the document's structure, and they can also create new documents or transform existing structures into new ones.  Digital humanists have already marked up a huge treasure trove of important texts in XML and XQuery is an ideal way to explore these treasures.  Often, the same document has been marked up different ways by different groups to record the information that mattered most to each. Queries on various editions of Julius Caesar can provide a more complete picture by leveraging each kind of markup.

## Markup as Interpretation

The XML markup used in a project directly reflects the priorities of the project - what aspects of the text are important to you? Let's demonstrate this by looking at very different ways of marking up the same text.  Here is a short Greek text from the Gospel of John. The text means "Jesus wept":

```txt
John 11:35
ἐδάκρυσεν ὁ Ἰησοῦς.
```

We use HTML markup to indicate how to format it - but note that this HTML tells us very little about the meaning of the text, and does not even tell us that "John 11:35" is a verse:

```xml
<h1>John 11:35</h1>
<p>
  <sup>35</sup>ἐδάκρυσεν ὁ Ἰησοῦς.</span>
</p>
```

The XML community generally prefers XML markup that is about the meaning of the text, not about formatting. Meaningful markup can be used to query the text, and stylesheets can be used to format it in a variety of ways depending on the output medium and the purpose. We can improve this a little by using a TEI encoding for biblical texts called [OSIS](http://www.bibletechnologies.net).  This example is modified slightly from the [SBLGNT markup](http://sblgnt.com/download/):

```xml
<verse osisID="John.11.35" sID="John.11.35">
<w>ἐδάκρυσεν</w> <w>ὁ</w> <w>Ἰησοῦς</w>.
</verse>
```

This is obviously a markup designed for print purposes, and is only marginally more meaningful than the HTML example.  Now let's look at an example from the [Nestle 1904 Lowfat Syntax Trees](https://github.com/biblicalhumanities/greek-new-testament/tree/master/syntax-trees/nestle1904-lowfat) that tells us a little more about the text from a linguistic perspective:

```xml
<sentence>
  <cite>Jhn11:35:1-11:35:3</cite>
  <wg nodeId="430110350010030" class="cl" role="s">
    <w id="43011035001" osisId="John.11.35!1" class="verb" role="v" head="true"
        lemma="δακρύω"
        normalized="ἐδάκρυσεν"
        person="third"
        number="singular"
        tense="aorist"
        voice="active"
        mood="indicative"
        gloss="wept">ἐδάκρυσεν</w>
    <wg nodeId="430110350020020" class="np" role="s">
        <w id="43011035002" osisId="John.11.35!2" class="det"
          lemma="ὁ"
          normalized="ὁ"
          case="nominative"
          gender="masculine"
          number="singular"
          gloss="the">ὁ</w>
        <w id="43011035003" osisId="John.11.35!3" class="noun" head="true"
          lemma="ἰησοῦς"
          normalized="ἰησοῦς"
          case="nominative"
          gender="masculine"
          number="singular"
          gloss="Jesus">Ἰησοῦς.</w>
    </wg>
  </wg>
</sentence>
```

The text is the same as for the previous examples, but the information contained in the markup is quite different, because the people who did the markup were interested in the syntax. Another group of digital humanists working with the same text might be interested in other things.  In America, digital humanities often has a strong focus on [distant reading](http://www.nytimes.com/2011/06/26/books/review/the-mechanic-muse-what-is-distant-reading.html), which is an excellent approach if you have a massive number of texts that cannot reasonably be carefully read by a human being.  In biblical studies, this is often not our problem.  We have a small number of biblical texts that are at the center of everything we do, and they have been carefully studied for thousands of years.  Encoding a text in XML is an act of careful reading, and the XML represents the interests of the reader. For instance, here is an excerpt from the markup for this text as found on [codexsinaiticus.org](http://codexsinaiticus.org/download), markup conventions are documented [here](http://codexsinaiticus.org/download/XMLspecs_sinaiticus.pdf).

```xml
<pb id="S-80-8v" corres="E-80-8v" n="80-8v" scribeid="A" archive="BL" localfol="254b"/>
<cb id="S-80-8v-1" corres="E-80-8v-1" n="1" />
<!-- SNIP -->
<lb  id="S-80-8v-1-14" corres="E-80-8v-1-14" n="14" vnumber="35" />
<w n="2">εδακρυϲεν</w>
<app>
    <rdg keyword="main-corr"><w n="3"></w></rdg>
    <rdg keyword="corr" n="ca"><w n="3">ο</w></rdg>
</app>
<w n="4"><hi rend="ol2">ιϲ</hi></w> <w n="5">·</w>
```

This is a transcription of a papyrus called Codex Sinaiticus, and the markup is designed to tell you what page the text found on and where it is located.  The pages of this papyrus are no longer located in one place, 347 leaves are in the British Library in London, 12 leaves in Saint Catherine's Monastery, 43 leaves in the Leipzig University library, and 3 leaves in the Russian National Library in Saint Petersburg.  In the above markup, the initial `pb` element tells us that this is page `80-8v`, which is found in the British Library. The `cb` element tells us the text is in column 1. The `lb` element tells us the text is in line 14 of the column.  The markup also tells us which of several scribes wrote this particular portion of the papyrus using a `scribeid` attribute.  Several people corrected the text later; on this particular page, a scribe added a missing word.

This is no longer exactly the same text because it uses ancient spelling without diacritics, but it is still "the same text" with the same Greek words. For instance, ἐδάκρυσεν is spelled εδακρυϲεν in this transcription, and the name of Jesus has been shortened from Ἰησοῦς to ιϲ.  This project does not use markup to indicate such abbreviations, which are called nomina sacra, but a project interested in doing so can add that information to the markup (as they do at [http://greekcntr.org/](http://greekcntr.org/)).

```xml
<w><abbr keyword='nominasacra'>ιϲ</abbr></w>
```

## Mining the Text Together

The humanities is all about rich interpretation of text. As you can see, XML allows the same text to be marked up in a wide variety of ways, depending on the goals of the project. And in many cases, the same text has already been marked up by different groups, providing rich data that can be harvested using queries.  A single query can also look at many different representations of the same text, bringing together syntax, textual criticism, discourse analysis, and original manuscripts that may have very different structure.

In the last few years, we have finally started to see the release of significant amounts of freely licensed data for digital biblical studies, and I suspect nobody has even begun to scratch the surface of what can be done with this data.  I hope we are on the verge of a new era. In this blog, I expect to share many ways that I use XQuery and other tools to mine the texts found in the [biblicalhumanities.org dashboard](http://biblicalhumanities.org/dashboard).  I will share queries that I use to test the consistency of data in syntax treebanks, generate class materials for teaching Greek as a living language, frequency lists, examples of syntactic constructions like supplementary participles or articular infinitives, and other tasks that arise during the course of my work generating resources for studying Greek.  Each of these queries uses data in ways not foreseen by the people who created the data in the first place, creating data that is valuable for particular purposes.

But I am much more excited about things that I have not yet even imagined, the things I will learn from others in this community who are working with the same texts. I am a small part of [biblicalhumanities.org](biblicalhumanities.org), where some people are working on things I would never have thought of, and a much smaller part of digital biblical studies as a whole. I hope this blog will inspire others to share what they are learning, to do their own blogging, and to help us grow an ecosystem of biblical data where one dataset builds on another.