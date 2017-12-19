---
layout: post
title: "Exploring Greek Syntax with Jupyter Notebooks"
date: 2017-12-08 15:46
comments: true
external-url:
categories:
- Treebanks
- greeksyntax package for Jupyter Notebooks
---

Imagine writing about Greek passages or Greek syntax in a document that lets you create headings and write text, automatically display passages, perform queries and show results in scrollable windows, perform statistical analysis, and create graphics based on your data. You could introduce a problem, display relevant data, describe your results in narrative text, and analyze it in the same environment. In the following image you can see text followed by a query, with the results of the query in a scrollable window:

![Syntax Notebook]({{ site.url }}/images/SyntaxNotebook.png "A Greek Syntax Query in a Jupyter Notebook")

This query was done using the `greeksyntax` package, which integrates the [Lowfat Treebanks](https://github.com/biblicalhumanities/greek-new-testament) into Jupyter - in the near future, I expect to provide additional resources in the same module.  I will describe this module later in this post and provide a pointer to a tutorial, but first I want to explain why notebooks are significant for biblical digital humanities.

# Notebooks and Open Science

In scientific computing and data science, notebooks are widely used for exploring data, experimentation, collaboration, and sharing results. Mathematicians, physicists, and engineers have been doing this since the 1980s using tools like [matlab](http://www.mathworks.com/), [Mathematica](http://reference.wolfram.com/legacy/v7/guide/NotebookBasics.html), and [MathCAD](https://www.ptc.com/en/products/mathcad).  I used MathCAD extensively in the early 1990s on a digital image quality project, and the project would have failed without it.

More recently, open source  notebooks like [Sage Notebook](http://www.sagenb.org/) and [Jupyter Notebooks](https://jupyter.org/) have become very popular in the data science community, and have become an important part of collaboration and open science [in a wide variety of domains](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks#natural-language-processing), including linguistics and text mining.

For researchers, notebooks provide an easy way to describe how they explore their research questions and their data, put it in context, provide access to the data itself, allow collaborators to confirm their findings, and allow others to build on their work.  Notebooks also provide a loosely coupled framework that can easily support a wide variety of resources even if they were not originally designed to be used together.  And notebooks are an excellent way to teach researchers how to work with data.

# Notebooks in Digital Humanities and Biblical Studies

This year, Jupyter Notebooks have been moving into biblical studies as well, particularly for Hebrew linguistics. [Dirk Roorda](https://github.com/ETCBC/bhsa/tree/master/programs), [Cody Kingham](https://github.com/codykingham/tfNotebooks), [Christiaan Erwich](https://github.com/cmerwich/participant-analysis), and [Martijn Naaijer](https://github.com/ETCBC/course_materials) have been using Jupyter Notebooks with Hebrew at the [Eep Talstra Centre for Bible and Computer](http://etcbc.nl/) at the Vrije Universiteit Amsterdam. At the 40th anniversary of the ETCBC, Cody gave a presentation on [Timex & Verb Associations in Biblical Hebrew](https://github.com/codykingham/Verb_in_Biblical_Hebrew/blob/master/data_analysis/time_phrase_analysis.ipynb) and Martijn gave a presentation on [The Hebrew copula, the use of HYH clauses and verbless clauses](https://github.com/MartijnNaaijer/HebrewCopula), both using Jupyter notebooks extensively.  After their presentations, Martijn and Cody showed me how to use Jupyter with ETCBC's Text Fabric.

At SBL 2017, Jupyter Notebooks were used in at least two presentations on the linguistics of biblical Hebrew. [Jarod Jacobs](https://warnerpacific.academia.edu/JarodJacobs) gave a presentation called [Adding Up the Numbers: A Statistical Visualization of the Linguistic Relationship Between Biblical Hebrew and Qumran Hebrew](https://www.academia.edu/35203176/Adding_Up_the_Numbers_A_Statistical_Visualization_of_the_Linguistic_Relationship_Between_Biblical_Hebrew_and_Qumran_Hebrew), and provided a link to [his data and code](https://www.academia.edu/35203246/Data_and_code_for_SBL_LBH_17_paper).

I came away from these two conferences believing that Jupyter Notebooks can play an important role in biblical digital humanities, and that Greek is about a year behind the Hebrew world.  And I thought it was time for Greek to start catching up.


# The `greeksyntax` Package

The `greeksyntax` package is a Python package designed for querying Greek morphology and syntax in the Jupyter environment. You can learn how to use it in this tutorial: [Tutorial: Greek Syntax Queries using Lowfat and Jupyter Notebooks](http://jonathanrobie.biblicalhumanities.org/assets/greeksyntax-tutorial.html). With this package, you can do queries based on chapter, book, verse, lemmas, morphology, and syntax.  Simple queries are simple, complex queries can use the full power of XPath or XQuery.  Results can be returned directly or in the context of the containing sentence (with results highlighted), in either plain text or HTML.  Creating a package like this is simple and straightforward&mdash;if you are a programmer, you can see the implementation [here](https://github.com/biblicalhumanities/greek-new-testament/tree/master/labnotes/greeksyntax).

# Installation

In the next few months, I hope to set up an environment where people can create Notebooks on the Internet without installing anything at all - see this discussion: [Setting up a public notebook environment](https://github.com/jupyter/help/issues/267). I'm currently focused on setting up the environment that I want to deploy, adding useful resources and trying out use cases.

But for now, you can install it like this:

- Get [the Git repo](https://github.com/biblicalhumanities/greek-new-testament), either using Git or as a zip file.  You will need both syntax trees and the labnotes subdirectory, which contains the tutorials as Jupyter notebooks.
- Install [BaseX](http://docs.basex.org/wiki/Startup)
- Start the BaseX GUI, import the resources you need, one per database.  If you want my tutorials to work out of the box, then import the Nestle1904 Lowfat Trees as a database named "nestle1904lowfat" and import the PROIEL Lowfat Trees as a database named "proiel-lowfat".
- Run the BaseX server, using default settings (that's what I use in the package right now).
- Install the BaseX client for Python:  `$ pip install basexclient`
- Install [Jupyter](https://jupyter.org/install.html).
- On the command line, go to the `greek-new-testament/labnotes subdirectory` and run Jupyter. It is (currently) important to run Jupyter from this directory because the `greeksyntax` package is in the `greek-new-testament/labnotes/greeksyntax` subdirectory.

```bash
$ cd ~/git/greek-new-testament/labnotes
$ jupyter notebook greeksyntax-tutorial.ipynb
```

This will open the notebook in your default browser.  From the `Kernel` menu, select `Restart and run all`:

![Syntax Notebook]({{ site.url }}/images/restart-and-run-jupyter.png  "Restart and run all")

If you have correctly installed everything, you will see output beneath each query.  If you have not, you will see error messages.

# Watch this space ...

In the coming months, I intend to show some scenarios that illustrate how to use this environment for exploring specific aspects of Greek passages or the Greek language. Over time, I expect to provide additional resources in this package, drawing from packages in the [biblicalhumanities.org dashboard](http://biblicalhumanities.org/dashboard/).
