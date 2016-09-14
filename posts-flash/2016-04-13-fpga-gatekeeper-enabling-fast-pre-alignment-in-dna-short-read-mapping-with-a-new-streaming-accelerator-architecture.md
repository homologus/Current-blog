---
title: 'FPGA - GateKeeper: Enabling Fast Pre-Alignment in DNA Short Read Mapping with
  a New Streaming Accelerator Architecture'
tags: []
categories:
- blog
---
[Link](http://arxiv.org/abs/1604.01789)
<!--more-->

> Genome analysis helps to reveal the genomic variants that cause diseases and
evolution of species. Unfortunately, high throughput DNA sequencing (HTS)
technologies generate excessive number of small DNA segments -called short
reads- that incur significant computational burden. To analyze the entire
genome, each of the billions of short reads must be mapped to a reference
genome through a computationally expensive process. Due to sequencing errors
and genomic variants, the similarity measurement between a read and
"candidate" locations in the reference genome, called alignment, is formulated
as an approximate string-matching problem, which is solved using quadratic-
time dynamic programming algorithms. In practice, the majority of candidate
locations do not align with a given read due to high dissimilarity. The
verification process of such candidate locations occupies most of a modern
read mapper's execution time. We propose GateKeeper, a new architecture that
functions as a pre-alignment step that quickly filters out most incorrect
candidate locations. The main idea of GateKeeper is to filter out the
incorrect mappings in a streaming fashion using Field-Programmable Gate Arrays
(FPGAs). By excluding the incorrect mappings at an early stage, we reduce the
number of candidate verifications in the rest of the execution, and thus
accelerate the read mapping. GateKeeper is the first design to accelerate pre-
alignment using new hardware technologies. On a single FPGA chip, it provides
up to 17.3-fold speedup over the state-of-the-art pre-alignment technique,
SHD. GateKeeper can provide more than two orders of magnitude speedup over
other hardware-accelerated mapping tools such as BWA and BFAST.

