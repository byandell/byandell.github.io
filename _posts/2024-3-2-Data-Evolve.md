---
layout: post
title: Data Evolve
---

The noun [data](https://en.wikipedia.org/wiki/Data) implies it is somehow static. However, data evolve in multiple ways.
I started thinking about how data evolve in our lives as a verb when I met
[Jhon Goes-in-Center](https://thebrintonmuseum.org/jhon-duane-goes-in-center-2020-brinton-101/)
at the
[Exploring Data Sovereignty Workshop](https://ncar.ucar.edu/exploring-data-sovereignty-workshop) in Feb 2024.
He was musing on how difficult it is to understand the noun `data` when his Lakota language is woven with verbs. Later, when we were looking out at the huge cottonwood trees surrounding the
[hogan](https://www.sipi.edu/pdf/SIPI_Campus_Map.pdf)
where we were meeting, he talked about how everything is related by `evolution`--how these very trees have evolved to be successful in this seemingly dry land just a short walk from the Rio Grande River.

- data evolve through collecting anew and extant data editing
- data evolve in context of changing metadata and harmonizing to clean data
- measurement tools evolve, which change precision and focus, altering meaning
- methods to examine data evolve insights through summaries and visualizations
- questions about data evolve as the broader context changes
- "small data" augmented by "Big Data" evolve our ability to ask questions

One `datum` (a single piece of data) may not change, but everything around it may, and hence its importance and value may change. A datum to one person or situation may be a world of data to another--consider a painting, which to one person may represent a single datum in a collection, such as current owner, while to another person may contain a rich history of technique, setting, artist, and
[provenance](https://www.nnlm.gov/guides/data-glossary/data-provenance).

## Software Evolves

Much earlier, in Fall 2017, I wrote a living (evolving) document as a guide for the language
[R for teams in the data sciences](https://github.com/UW-Madison-DataScience/R_for_data_sciences).
I organized it as a series of verbs--curate, visualize, organize, analyze, profile, and connect--to emphasize how to think about examining data with such a language.
About that time, I and others were asking,
[What is Data Science?](/What-is-Data-Science/)
Interestingly, `science` is also a noun.
[What is Science?](https://undsci.berkeley.edu/understanding-science-101/what-is-science/),
a 101-level explanation from UC-Berkely, points out that science is both a body of knowledge (noun) and a process (verb) of studying the world.
Science is very much verb-driven, as is the incorporation of data science into science to make sense of complex patterns and relationships.

Someone once told me that
[software rots](https://towardsdatascience.com/why-and-how-software-systems-decay-fa7ec83c4ff3).
That is, software/code cannot be static, or it becomes irrelevant as the computing system, data and context around it evolve.
I once heard Daryl Pregibon, one of the incredible team at Bell Labs that developed
[C](https://en.wikipedia.org/wiki/C_(programming_language))
and
[S](https://en.wikipedia.org/wiki/S_(programming_language)),
precursors to
[R](https://www.r-project.org/)
and many other language systems, who stated (paraphrased from memory),
"We used to be able to provide an equation, then an algorithm, and later a string of code perhaps organized as a function. Later we found it useful to organize code into a package, say to use in a system like R or S.
This was useful for fellow statisticians, but often didn't reach our
collaborators effectively.
So we developed standalone widgets to share with colleagues."
See for instance
[Daryl Pregibon: "Incorporating statistical expertise into computer software"](https://www.youtube.com/watch?v=8h96LgVpUrI)
talking at the Second International Tampere Conference in Statistics (1987),
later published in the
[1991 Future of Statistical Software National Academies report](https://nap.nationalacademies.org/catalog/1910/the-future-of-statistical-software-proceedings-of-a-forum).
[Roger Peng (2013) (Back to) The Future of Statistical Software](https://simplystatistics.org/posts/2013-10-25-back-to-the-future-of-statistical-software-futureofstats/)
provides a short critique of this volume and Pregibon's chapter.

Now there is recognized value in web-based apps, such as
[Shiny apps](https://shiny.posit.co/r/gallery/)
that in their simplest form can be created in a few minutes or hours.
More complicated platforms have emerged, such as
[Galaxy](https://galaxyproject.org/)
and
[Ramadda](https://ramadda.org/),
that enable teams to collaboratively share data and code, possibly with
protections to respect
[data sovereignty](/Data-Sovereignty/).
This begs the question of emerging tools and platforms for AI, notably 
[large language models (LLMs)](https://medium.com/data-science-at-microsoft/how-large-language-models-work-91c362f5b78f).

## Learning from Data with R

The organic process of learning from data while developing useful study tools might be somewhat planned in advance, but typically, for me,
evolves based on insights and
[collaboration](/pages/collaborate/)
along the way.
Good collaboration includes documenting at every step, including notes on what is still
broken and what is hoped for future development.
Some of this is written for collaborators, but much is for my "future self"
so that I can recall my strategy and challenges along the way.

Consider a data project that benefits from software scripting (that is, most data projects),
here illustrated with the
[R language system](https://www.r-project.org/about.html).
My involvement is usually organic, starting with a few lines of code, developing likely into an
[R markdown document](https://rmarkdown.rstudio.com/)
that enables me to document my ideas and present visualizations, and even share results with others.
As the project develops, some code gets reused and is better organized as a
[function](https://www.sciencedirect.com/topics/computer-science/software-function).
Eventually, those functions get organized into a folder.
Ideally, each function of import is documented, say in R using
[Roxygen2](https://kbroman.org/pkg_primer/pages/docs.html).
As the collection of functions grow, it may be useful to organize them into an
[R package](https://cran.r-project.org/doc/manuals/R-exts.html),
particularly if I am using them for more than one project.
Typically, both for safety and sharing, it is helpful to put packages online, often in
[GitHub](https://happygitwithr.com/);
then others may view or use them as well.
Some projects have broader appeal and longevity, leading to submission to an archive such as
[CRAN](https://cran.rstudio.com/).

## Blending R and Python to Leverage Data

The
[Environmental Data Science Innovation & Inclusion Lab (ESIIL)](https://esiil.org/)
has the ambitious goal of "Enabling an inclusive community of practice to leverage the wealth of environmental data for challenges in the environmental sciences".
That is, guide communities to use data at scale with online tools, particularly for geospatial but also for lots of other types of data. I have gotten involved in this
[environmental data science](/pages/eds/) center
for a variety of reasons. Last week (March 22, 2024) I attended a virtual training session with two Tribal colleges where I learned a great deal (see my notes on python in
<https://github.com/byandell/geospatial/>).
The following is based on follow-up conversations.

### Compute platform

- The session last Friday used
[CoLab](https://colab.research.google.com/),
which seems to be an intuitive tool from google for python. ESIIL set up an
[empty python notebook](https://colab.research.google.com/drive/1ZuzbG74DIqRibNtyyylYLbcZo8aTwmIB)
that overcame the hassles of configuring your own laptop.
- ESIIL is also using the
[Cyverse Discovery Environment](https://cyverse.org/discovery-environment), which supports R/Rstudio as well as version of Jupyter Notebook and a Linux command line interface. Cyverse is a heavier lift, particularly for an intro.

### Language choice

- Generic scripting languages (say R or Python) are your (and my) way to customize how we play with data. They give us local control of how we use our understanding of a project to make a story from data, which might include available data from NSF or NASA or other sources, possibly along with our own sovereign data.
- R and Python were designed for different purposes—R for data and statistical analysis, Python for computing at scale—so they naturally have different strengths and weaknesses. 
- R can be quite slow, but should not be dismissed as such. It can be lightning fast. It takes a mix of art and careful choice of methods and add-on packages. A key area involves
[for loops](https://bookdown.org/content/d1e53ac9-28ce-472f-bc2c-f499f18264a3/loops.html),
where judicious use of apply and
[parallel approaches](https://dept.stat.lsa.umich.edu/~jerrick/courses/stat701/notes/parallel.html)
can greatly improve speed. The apply tools in R are actually quite old, largely supplanted by cool, new tools in the
[tidyverse](https://www.tidyverse.org/packages/).
-	Here are some comparisons of R and Python quickly gleaned via search, which capture some of the essence:
    +	[R vs Python: Which Is Best 2024?](https://www.turing.com/kb/best-programming-language-for-data-science-r-vs-python)
    +	[R vs. Python: 12 Key Comparisons](https://www.spiceworks.com/tech/devops/articles/r-vs-python/)
    +	[R vs Python: Key Differences](https://blog.jetbrains.com/datalore/2022/11/15/r-vs-python-key-differences/)
    +	[Python vs R 2023: Which is better?](https://www.projectpro.io/article/data-science-programming-python-vs-r/128) 
    +	[Question for office hour: R vs Python](https://forum.posit.co/t/question-for-office-hour-r-vs-python/135/3)

### Working environment

- I personally find
[Rstudio](https://posit.co/download/rstudio-desktop/)
more intuitive than a
[Jupyter notebook](https://jupyter.org/).
You can actually do R or Python in either these days, and share data between them in the same document with care.
- [Rmarkdown](https://rmarkdown.rstudio.com/)
is great for developing and documenting one’s data story, and later turning that into a separate, refined document. Again, one can use python and linux code in Rmarkdown code chunks.
- [Quarto](https://quarto.org/) seems to have the benefits of Rmarkdown with the flexibility to switch between source and rendered document. It is also newer technology. I have not really explored this much yet.

### Personal choice

Yeah, we all have feelings about this stuff, and we have our comfort levels. There seems to be a lot of ambiguity and overlap, which makes it so one size does not fit all. But hey, that gives us opportunity to do what we want. Sort of reminds me of the emotional battles over frequentist and Bayesian approaches to statistics decades ago—that seems to have settled into a blended approach these days, where we now have the data and computing resources to learn from data in context of (partially) parametric models.

## Beyond Data to Broader Communications

Software is itself a type of data, and data carry us along the path from
ignorance to wisdom (see
[Clifford Stoll quote](/Useful-Data-Science-Quotes/)).
But software is used for many things beyond computation and data analysis.

Software, of course, is used to write articles and books.
I am working on a book
[Quantitative Population Ethology](https://connect.doit.wisc.edu/qpe/)
that is written in
[Bookdown](https://github.com/rstudio/bookdown-demo)
and hosted on the
[UW-Madison campus Connect server](https://connect.doit.wisc.edu/)
(part of the
[Data Science Platform](https://researchci.it.wisc.edu/data-science-platform/))
with source at
[GitHub](https://github.com/byandell/ewing_book).
The connect server uses
[Posit’s continuous integration](https://docs.posit.co/connect/admin/appendix/ci/)
so that when I update GitHub, the book on Connect is soon updated.
Notice in particular equations in
[section 5.7 on competing risks](https://connect.doit.wisc.edu/qpe/event.html#competing-risks-for-life-events)
(see
[chapter 5 source](https://github.com/byandell/ewing_book/blob/main/05-event.Rmd)). Chapters are written in
[Rmarkdown](https://rmarkdown.rstudio.com/)
using
[MathJax](https://www.mathjax.org/)
to invoke
[LaTeX](https://www.latex-project.org/).

This blog is part of my personal website <https://byandell.github.io>,
which is largely written in markdown with source at <https://github.com/byandell/byandell.github.io>.
Fork this repo (or the original at <https://github.com/barryclark/jekyll-now>) and make your own.
Slide decks can also be software,
and can be hosted online, such as
Srikanth Aravamuthan's Posit Day slides
<https://connect.doit.wisc.edu/posit-day/>.

Nowadays, I continue to rely on the lessons I learned building that guide and various projects in my
[GitHub repositories](https://github.com/byandell),
including this web site
[byandell.github.io](https://github.com/byandell/byandell.github.io).
I now think more about how
[teams](/pages/team/)
evolve their relationship with data,
and their relationship with tools to make sense of data.
Data is really about people and about how we form our data-informed stories,
much in the way
[Jaron Lanier](/Jaron-Lanier-There-is-no-AI/)
thinks about AI.

## Resources

* [What is Science?](https://undsci.berkeley.edu/understanding-science-101/what-is-science/)
* [What is Data Science?](/What-is-Data-Science/)
  * [Data -- Wikipedia](https://en.wikipedia.org/wiki/Data)
  * [Data Sovereignty](/Data-Sovereignty/)
  * [Data Provenance](https://www.nnlm.gov/guides/data-glossary/data-provenance)
  * [Data Literacy](https://data.wisc.edu/data-literacy/)
  * [Research Data Management](https://learn.library.wisc.edu/research-data-management/)
  * [Researcher Toolkit](https://researchertoolkit.wisc.edu/)
  * [Research Data Services](https://researchdata.wisc.edu/)
* [Why Software Rots](https://towardsdatascience.com/why-and-how-software-systems-decay-fa7ec83c4ff3)
* [R language system](https://www.r-project.org/about.html)
  * [R for teams in the data sciences](https://github.com/UW-Madison-DataScience/R_for_data_sciences)
  * [R markdown document](https://rmarkdown.rstudio.com/)
  * [Documenting R functions (Roxygen2)](https://kbroman.org/pkg_primer/pages/docs.html)
  * [Writing R Extensions (packages)](https://cran.r-project.org/doc/manuals/R-exts.html)
  * [Comprehensive R Archive Network (CRAN)](https://cran.rstudio.com/)
  * [Shiny apps](https://shiny.posit.co/r/gallery/)
* [GitHub](https://github.com/)
  * [HappyGit](https://happygitwithr.com/)
  * [Dangit Git](https://dangitgit.com/en)
* Extensible Work Environments
  * [Posit Team](https://posit.co/products/enterprise/team/): [Workbench](https://posit.co/products/enterprise/workbench/) & [Connect](https://posit.co/products/enterprise/connect/)
  * [Galaxy](https://galaxyproject.org/)
  * [Ramadda](https://ramadda.org/)
  * [Cyverse Open Science Workspace](https://cyverse.org/)
* [Large Language Models (LLMs)](https://medium.com/data-science-at-microsoft/how-large-language-models-work-91c362f5b78f)

_Updated March 22-25, 2024._


