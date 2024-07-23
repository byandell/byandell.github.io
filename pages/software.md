---
layout: page
title: Software Projects
---

I began working on software in the 1970s as an undergraduate, both at Caltech and during
summer employment at UC-Berkeley Entomology (with [Bland Ewing](/pages/ewing)). I played around with [APL](https://xpqz.github.io/learnapl/), [Pascal](https://www.tutorialspoint.com/pascal/), [Fortran](https://fortran-lang.org/) and [Assembly](https://www.tutorialspoint.com/assembly_programming/assembly_introduction.htm) computer languages.
In one project, I redesigned the Pascal compiler to be able to insert Assembly code for fast computation.
UC-Berkeley had a CDC 6600 and a 7600 computer, which required users to stand in line with decks of computer cards (think one line of code per piece of cardboard, each fitting in a legal envelope).
Nevertheless, our team got access through early "high-speed" telephone wires to a computer each in San Francisco and UCLA.

Later as a graduate student at UC-Berkeley, my thesis involved a substantial computing part, along with high-end theory.
I happened to be in the same building with some of the designers of [4BSD Unix](https://en.wikipedia.org/wiki/History_of_the_Berkeley_Software_Distribution) and some of the popular early Unix tools.
Networking was rather rudimentary, with a colleague rigging a 2-wire connection between terminals to transfer coded between machines.
There were still only a few computers on campus,
with the new generation being [PDP-11 minicomputers](https://en.wikipedia.org/wiki/PDP-11). The UC-Berkeley CS and Stat departments shared a machine with 11 MB for each on a disk the size of a airport-friendly suitcase.
One day, I watched a colleage trash the [superblock](https://www.techopedia.com/definition/13376/superblock) of this computer, which lost all the pointers to computer file components. I helped him design tools (functions) to recover most of the files from the major crash.

My professor-track employment at UW-Madison involved a careful balance of theoretical work
(to establish my bonafides) and computational projects (to explore tools and ground ideas in data-driven stories). That is, I needed to write
theory papers to justify my tenure case, but managed to back up most of these with computer tools to justify the methodology.

I was actually stretched in a third, important way, through my career-long interest in collaboration. This has involved developing professional relationships with colleagues across campus, and around the world. While some of this work extends existing, or develops new, stats theory, many of my collaborations have involved more attention to the practical aspects of addressing challenging research questions through data analysis and visualization.
This work led to my book,
[Practical Data Analysis for Designed Experiments](http://www.stat.wisc.edu/~yandell/pda), along with a companion package, [pda](https://github.com/byandell/pda).

*   [R Software Introduction for Stat 571](https://www.stat.wisc.edu/~yandell/st571/R/)
*   [R Appendices for the Stat/For/Hort 571 Course Notes](https://www.stat.wisc.edu/~yandell/st571/R/append.html)
*   [Graphical Data Presentation with Emphasis on Genetic Data (R code for ASHS paper)](https://www.stat.wisc.edu/~yandell/talk/hort/2004.ashs/hort.r)
    
## Software Releases

*   [GCVPACK](ftp://ftp.stat.wisc.edu/pub/wahba/software/gcvpack.html): Routines for Generalized Cross Validation (free release in 1986; now part of base of [R](http://cran.r-project.org/); Bates, Lindstrom, Wahba and Yandell 1987)
*   [Splus/QDA](http://www.tragon.com/html/qda_-_news.html): Quality Data Attributes Analysis. (proprietary release in 1999; Yandell and Tragon Corporation).
*   [Practical Data Analsysis: library(pda)](http://www.stat.wisc.edu/~yandell/pda) for Splus and R. (free release in 1997; revised in 2000)
*   [Microarray Data Analysis: library(pickgene)](http://www.stat.wisc.edu/~yandell/statgen/software) for R. (2001; Lin et al. 2001)
[Bioconductor](https://doi.org/doi:10.18129/B9.bioc.pickgene)
*   [Quantitative Population Ethology: library(ewing](http://www.stat.wisc.edu/~yandell/ewing/) for R. (free release in 2001; Ewing et al. 2001)

### QTL Software

I have contributed to multiple
[quantitative trait loci (QTL)](https://en.wikipedia.org/wiki/Quantitative_trait_locus)
studies and software projects since the early 1990s.
In particular, I am a contributor to
[R/qtl](https://rqtl.org/)
and
[R/qtl2](https://kbroman.org/qtl2/),
both led by
[Karl Broman](https://kbroman.org/) with
[Saunak Sen](http://www.senresearch.org/),
and I have developed or co-developed multiple companion packages to these
widely used resources (see below).
I co-taught a QTL course with 
[Zhao-Bang Zeng](https://brcwebportal.cos.ncsu.edu/zeng/index.php)
and
[Chris Basten](https://www.linkedin.com/in/christopher-basten-8323678/),
and contributed insights and code to
[QTL Cartographer](https://brcwebportal.cos.ncsu.edu/qtlcart/).
In addition, working with
[Gary Churchill](https://www.jax.org/research-and-faculty/faculty/gary-churchill)
and
[Elias Chaibub Neto](https://www.linkedin.com/in/elias-chaibub-neto-a469913b/),
we developed various tests and packages for mediation analysis.

* [intermediate](https://github.com/byandell/intermediate):
Mediation analysis building on work of Gary Churchill team and
Elias Chaibub Neto.
See links under `qtl2mediate`, `qtlnet` and `qtlhot` below.
* [R/qtl](https://rqtl.org/) extensions
  * [R/qtlbim](https://cran.r-project.org/package=qtlbim):
  [QTL Bayesian Interval Mapping](https://pages.stat.wisc.edu/~yandell/qtl/software/qtlbim/).
  Improved and totally revamped R library for
  model selection with Bayesan interval mapping, allowing for covariates and
  epistasis.
  [CRAN](http://cran.r-project.org/) in 2006. [deprecated]
  * [R/qdg](https://cran.r-project.org/package=qdg):
  QTL-driven dependent graphs R library (CRAN 2008). [deprecated]
    * Chaibub Neto E, Ferrara C, Attie AD, Yandell BS (2008)
    Inferring causal phenotype networks from segregating populations.
    Genetics 179 : 1089-1100.
    [doi:10.1534/genetics.107.085167](http://doi.org/10.1534/genetics.107.085167).
  * [R/qtlhot](https://github.com/byandell/qtlhot): QTL Hotspot analysis.
    * Chaibub Neto E, Keller MP, Broman AF, Attie AD, Jansen RC, Broman KW, Yandell BS (2012) 
    Quantile-based permutation thresholds for QTL hotspots. Genetics 191 : 1355-1365. 
    [doi:10.1534/genetics.112.139451](http://doi.org/10.1534/genetics.112.139451).
    * Chaibub Neto E, Broman AT, Keller MP, Attie AD, Zhang B, Zhu J, Yandell BS (2013)
    Modeling causality for pairs of phenotypes in system genetics. Genetics 193 : 1003-1013.
    [doi:10.1534/genetics.112.147124](http://doi.org/10.1534/genetics.112.147124).
  * [R/qtlnet](https://github.com/byandell/qtlnet): QTL Network analysis.
    * Chaibub Neto E, Keller MP, Attie AD, Yandell BS (2010)
    Causal Graphical Models in Systems Genetics: a unified framework for joint
    inference of causal network and genetic architecture for correlated phenotypes.
    Annals of Applied Statistics 4: 320-339.
    [doi:10.1214/09-AOAS288](http://doi.org/10.1214/09-AOAS288).
* [R/qtl2](https://kbroman.org/qtl2/) extensions
  * [R/qtl2ggplot](https://cran.r-project.org/package=qtl2ggplot):
Visualize qtl2 objects with package `ggplot2`.
  * [R/qtl2fst](https://cran.r-project.org/package=qtl2fst):
  Fast access to genotype probabilities using [FST Package](https://www.fstpackage.org/).
  * [R/qtl2pattern](https://cran.r-project.org/package=qtl2pattern):
  Routines to investigate strain distribution patterns (SDPs).
  * [R/qtl2mediate](https://github.com/byandell/qtl2mediate):
  QTL mediation using  [intermediate](https://github.com/byandell/intermediate)
    * Chaibub Neto E, Broman AT, Keller MP, Attie AD, Zhang B, Zhu J,
    Yandell BS (2013)
    Modeling causality for pairs of phenotypes in system genetics.
    Genetics 193 : 1003–1013.
    [doi:10.1534/genetics.112.147124](http://dx.doi.org/10.1534/genetics.112.147124)
  * [R/qtl2shiny](https://github.com/byandell/qtl2shiny):
  Shiny app for fine-scale analysis and visualization.
* [DO Founder](https://www.jax.org/research-and-faculty/genetic-diversity-initiative/getting-started) Studies
  * [R/foundr](https://github.com/byandell/foundr):
  Package to analyze and visualize Diversity Outbred (DO) founder lines by sex
  and condition.
  * [R/foundrShiny](https://github.com/byandell/foundrShiny):
  Shiny app for `foundr` package.
  * [R/foundrHarmony](https://github.com/byandell/foundrHarmony):
  Data input and harmonization for `foundr` package.
  * [Foundr Shiny App Developer Guide](https://docs.google.com/presentation/d/171HEopFlSTtf_AbrA28YIAJxJHvkzihB4_lcV6Ct-eI)
* Miscellaneous QTL Packages
  *   [MCMC-QTL](ftp://ftp.stat.wisc.edu/pub/yandell/tr925r.html): Markov chain Monte Carlo inference for Quantitative Trait Loci. (free release in 1998; Satagopan, Yandell, Newton and Osborn 1996).
  *   [RevJump-QTL](ftp://ftp.stat.wisc.edu/pub/yandell/revjump.html): Bayesian model Determination of the Number of QTLs using Reversible Jump MCMC. (free release in 1999; Satagopan and Yandell 1998).
  *   [Bmapqtl](http://www.stat.wisc.edu/~yandell/qtl/software/qtlbim): Bayesian QTL mapping module for QTL Cartographer. (public domain release in 2001; Gaffney 2001)
  *   [R/bim](http://www.stat.wisc.edu/~yandell/qtl/software/qtlbim): Bayesian interval mapping R library. (free release in 2002; [CRAN](https://cran.r-project.org/package=qtlbim) in 2003; [Bioconductor](http://www.bioconductor.org/) in 2004. [deprecated]

