---
layout: post
title: "Minimal Pairs for Greek and Hebrew"
date: 2018-01-12 15:46
comments: true
external-url:
categories:
- Teaching Resources
---

When teaching the sounds of Greek or Hebrew, it would be helpful to have lists of words that differ by only one sound.  Most Americans remember learning how to spell our own language using lists like this in English:

```
bake cake
pan  pen
cat  cut
```

When I use apps that teach foreign languages, they sometimes use lists like this to teach the sounds of the language, so I [asked the B-Greek community](http://www.ibiblio.org/bgreek/forum/viewtopic.php?f=17&t=4308&p=29117#p29117) if they knew of a list of minimal pairs for English.

The next day, Dirk Roorda generated lists of word pairs for both Greek and Hebrew using [Levenshtein Distance](https://en.wikipedia.org/wiki/Levenshtein_distance) - for each pair (a, b), the Levenshtein distance is 1, which basically means that you could convert one into the other with a single insertion, deletion, or substitution.  He also posted [a Jupyter notebook](https://github.com/ETCBC/bhsa/blob/master/programs/minimalPairs.ipynb) with the code for his solution.

Here are a few examples for Greek:

```
ἄγε    ἄγω
ἄγω    ἄνω
ἄδηλος    ἄδολος
ἄλαλος    ἄναλος
```

Here are a few examples for Hebrew:

```
בְּ    כְּ
בְּ    כְּ
ברא    קרא
ברא    ברך
ברא    בוא
ברא    ירא
ברא    קרא
ברא    ברח
```

If you are a programmer who needs lists along these lines, but also need to taylor the results by word frequency, length, using a different distance metric, etc, you might want to start with [Dirk's notebook](https://github.com/ETCBC/bhsa/blob/master/programs/minimalPairs.ipynb) and modify it as needed.

If you are a teacher who wants to use these lists without installing software, you can find the output here:

- [Minimal Pairs for Greek]({{ site.url }}/assets/minimalPairsGreek.tsv)
- [Minimal Pairs for Hebrew]({{ site.url }}/assets/minimalPairsHebrew.tsv)
