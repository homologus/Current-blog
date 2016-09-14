---
title: Bioinformatics Patents on Burrows Wheeler Transform
tags: []
categories:
- blog
---
While "[Complete Genomics, Illumina Settle Patent Infringement
Lawsuits](http://www.genomeweb.com/sequencing/complete-genomics-illumina-
settle-patent-infringement-lawsuits)", bioinformaticians will be looking
forward to a new level of nuisance.
<!--more-->

**Pacbio's BLASR patent**: 

[SEQUENCE ASSEMBLY AND CONSENSUS SEQUENCE
DETERMINATION](http://www.freepatentsonline.com/y2012/0330566.html)

United States Patent Application 20120330566 Kind Code: A1

Abstract:

> Computer implemented methods, and systems performing such methods for
processing signal data from analytical operations and systems, and
particularly in processing signal data from sequence-by-incorporation
processes to identify nucleotide sequences of template nucleic acids and
larger nucleic acid molecules, e.g., genomes or fragments thereof. In
particularly preferred embodiments, nucleic acid sequences generated by such
methods are subjected to de novo assembly and/or consensus sequence
determination.

Inventor: Chaisson, Mark (San Francisco, CA, US)

Assignee: Pacific Biosciences of California, Inc. (Menlo Park, CA, US)

Does that mean anyone using BLASR is violating the patent? Or anyone
implementing an alignment algorithm with the following rules?

> A method of aligning a sequence read to a reference sequence, comprising: a)
sequencing a target nucleic acid to provide a sequence read; b) providing a
reference sequence for the target nucleic acid; c) finding a set of
subsequences in the sequence read that match portions of the reference
sequence; d) refining the set of subsequences, wherein the refining comprises
scoring and realigning the subsequences using sparse dynamic programming; and
e) scoring and realigning a final set of subsequences using a banded
alignment, thereby aligning the sequence read to the reference sequence.

2\. The method of claim 1, wherein the finding comprises finding all exact
matches from the sequence read that are longer than a minimum match length k
and that match the reference sequence.

3\. The method of claim 2, wherein k is between 8 and 15.

etc.

BWA-MEM chains the seeds during the alignment. Does that mean use of BWA-MEM
in GATK violates PacBio patents?

>

5\. The method of claim 1, wherein the finding comprises clustering exact
matches using global chaining.

..........

15\. The method of claim 1, wherein the sequencing is performed using a method
selected from the group consisting of pyrosequencing, tSMS sequencing, Sanger
sequencing, Solexa sequencing, SMRT sequencing, SOLiD sequencing, Maxam and
Gilbert sequencing, nanopore sequencing, and semiconductor sequencing.

\----------------------------------------------------------------

**Illumina's BCR patent (applied, not granted):**

[METHODS AND SYSTEMS FOR DATA
ANALYSIS](http://www.freepatentsonline.com/y2012/0330567.html)

>

The present disclosure provides computer implemented methods and systems for
analyzing datasets, such as large data sets output from nucleic acid
sequenceing technologies. In particular, the present disclosure provides for
data analysis comprising computing the BWT of a collection of strings in an
incremental, character by character, manner. The present disclosure also
provides compression boosting strategies resulting in a BWT of a reordered
collection of data that is more compressible by second stage compression
methods compared to non-reordered computational analysis.

United States Patent Application 20120330567 Kind Code: A1

Inventors:

Bauer, Markus J. (Mariapfarr, AT)

Cox, Anthony James (Nr Saffron Walden, GB)

Rosone, Giovanna (Palermo, IT)

Evers, Dirk (Arkesden, GB)

Assignee: ILLUMINA CAMBRIDGE LIMITED (Nr Saffron Walden, GB)

Hmm...seems like Jared Simpson's string graph assembler cannot be used any
more given that its index creation violates this patent (Please see an update
from Jared at the bottom).

>

1\. A method for determining the sequence of a nucleic acid comprising: a)
receiving a collection of data strings from a nucleic acid sequence dataset
wherein said data strings comprise a plurality of characters, b) generating a
Burrows Wheeler transform on a first collection of characters, wherein the
first collection of characters comprises a first character from each of said
data strings, c) merging a second collection of characters with said first
collection of characters to form a merged collection of characters, wherein
the second collection of characters comprises a second character from each of
said data strings, d) augmenting the Burrows Wheeler transform from the merged
first and second collection of characters, and e) determining the sequence of
the nucleic acid based on the Burrows Wheeler transform of the nucleic acid.

