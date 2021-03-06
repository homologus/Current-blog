---
title: Efficient Algorithms for de novo Assembly of Alternative Splicing Events from
  RNA-seq Data
categories:
- rnaseq
---
Readers may enjoy this new arxiv paper from Gustavo Sacomoto (h/t: haldane's
sieve)
<!--more-->

E[fficient Algorithms for de novo Assembly of Alternative Splicing Events from
RNA-seq Data](http://arxiv.org/abs/1406.6047)

> In this thesis, we address the problem of identifying and quantifying
variants (alternative splicing and genomic polymorphism) in RNA-seq data when
no reference genome is available, without assembling the full transcripts.
Based on the fundamental idea that each variant corresponds to a recognizable
pattern, a bubble, in a de Bruijn graph constructed from the RNA-seq reads, we
propose a general model for all variants in such graphs. We then introduce an
exact method, called KisSplice, to extract alternative splicing events.
Finally, we show that it enables to identify more correct events than general
purpose transcriptome assemblers.

In order to deal with ever-increasing volumes of NGS data, we put an extra
effort to make KisSplice as scalable as possible. First, to improve its
running time, we propose a new polynomial delay algorithm to enumerate
bubbles. We show that it is several orders of magnitude faster than previous
approaches. Then, to reduce its memory consumption, we propose a new compact
way to build and represent a de Bruijn graph. We show that our approach uses
30% to 40% less memory than the state of the art, with an insignificant impact
on the construction time.

Additionally, we apply the same techniques developed to list bubbles in two
classical problems: cycle enumeration and the K-shortest paths problem. We
give the first optimal algorithm to list cycles in undirected graphs,
improving over Johnson's algorithm. This is the first improvement to this
problem in almost 40 years. We then consider a different parameterization of
the classical K-shortest (simple) paths problem: instead of bounding the
number of st-paths, we bound the weight of the st-paths. We present new
algorithms with the same time complexities but using exponentially less memory
than previous approaches.

