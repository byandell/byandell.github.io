---
layout: page
title: Correlation and Design
---

Correlation among measurements (traits) is useful, particularly when there are many of them, to finds groups of related traits. The goal is some sort of dimension reduction. A great tool for this in genomic studies at scale is [WGCNA](https://horvath.genetics.ucla.edu/html/CoexpressionNetwork/Rpackages/WGCNA/), which provides visual summaries and convenient grouping of traits.

However, the danger of examining correlation when there is some population admixture, such as from a genetic cross or an experimental design, is that the correlation may be due to the driver of interest (say genetics or diet) or due to unrelated environmental co-variation. 
[Korol et al. (2001) Figure 1](https://doi.org/10.1093/genetics/157.4.1789) illustrates this nicely. That is, the observed raw correlation may be spurious.

![Korol Figure 1](https://academic.oup.com/view-large/figure/325609537/GEN9824.f1.jpeg)

In a genetic population, say of DO mice, correlation might seem ideal to prioritize traits, but it still has the danger identified by Korol's team. That is, if there is one genetic driver (QTL), that splits the data into 2 (or 3) sets similar to Figure 1. Add to that a diet study, and sex effects, and it gets more complicated (with more ellipses). A diet study with founder strains will have the same issue, but more so as the environmental correlation concerns the replicates while the design factors (strain, diet, sex) drive their own form of "design correlation".

There are several possible ways to approach association among traits in a designed experiment besides relying on raw correlations and filtering post hoc. For two traits, one can do analysis of covariance ([ANCOVA](https://www.r-bloggers.com/2021/10/analysis-of-covariance-ancova-using-r/)), which considers factors and the continuous relationship; for Figure 1, we have slopes for each ellipse (may or may not be parallel), and the separation of the ellipses. While ANCOVA is conceptually asymmetrical, as is regression, it can be interpreted in terms of co-variation. The trick here is to be clear on what is the key question, such as do the two traits see the same diet pattern across strains? That will guide how one uses ANCOVA at scale (all pairs of traits) to prioritize.

A related approach is multivariate ANOVA ([MANOVA](https://www.reneshbedre.com/blog/manova.html)) in which one aims to relate a set of traits to explanatory variables (again, strain, diet, sex). This will also take some care in how to frame questions and build tools.

Another related method is [clustering](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6634702/), which is used in WGCNA. The challenge is how to incorporate the experimental design into study of the association among traits. See Galbraith et al. (2010) for some ideas.

# Signal and Noise

Lets first recognize that a trait measurement consists of signal and noise. When considering correlation across traits, we hope to find traits that have correlated signals, with the noise being a nuisance. If the noise is minor, than correlation among traits essentially focuses on correlation among signals, with some slight attenuation. Here is some brief math:

<div align="center">
`trait value = signal + noise,`
</div>

with signal and noise uncorrelated. Thus the variance can be decomposed as

<div align="center">
V<sub>T</sub> = V<sub>S</sub> + V<sub>N</sub> .
</div>

The covariance with another trait, say X, can be decomposed into

<div align="center">
C<sub>T,X</sub> = C<sub>S,X</sub> + C<sub>N,X</sub> .
</div>

Again, the covariance of the trait with X is attenuated by the noise, which may increase or decrease covariance. So, the trick is to isolate the signal and consider covariances (and correlations) involving this quantity.

Two more considerations are important. The noise is the unexplained variation, or the variation you would see in a population where there is no signal. In our case, that corresponds to a population of like individuals, and the variation V<sub>N</sub> as well as the covariation C<sub>N,X</sub> would address (co)variation in a uniform population. That is, how do the traits co-vary in a common population? This is relevant to studying internal processes, but not to addressing how the signal changes the relationship.

The other consideration is that the signal may be accompanied by other terms, such as differences by sex or diet on their own. Further, if the trait is measured over multiple populations that are mixed together -- say from different locations or different genetic crosses -- then there there could be admixture that has design implications. Thus it is useful to consider a slightly expanded model

<div align="center">
`trait value = cellmean + noise = signal + rest + noise`,
</div>

with signal, rest and noise uncorrelated. The variance can be decomposed as

<div align="center">
V<sub>T</sub> = V<sub>S</sub> + V<sub>D</sub> + V<sub>N</sub> .
</div>

The covariance with another trait, say X, can be decomposed into

<div align="center">
C<sub>T,X</sub> = C<sub>S,X</sub> + C<sub>D,X</sub>  + C<sub>N,X</sub> .
</div>

Again, the covariance of the trait with X is attenuated by the rest and the noise effects, which may each increase or decrease covariance. Again, being able to isolate signal from rest and noise effects will enable more useful covariance (and correlation) studies.

Isolation of signal comes from the following two regression steps:

* regress trait T on rest factors to create residuals (N)
* regress residuals (from rest factors) on signal factors
    * the predicted values will be the estimated signal effect (S) adjusted for rest factors
    * the residuals from this second fit will be the estimated rest effect (D)

It can be verified that S, D and N are uncorrelated, they add up to T, and that their empirical variances add up to empirical variance of T. This provides an easy way to construct the signal as uncorrelated from rest and noise effects. If all the signal and rest factors are discrete, as is the case in our study, then S will include repeats, and it will make sense to reduce to distinct values for the actual correlation study.

In a situation comparing strains with possible sex effects, the focus should be away from sex-only effect. Thus the following partition useful:

* `cellmean = strain:sex + strain + sex = signal + rest`
* `signal = strain:sex + strain`
* `rest = sex`

Operationally, the steps above become:

* `fit1 <- lm(trait ~ sex)`
* `rest <- predict(fit1)`
* `resid <- resid(fit1)`
* `fit2 <- lm(resid ~ strain*sex)`
* `signal <- predict(fit2)`
* `noise <- resid(fit2)`

One can verify that for each trait, `value = signal + rest + noise` and empirical variances and covariances add up appropriately.

For a more complicated situation with strain, diet and sex, it makes sense to focus the signal on terms involving `strain:diet `interactions. [It could be argued to also include the main effect of `strain` in the signal, but the focus of study is really on `diet` effects.] That is, how do strains respond differently to diet? That would make the following partition useful:

* `cellmean = signal + rest`
* `signal = strain:diet + strain:diet:sex`
* `rest = strain + diet + sex + strain:sex + diet:sex`

Operationally, the steps above become:

* `fit1 <- lm(trait ~ strain*diet + sex*diet)`
* `rest <- predict(fit1)`
* `resid <- resid(fit1)`
* `fit2 <- lm(resid ~ strain*diet*sex)`
* `signal <- predict(fit2)`
* `noise <- resid(fit2)`

Again, one can verify that `trait = cellmean + noise = signal + rest + noise` and that empirical variances and covariances add up appropriately.

# Mediation

Mediation has been used for QTL studies, but can also be used for founder studies. The idea is that one supposes there is a genomic region (QTL = quantitative trait loci) corresponding to some DNA segment that influences some biomolecular activity, in turn ultimately affecting some physiological trait. For the founders, we cannot assess the genomic region directly, but we can assess the relationship with measured RNA, either corresponding to a gene, or an isomer of that gene. We may consider different types of measured biomolecules, but let's start with metabolites. In our situation, we have liver RNA (LivRna) and liver metabolites (LivMet). The proposed model might be

<div align="center">
`QTL -> LivRNA -> LivMet`
</div>

The QTL would measure a differential effect of genetics on different diet background. The main thing we can examine in the founder is the `strain:diet` interaction, possibly modified by `sex` (combined and referred to above as `signal`). We do this via analysis of covariance, such as

<div align="center">
`LivMet ~ LivRNA + signal + rest (3)`
</div>

The question is whether or not `LivRNA `explains the `signal`. That is, we compare the model above to

<div align="center">
`LivMet ~ LivRNA + rest (4)`
</div>

We can also compare this to the model without the covariate:

<div align="center">
`LivMet ~ signal + rest (1)`
</div>

Finally, there is the model without signal or covariate

<div align="center">
`LivMet ~ rest (2)`
</div>

The p-value for signal (`p_signal`) compares models (1) and (2). Mediation would roughly compare models (3) and (4), say with p-value `p_mediator`. If `p_mediator `is much larger than `p_signal`, we would conclude that `LivRNA `mediates the `signal`. In a sense this involves comparing all four models, and can be formalized with a causal model selection test (Chaibub Neto et al. 2011 or so). This could be visualized with a plot of p-values against the genomic position of the RNA traits. Only those traits with significant signal, in the sense of

<div align="center">
`LivRna ~ signal + rest (5)`
</div>

vs

<div align="center">
`LivRna ~ rest (6)`
</div>

would be formally compared; that is, restrict to `LivRna `with `p_signal `<= 0.05, say. See [LivRNA Case Studies](https://docs.google.com/document/d/1XarvkCVYMywZf6bzG_Od6LXZROe6qhufL_2ppiwaZak).

## References

[WGCNA: R package for performing Weighted Gene Co-expression Network Analysis](https://horvath.genetics.ucla.edu/html/CoexpressionNetwork/Rpackages/WGCNA/)

Nicholas A. Furlotte and Eleazar Eskin (2015) [Efficient Multiple-Trait Association and Estimation of Genetic Correlation Using the Matrix-Variate Linear Mixed Model](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4423381). Genetics 200: 59–68. [https://doi.org/10.1534/genetics.114.171447](https://doi.org/10.1534/genetics.114.171447)  

 

Korol A., Ronin Y., Itskovich A., Peng J., Nevo E. (2001) Enhanced efficiency of quantitative trait loci mapping analysis based on multivariate complexes of quantitative traits. Genetics 157: 1789–1803. [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1461583/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1461583/) 

Sally Galbraith, James A. Daniel, and Bryce Visselcorresponding (2010) A Study of Clustered Data and Approaches to Its Analysis. J Neurosci. 30: 10601–10608. [https://doi.org/10.1523/JNEUROSCI.0362-10.2010](https://doi.org/10.1523/JNEUROSCI.0362-10.2010) 