etc.

\----------------------------------------------------------

**Unrelated alignment-related patents (does not use BWT)**

V. Galinsky claiming to do better than Smith-Waterman.

[Method for rapid assessment of similarity between sequences - V.
Galinsky](http://patents.justia.com/patent/20130091121)

[Method for fast and accurate alignment of sequences - V.
Galinsky](http://patents.justia.com/patent/20130041593)

> Application number: 20130041593

Abstract: Genomic sequence matching and alignment techniques are disclosed. In
one embodiment of the invention, computerized methods are provided for
analyzing sequence similarity data obtained by means of a table of all local
hits recorded between query sequence and reference index. The table of local
hits represents all occurrences of query subsequences in reference index that
stored all transitions between single l-mer prefix to multiple m-mer suffixes.
The index data structure may take a variety of forms, including an array or a
tree. The base position of each transition from l-prefix to m-suffix is
recorded in k-bit masked form. The positions data structure may take a variety
of forms as well, including an array or a tree. The table of local hits
derived from l-prefix, m-suffix and k-position reference index is used by a
series of low time and space complexity algorithms for optimizing alignment
between query and reference.

Gimme a break !!! Can you patent something in GPU and FPGA without
implementing anything in GPU and FPGA? In the earlier days, people claiming to
build better mousetrap had to build one before patenting.

Of course the above patents are irrelevant, because

[Forget Gene Patents. Co-founder of 23andMe Patents Personalized
Genomics](http://www.homolog.us/blogs/blog/2013/06/21/forget-gene-patents-co-
founder-of-23andme-patents-personalized-genomics/)

\------------------------------------

Edit.

**An Update from Jared Simpson regarding SGA**

We contacted Jared Simpson, Heng Li and Anthony Cox about the implications of
above patents.

Anthony Cox corrected us about the status of the patent. Currently, their
innovation on BCR is under pending status under review and not a granted
patent. Also, he highlighted our previous discussion in the BEETL/ISAAC
thread, where he explained IP position of Illumina in the comment section.

"My understanding of the license is that it is meant to allow you to do pretty
much whatever you want with the code install, use, distribute, modify for non-
commercial purposes."

[Academic Bioinformaticians Uncomfortable with Illuminas Publication of
Variant Caller](http://www.homolog.us/blogs/blog/2013/06/05/academic-
bioinformaticians-uncomfortable-with-illuminas-publication-of-variant-caller/)

Jared wrote back to us:

> We are aware of Illumina's patent and discussed our implementation of BCR
with them. They agreed that we can release our implementation as long as we
provided a notice in SGA's README
(<https://github.com/jts/sga/blob/master/src/README#L151>). I was satisfied
with this arrangement but am generally opposed to algorithm patents.

Does that clear up SGA? We doubt it until Illumina lawyers write something up
explaining what they agree to and what they do not.

i) Can SGA be used for commercial and non-commercial purposes? (To save
readers time, we had a similar discussion with Tony Cox earlier on another
program recently released by Illumina - [Academic Bioinformaticians
Uncomfortable with Illuminas Publication of Variant
Caller](http://www.homolog.us/blogs/blog/2013/06/05/academic-
bioinformaticians-uncomfortable-with-illuminas-publication-of-variant-
caller/)).

ii) Can SGA, a [GPL-licensed
code](https://github.com/jts/sga/blob/master/src/COPYING), be modified and
'sold' by anyone other than Jared, provided he follows GPL's rules about
releasing the source code? Or does each programmer have to separately
negotiate with Illumina's IP office to get the same approval that Jared got?

iii) If SGA can be updated by anyone other than Jared, can that person turn
off all other blocks of SGA and keep only the BCR-inspired library, but still
call the forked version SGA? What is the patent protecting then?

Oh well, we should not have mentioned (iii) before seeing the signed document
regarding (i) and (ii) :)
