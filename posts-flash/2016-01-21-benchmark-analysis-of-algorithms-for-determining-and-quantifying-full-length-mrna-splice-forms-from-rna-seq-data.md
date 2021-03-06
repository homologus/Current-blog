---
title: Benchmark analysis of algorithms for determining and quantifying full-length
  mRNA splice forms from RNA-seq data
categories:
- rnaseq
---
>
Abstract
<!--more-->

MOTIVATION:

Because of the advantages of RNA sequencing (RNA-Seq) over microarrays, it is
gaining widespread popularity for highly parallel gene expression analysis.
For example, RNA-Seq is expected to be able to provide accurate identification
and quantification of full-length splice forms. A number of informatics
packages have been developed for this purpose, but short reads make it a
difficult problem in principle. Sequencing error and polymorphisms add further
complications. It has become necessary to perform studies to determine which
algorithms perform best and which if any algorithms perform adequately.
However, there is a dearth of independent and unbiased benchmarking studies.
Here we take an approach using both simulated and experimental benchmark data
to evaluate their accuracy.

RESULTS:

We conclude that most methods are inaccurate even using idealized data, and
that no method is highly accurate once multiple splice forms, polymorphisms,
intron signal, sequencing errors, alignment errors, annotation errors and
other complicating factors are present. These results point to the pressing
need for further algorithm development.

AVAILABILITY AND IMPLEMENTATION:

Simulated datasets and other supporting information can be found at
http://bioinf.itmat.upenn.edu/BEERS/bp2SUPPLEMENTARY INFORMATION:
Supplementary data are available at Bioinformatics online.

[Link](http://www.ncbi.nlm.nih.gov/pubmed/26338770)
