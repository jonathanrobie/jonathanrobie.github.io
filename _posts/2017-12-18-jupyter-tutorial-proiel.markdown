---
layout: post
title: "Second Opinions: Jupyter Notebooks and PROIEL Lowfat"
date: 2017-12-18 15:46
comments: true
external-url:
categories:
- greeksyntax package for Jupyter Notebooks
---

In [Exploring Greek Syntax with Jupyter Notebooks](http://jonathanrobie.biblicalhumanities.org/blog/2017/12/08/jupyter-tutorial/) I presented [this tutorial](http://jonathanrobie.biblicalhumanities.org/assets/greeksyntax-tutorial.html), which queries [Lowfat syntax trees](https://github.com/biblicalhumanities/greek-new-testament) from [biblicalhumanities.org](http://biblicalhumanities.org/about/).  These syntax trees are derived from syntax trees produced by the [Global Bible Initiative](http://www.globalbibleinitiative.org), and most of the analysis was done by Randall Tan and Andi Wu, who were also responsible for the [Cascadia Syntax Graphs](https://www.logos.com/resources/CSGNTSBL/cascadia-syntax-graphs-of-the-new-testament-sbl-edition) used in Logos.

Dag Haug's [PROIEL Treebanks](https://github.com/proiel/proiel-treebank/) are the other major openly licensed treebank for the Greek New Testament, and it is a completely independent analysis, using a [different linguistic model and different annotation](http://folk.uio.no/daghaug/syntactic_guidelines.pdf).  It also contains some information not found in the Global Bible Initiative or Lowfat treebanks.  Obviously, it would be great to query these treebanks in roughly the same way so that we can compare results, but the models are significantly different.  Fortunately, it is not hard to convert treebanks from one format to another.  This is easiest when they are similar - for instance, converting from PROIEL to [universal dependency format](universaldependencies.org) is straightforward, though it loses some data.  But it is also possible to convert a dependency treebank to constituency and vice versa.

Once this is done, the PROIEL data can be queried much like the Lowfat data.  Here is a sample query and the results as they are shown in a scrollable window in a Jupyter notebook:

![A PROIEL Lowfat Query]({{ site.url }}/images/proiel-lowfat-query.png  "A PROIEL Lowfat Query")

In this post, I will start by introducing a tutorial oriented toward users, then give a brief overview of how the PROIEL data was converted for those who are interested in that level of detail.

# The PROIEL Lowfat `greeksyntax` Tutorial

I have written a tutorial for using the PROIEL Lowfat data in a Jupyter notebook with the `greeksyntax` module.  It assumes that you have already installed the environment described in [Exploring Greek Syntax with Jupyter Notebooks](http://jonathanrobie.biblicalhumanities.org/blog/2017/12/08/jupyter-tutorial/).  It also assumes that you have installed `proiel-lowfat.xml` in the database using the name `proiel-lowfat`.  Once you have done that, you can go ahead and run the tutorial named `greeksyntax-tutorial.ipynb` in the `greek-new-testament/labnotes` directory.

Because GitHub does not enable scrolling for checked-in notebooks, you cannot see the output in that notebook until you run it, so I have provided a copy that contains the output here:

- [Tutorial: Greek Syntax Queries using PROIEL Lowfat and Jupyter Notebooks](http://jonathanrobie.biblicalhumanities.org/assets/greeksyntax-tutorial-proiel.html).

For comparison, here is the original Lowfat tutorial and its output:

- [Tutorial: Greek Syntax Queries using Lowfat and Jupyter Notebooks](http://jonathanrobie.biblicalhumanities.org/assets/greeksyntax-tutorial.html).

# Converting PROIEL Treebanks to Lowfat

Let's look at part of Matthew 1:20.  Here is how it looks in the graphical representation of PROIEL:

![Matthew 1:20 PROIEL]({{ site.url }}/images/matt.1.20.proiel.png  "Matthew 1:20 in PROIEL")

That is generated from the following XML:

```xml
      <sentence id="47628" status="reviewed" presentation-after=" ">
        <token id="267082" form="τὸ" citation-part="MATT 1.20" lemma="ὁ" part-of-speech="S-" morphology="-s---nn--i" head-id="267086" relation="aux" presentation-after=" "/>
        <token id="267083" form="γὰρ" citation-part="MATT 1.20" lemma="γάρ" part-of-speech="Df" morphology="---------n" head-id="267089" relation="aux" presentation-after=" "/>
        <token id="267084" form="ἐν" citation-part="MATT 1.20" lemma="ἐν" part-of-speech="R-" morphology="---------n" head-id="267086" relation="adv" presentation-after=" "/>
        <token id="267085" form="αὐτῇ" citation-part="MATT 1.20" lemma="αὐτός" part-of-speech="Pp" morphology="3s---fd--i" head-id="267084" relation="obl" antecedent-id="267077" information-status="old" presentation-after=" "/>
        <token id="267086" form="γεννηθὲν" citation-part="MATT 1.20" lemma="γεννάω" part-of-speech="V-" morphology="-sappnn--i" head-id="267089" relation="sub" information-status="acc_gen" presentation-after=" "/>
        <token id="267087" form="ἐκ" citation-part="MATT 1.20" lemma="ἐκ" part-of-speech="R-" morphology="---------n" head-id="267089" relation="xobj" presentation-after=" ">
          <slash target-id="267086" relation="xsub"/>
        </token>
        <token id="267088" form="πνεύματός" citation-part="MATT 1.20" lemma="πνεῦμα" part-of-speech="Nb" morphology="-s---ng--i" head-id="267087" relation="obl" antecedent-id="267035" information-status="acc_gen" presentation-after=" "/>
        <token id="267089" form="ἐστιν" citation-part="MATT 1.20" lemma="εἰμί#1" part-of-speech="V-" morphology="3spia----i" relation="pred" presentation-after=" "/>
        <token id="267090" form="ἁγίου" citation-part="MATT 1.20" lemma="ἅγιος" part-of-speech="A-" morphology="-s---ngp-i" head-id="267088" relation="atr" presentation-after="·"/>
      </sentence>
```

Of course, we could simply query this directly, and I may explore that route in future posts. In the PROIEL format, words are represented as `token` elements, and the relationships among them are represented via numeric identifiers and references.  That means that some kinds of queries may require recursive algorithms, which I would like to avoid.  And it also means that queries on this native format will be hard to compare to queries on the Lowfat format. PROIEL provides a [Universal Dependency](http://universaldependencies.org) representation of their treebanks, which looks like this if displayed in [Arborator](https://corpling.uis.georgetown.edu/arborator/):

![Matthew 1:20 PROIEL]({{ site.url }}/images/matt.1.20.arborator.png  "Matthew 1:20 in Universal Dependency Format")

That diagram is generated from the following comma delimited file.

```csv
1   τὸ  ὁ   S   S-  NUMBs|GENDn|CASEn   5   aux _   _
2   γὰρ γάρ D   Df  INFLn   8   aux _   _
3   ἐν  ἐν  R   R-  INFLn   5   adv _   _
4   αὐτῇ    αὐτός   P   Pp  PERS3|NUMBs|GENDf|CASEd 3   obl _   _
5   γεννηθὲν    γεννάω  V   V-  NUMBs|TENSa|MOODp|VOICp|GENDn|CASEn 8   sub _   _
6   ἐκ  ἐκ  R   R-  INFLn   8   xobj    _   _
7   πνεύματός   πνεῦμα  N   Nb  NUMBs|GENDn|CASEg   6   obl _   _
8   ἐστιν   εἰμί#1  V   V-  PERS3|NUMBs|TENSp|MOODi|VOICa   0   pred    _   _
9   ἁγίου   ἅγιος   A   A-  NUMBs|GENDn|CASEg|DEGRp 7   atr _   _
```

And it is also possible to convert dependency treebanks like PROIEL to constituency treebanks like Lowfat and vice versa.  [This query](https://github.com/biblicalhumanities/greek-new-testament/blob/master/syntax-trees/xquery/proiel2lowfat.xquery) converts from PROIEL to the Lowfat format.  Here is the converted tree as it displays in Treedown:

![Matthew 1:20 PROIEL]({{ site.url }}/images/matt.1.20.proiel-lowfat.png  "Matthew 1:20 in PROIEL Lowfat Format")

That representation is created using a CSS stylesheet and the following XML, which is the result of our conversion:

```xml
  <sentence id="47628">
    <milestone unit="verse" id="Matt.1.20">Matt.1.20</milestone>
    <p>τὸ γὰρ ἐν αὐτῇ γεννηθὲν ἐκ πνεύματός ἐστιν ἁγίου·</p>
    <wg role="pred" head="267089">
      <w class="adverb" role="aux" lemma="γάρ" inflection="non-inflecting" n="267083" head-id="267089">γὰρ</w>
      <wg role="sub" head="267086">
        <w class="article" role="aux" lemma="ὁ" number="singular" gender="neuter" case="nominative" inflection="inflecting" n="267082" head-id="267086">τὸ</w>
        <wg role="adv" head="267084">
          <w class="preposition" role="adv" lemma="ἐν" inflection="non-inflecting" n="267084" head-id="267086">ἐν</w>
          <w class="pronoun" type="personal" role="obl" lemma="αὐτός" number="singular" person="third" gender="feminine" case="dative" inflection="inflecting" information-status="old" n="267085" head-id="267084">αὐτῇ</w>
        </wg>
        <w class="verb" role="sub" lemma="γεννάω" number="singular" gender="neuter" case="nominative" tense="aorist" voice="passive" mood="participle" inflection="inflecting" information-status="acc_gen" n="267086" head-id="267089">γεννηθὲν</w>
      </wg>
      <wg role="xobj" head="267087">
        <w class="preposition" role="xobj" lemma="ἐκ" inflection="non-inflecting" n="267087" head-id="267089">ἐκ</w>
        <wg role="obl" head="267088">
          <w class="noun" type="common" role="obl" lemma="πνεῦμα" number="singular" gender="neuter" case="genitive" inflection="inflecting" information-status="acc_gen" n="267088" head-id="267087">πνεύματός</w>
          <w class="adjective" role="atr" lemma="ἅγιος" number="singular" gender="neuter" case="genitive" degree="positive" inflection="inflecting" n="267090" head-id="267088">ἁγίου</w>
        </wg>
      </wg>
      <w class="verb" role="pred" lemma="εἰμί#1" number="singular" person="third" tense="present" voice="active" mood="indicative" inflection="inflecting" n="267089">ἐστιν</w>
    </wg>
  </sentence>
```

This representation uses word groups the same way as our Lowfat format, and converts PROIEL's `id` attributes to `n` attributes so that it works well with the `lowfat` module in the `greeksyntax` package.  It also maintains the original relationships that PROIEL represents using numeric ids and references so that these relationships can be queried directly.
