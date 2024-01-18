---
layout: page
title: Correlation and Design
---

We consider two related situations that arise in systems genetics with multi-parent (MAGIC) populations (Cavanagh et al. 2008). One may study the individuals from the founder `strain`s or individuals derived from the MAGIC population, which are derived from founder strains through a multiple generations of crossing. In particular, we illustrate with the Diversity Outbred (DO) (Bogue et al. 2015) mice population derived from 8 founder straits. Below we refer to Founder and DO studies, respectively.

We further consider the complication that individuals may be of different `sex`s, and there may be a treatment condition, such as `diet`. Founder studies typically have replicate individuals of the same `strain`, `sex`, and `diet`, while DO studies have geneticially unique (_not_ identical replicates) individuals in groups by `sex` and `diet`.

## Spurious Correlation

Correlation among measurements (traits) is useful, particularly when there are many of them, to finds groups of related traits. The goal is some sort of dimension reduction. A useful tool for this in genomic studies at scale is [WGCNA](https://horvath.genetics.ucla.edu/html/CoexpressionNetwork/Rpackages/WGCNA/), which provides visual summaries and convenient grouping of traits.
However, the danger of examining correlation when there is some population admixture, such as from a genetic cross or an experimental design, is that the correlation may be due to drivers of interest (say `strain` or `diet` or `sex` or their combination) or due to unrelated environmental co-variation. 

Korol et al. (2001) illustrates this nicely in [Figure 1](https://academic.oup.com/view-large/figure/325609537/GEN9824.f1.jpeg) for two traits $x$ and $y$. If we think of this as grouping, say by `sex`, then the within-`sex` correlation may be quite different from the raw correlation (ignoring `sex`). It is possible (Figure 1a) to have no correlation within sex but a negative raw correlation ignoring `sex`, which is spurious. Conversely, there may be strong correlation within `sex` but no correlation when `sex` is ignored (Figure 1c), which is also spurious.

In a genetic population of DO mice, correlation might seem ideal to prioritize traits, but it still has the danger identified by Korol's team. That is, a genetic driver, such as a QTL, splits the data into several groups based on `strain` distribution pattern (SDP, similar to Korol's Figure 1. Add to that a `diet` study, and `sex` effects, and it gets more complicated (with more ellipses). 

A founder `diet` study will have the same issue, but more so as the environmental correlation is across replicate subjects while the design factors (`strain`, `diet`, `sex`) drive their own form of "design correlation".

## Design and Partition of Effects

We begin with the Founder study having `strain`, `sex`, `diet`, and
replication of individuals within `strain:sex:diet` combinations. For a study with DO mice, there are 8 `strain`s, and we only consider 2 `diet`s and 2 `sex`s here, making 32 = 8*2*2 groups, sometimes called cells.

We will study multiple `trait`s, but begin with one.
The explained part of the `trait` variation is in the 32 cell means,
while the unexplained part is in the variation among mice in the same cell (combined then across cells). That is, we can partition the `trait` value into

<div align="center">
`trait = cellmean + noise`,
</div>

More specifically, the `cellmean` has seven components:

<div align="center">
`cellmean = strain + diet + sex + strain:sex + diet:sex + strain:diet + strain:diet:sex`,
</div>

with the last two terms (`strain:diet` and `strain:diet:sex`)
being of paramount interest.

A statistical analysis of a single `trait`, using analysis of variance (ANOVA), will partition the `trait` variation into 8
components, 7 for the `cellmean`, or model, parts and 1 for the residual, or noise or error. In a balanced study (no missing data),
these 8 components are orthogonal to each other.

### Implication of Design on Correlation

Two different `trait`s may be correlated with each other for
multiple reasons having to do with design components. Here we
illustrate this with a simpler design, say only considering `cellmean = sex`.
That is, suppose we have mice of one `strain` on one `diet`,
identified by `sex`, with equal numbers of mice by `sex`. The `trait`s $x$ and $y$ each have `sex` and `noise` components,

<div align="center">
`trait_x = sex_x + noise_x` and
`trait_y = sex_y + noise_y`,
</div>

which are are uncorrelated (`cor(sex, noise) = 0`).
Thus, the trait correlation can be partitioned into that part concerning `sex` and that concerning `noise`.

<div align="center">
`cor(trait_x. trait_y) = cor(sex_x, sex_y) + cor(noise_x, noise_y)`
</div>

As in Korol et al. (2001), the `sex` and `noise` correlations may
reinforce each other, or cancel out, or simple be different.
Again, with a more complicated design have `strain`, `sex` and `diet`, there will be 8 correlations that are all added together when considering the raw correlation of `trait`s.

### Alternatives to Correlation

There are several possible ways to approach association among traits in a designed experiment besides an "unsupervised" study based on raw correlations with post-hoc filtering, as might be done with WGCNA. For two traits, one can conduct analysis of covariance ([ANCOVA](https://www.r-bloggers.com/2021/10/analysis-of-covariance-ancova-using-r/)), which considers factors and the continuous relationship; for Korol's Figure 1, we have slopes for each ellipse (may or may not be parallel), and the separation of the ellipses. While ANCOVA is conceptually asymmetrical, as is regression, it can be interpreted in terms of co-variation. The trick here is to be clear on what is the key question, such as do the two traits see the same diet pattern across strains? That will guide how one uses ANCOVA at scale (all pairs of traits) to prioritize.

A related approach is multivariate ANOVA ([MANOVA](https://www.reneshbedre.com/blog/manova.html)) in which one aims to relate a set of traits to explanatory variables (again, strain, diet, sex). This will also take some care in how to frame questions and build tools.

Another related method is [clustering](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6634702/), which is used in WGCNA. The challenge is how to incorporate the experimental design into study of the association among traits. See Galbraith et al. (2010) for some ideas.

### Correlation on Contrasts

Another straightforward approach illustrated below is to focus on
a contrast that is of particular interest. If the focus is on the
`strain:diet` component say for one `sex`, `trait`s would be differenced across `diet`. That is, for one `sex`, we have

<div align="center">
`trait = strain + diet + strain:diet + noise`,
</div>

Average across mice in the same `strain:diet` combination,
subtract out the average for each `diet` across `strain`s,
and contrast (subtract) values between diets to get:

<div align="center">
`trait_contrast = strain:diet_contrast + noise_contrast`,
</div>

This will have one measurement per `strain` (and only considering one `sex` still), or 8 measurements per `trait` for the DO mice.
The variance of the `noise_contrast` is $2/n$, where $n$ is the number of replicates and the `SD` for the `trait` has been normalized to 1.

Or, writing this separately by `diet`s 1 and 2,

<div align="center">
`trait_1 = strain + diet_1 + strain:diet_1 + noise_1`,
</div>
<div align="center">
`trait_2 = strain + diet_2 + strain:diet_2 + noise_2`,
</div>

Thus `noise_1` has variances $1/n$ as it is based on averages over replicates, and `strain:diet_contrast = strain:diet_1 - strain:diet_2`.

To be continued. Ideally develop graphic for correlation confounding
in experimental design.

# Signal and Noise

Lets first recognize that a trait measurement consists of signal and noise. When considering correlation across traits, we hope to find traits that have correlated signals, with the noise being a nuisance. If the noise is minor, than correlation among traits essentially focuses on correlation among signals, with some slight attenuation. Here is some brief math for a `trait`:

<div align="center">
`value = signal + noise`,
</div>

with signal and noise uncorrelated. Thus the variance can be decomposed as

<div align="center">
$V_T = V_S + V_N$.
</div>

The covariance with another trait, say X, can be decomposed into

<div align="center">
$C_{T,X} = C_{S,X} + C_{N,X}$.
</div>

Again, the covariance of the trait with X is attenuated by the noise, which may increase or decrease covariance. So, the trick is to isolate the signal and consider covariances (and correlations) involving this quantity.

Two more considerations are important. The noise is the unexplained variation, or the variation you would see in a population where there is no signal. In our case, that corresponds to a population of like individuals, and the variation $V_N$ as well as the covariation $C_{N,X}$ would address (co)variation in a uniform population. That is, how do the traits co-vary in a common population? This is relevant to studying internal processes, but not to addressing how the signal changes the relationship.

The other consideration is that the signal may be accompanied by other terms, such as differences by sex or diet on their own. Further, if the trait is measured over multiple populations that are mixed together -- say from different locations or different genetic crosses -- then there there could be admixture that has design implications. Thus it is useful to consider a slightly expanded `trait` model

<div align="center">
`value = cellmean + noise = signal + rest + noise`,
</div>

with signal, rest and noise uncorrelated. The variance can be decomposed as

<div align="center">
$V_T = V_S + V_D + V_N$.
</div>

The covariance with another trait, say X, can be decomposed into

<div align="center">
$C_{T,X} = C_{S,X} + C_{D,X} + C_{N,X}$.
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

Bogue MA, Churchill GA, Chesler EJ (2015)
Collaborative Cross and Diversity Outbred data resources in the Mouse Phenome Database. Mammalian Genome 26: 511-520. <https://doi.org/10.1007/s00335-015-9595-6>.

Cavanagh C, Morell M, Mackay I, Powell W (2008)
From mutations to MAGIC: resources for gene discovery, validation and delivery in crop plants,
Current Opinion in Plant Biology 2(2)
<https://doi.org/10.1016/j.pbi.2008.01.002>.

Furlotte NA, Eskin E (2015) [Efficient Multiple-Trait Association and Estimation of Genetic Correlation Using the Matrix-Variate Linear Mixed Model](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4423381). Genetics 200: 59–68. <https://doi.org/10.1534/genetics.114.171447>  

Galbraith S, Daniel JA, Vissel B (2010) A Study of Clustered Data and Approaches to Its Analysis. J Neurosci. 30: 10601–10608. <https://doi.org/10.1523/JNEUROSCI.0362-10.2010> 

Korol A, Ronin Y, Itskovich A, Peng J, Nevo E (2001) Enhanced efficiency of quantitative trait loci mapping analysis based on multivariate complexes of quantitative traits. Genetics 157: 1789–1803. <https://doi.org/10.1093/genetics/157.4.1789>

[WGCNA: R package for performing Weighted Gene Co-expression Network Analysis](https://horvath.genetics.ucla.edu/html/CoexpressionNetwork/Rpackages/WGCNA/)
