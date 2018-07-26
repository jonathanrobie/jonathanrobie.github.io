---
layout: post
title: Needed - An Open, Trustworthy, Trusted Greek Text
date: 2018-07-24 15:46
comments: true
external-url:
categories:
    - Open Data
---

The Bible is at the heart of digital biblical humanities, and open scholarship depends on an open text that can be used in scholarly publications and translations.  For the Greek New Testament, the critical editions that can be used in scholarly publications and most translations are not open.  The texts that are open are generally not considered acceptable for scholarly publications or translation.

Something's got to give.  Open scholarship requires a text that is trustworthy, trusted, and openly licensed:

- **Trustworthy** We need a text that is good enough to be trusted, based on rigorous scholarship and a good understanding of textual criticism.
- **Trusted** We need a text that is actually trusted in the communities we serve, including academic research and Bible translation.
- **Openly Licensed** We need to be able to create [derivative works](https://en.wikipedia.org/wiki/Derivative_work) that analyze the text in various ways and use them freely without the overhead of legal negotiation.

A resource is freely licensed if the license permits free use, reuse, modification, and sharing with others. Free resources [enable creativity and research](http://copenhagen-alliance.org/why-free.html) using well-known, clear licenses.

> Freely licensed resources can be used without contacting and negotiating with the copyright holder. That way, creators can focus on doing their work, using and building on the resources according to the terms of use spelled out in standard licenses.

Free resources are at the heart of open scholarship.

Most academic publications and translations are based on the UBS/Nestle-Aland text, which is not freely licensed. This text is both trustworthy and widely trusted, but its licensing restrictions affect any derivative works, including translations and any analysis that incorporates the text itself, e.g. morphologies, syntax trees, or discourse analyses.  If you create an analysis of the text, it is constrained by the text's license.

This is a major stumbling block for open scholarship in biblical studies. We can only have open scholarship for the Greek New Testament if we have an open Greek New Testament that scholars can use.

## Hebrew has Trustworthy, Trusted, Openly Licensed Texts

For Hebrew, the [Westminster Leningrad Codex](http://www.tanach.us/Tanach.xml) fills this need nicely, and the [Biblia Hebraica Stuttgartensia](https://github.com/ETCBC/bhsa), which differs by only about a dozen consonants and another dozen vowel or pointing differences, is freely licensed for non-commercial use.

## Workarounds in the Open Greek Community

Because there is no truly free text that is generally acceptable for scholarly work, the open data community has been forced to use various workarounds.

Some open-source projects  are based on the Nestle-Aland but strip out the text itself before publishing to avoid copyright restrictions, even though their work is an analysis of the very text they are forced to strip out (e.g. [OpenText](https://github.com/OpenText-org)).

Other projects choose a text that is open but not generally used in the research or translation communities. Until recently there were few reasonable choices, but the number of reasonable possibilities has grown quite a bit:

- The [SBLGNT](http://sblgnt.com/) was originally designed to enable open scholarship but has significant [licensing issues](http://sblgnt.com/license/) of its own - the license does not even address noncommercial use or creation of derivative works, the official route for permissions and licensing involves sending physical mail and waiting for a response in some unspecified time frame, and commercial use requires sales reporting that has prevented Logos competitors from using it.
- The [Nestle 1904](https://github.com/biblicalhumanities/nestle1904/) is the text that made Nestle's reputation, and some consider it quite good. Older critical texts can be quite good, but are often not trusted because they do not reflect the latest scholarship.
- The [Robinson-Pierpoint](https://github.com/byztxt/byzantine-majority-text) is a freely-licensed, high-quality Byzantine critical text. Few modern translations or academic publications now use a Byzantine text, which is out of favor with much of the academic community.
- The [Bunning Heuristic Prototype](https://github.com/greekcntr/BHP) is a critical text generated algorithmically from all texts before AD 400 by Alan Bunning. It differs from the Nestle-Aland 28 in about 500 places, so it is quite similar.
- The [TANTT (Tyndale Amalgamated NT Tagged texts)](https://github.com/tyndale/STEPBible-Data) was "created from the SBLGNT+apparatus, following the decisions made by NA27, listing the major editions that also use that form (SBL, Treg, TR, Byz, WH, NA28)". The result is a text that is a word-for-word equivalent to the Nestle-Aland 27, but with differences in spelling, capitalization, punctuation, paragraphs, etc.  That makes it very easy to port resources created for Nestle-Aland 27 to this edition.
- The [Open Greek New Testament Project](https://github.com/eliranwong/OpenGNT) is a similar text designed to be word-for-word equivalent to the Nestle-Aland 28.

There are currently open-source projects based on each of these texts, often creating the same kinds of resources that exist for another text. Many of us find ourselves porting resources from one text to another, but this is complex and time-consuming if the texts differ much at all, especially for complex analyses like syntax trees or discourse analysis.  I would love to support every openly licensed critical edition, but porting some of these resources can take months.

Other projects are simply stripping out the Greek text from their analyses in order to be able to publish without violating the licenses of copyright holders.  And some projects are simply violating these copyrights, which is clearly illegal.

## Something's Got to Give

We need to build a digital humanities community around a Greek text that is openly licensed and accepted for academic work and translation.  There are now quite a few projects creating high quality open resources for the Greek text, but no openly licensed Greek text to use with them.  And there is more and more pressure to fix this problem.

There are several possible ways forward.

- One of the copyright holders for an existing scholarly critical edition could choose to license their work openly, at least for non-commercial use. The Nestle-Aland, SBLGNT, or Tyndale House Greek New Testament might be suitable candidates.
- The scholarly community could agree that one of the existing openly-licensed critical editions is suitable for scholarly use and translation.
- A new critical edition could be created and licensed openly under supervision of a solid text-critical scholar.

Until one of these things happens, we will continue to limp along with the work-arounds I described earlier.  But as more and more people are doing this work, the pain of approaching it this way becomes obvious, and the pressure to find or create an open text for scholarly study continues to build.

And this is becoming increasingly obvious to some people who may be in a position to do something about it.
