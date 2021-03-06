---
title: Untangling Genomes from Metagenomes (Attn. SOLiD users)
tags:
- ABI-SoLID
- genome assembly
- metagenome
categories:
- blog
---
Professor E. Virginia Armbrust, one of our collaborators, [published an
interesting paper](http://www.sciencemag.org/content/335/6068/587) on de novo
assembly of metagenomes that is worth paying attention to.
<!--more-->

Especially those working on SOLiD data can find use in the tools developed by
professor Armbrust's group, even if you are not working directly on
metagenomic data. Vaughn Iverson, the first author of the paper, is a very
bright bioinformatician, and he found the standard Velvet assembly program to
be of limited use in his analysis. Therefore, he developed a set of custom
programs to generate larger scaffolds by connecting and extending contigs
generated by Velvet.

Vaughn is depositing his custom programs at
[github](https://github.com/armbrustlab/SEAStAR) under GPL license. A user
manual is available at [this github link](https://github.com/armbrustlab/SEASt
AR/blob/master/SEAStAR_User_Guide.pdf).

Here is the abstract of the paper -

>

**Untangling Genomes from Metagenomes: Revealing an Uncultured Class of Marine Euryarchaeota**

Vaughn Iverson, Robert M. Morris, Christian D. Frazar, Chris T. Berthiaume,
Rhonda L. Morales, E. Virginia Armbrust

Ecosystems are shaped by complex communities of mostly unculturable microbes.
Metagenomes provide a fragmented view of such communities, but the ecosystem
functions of major groups of organisms remain mysterious. To better
characterize members of these communities, we developed methods to reconstruct
genomes directly from mate-paired short-read metagenomes. We closed a genome
representing the as-yet uncultured marine group II Euryarchaeota, assembled de
novo from 1.7% of a metagenome sequenced from surface seawater. The genome
describes a motile, photo-heterotrophic cell focused on degradation of protein
and lipids and clarifies the origin of proteorhodopsin. It also demonstrates
that high-coverage mate-paired sequence can overcome assembly difficulties
caused by interstrain variation in complex microbial communities, enabling
inference of ecosystem functions for uncultured members.

