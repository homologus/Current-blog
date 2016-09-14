---
title: After SAM and BAM Comes ADAM !
tags: []
categories:
- blog
---
A Berkeley group is proposing [new data
format](http://www.eecs.berkeley.edu/Pubs/TechRpts/2013/EECS-2013-207.html).
<!--more-->

> Current genomics data formats and processing pipelines are not designed to
scale well to large datasets. The current Sequence/Binary Alignment/Map
(SAM/BAM) formats were intended for single node processing. There have been
attempts to adapt BAM to distributed computing environments, but they see
limited scalability past eight nodes. Additionally, due to the lack of an
explicit data schema, there are well known incompatibilities between libraries
that implement SAM/BAM/Variant Call Format (VCF) data access. To address these
problems, we introduce ADAM, a set of formats, APIs, and processing stage
implementations for genomic data. ADAM is fully open source under the Apache 2
license, and is implemented on top of Avro and Parquet for data storage. Our
reference pipeline is implemented on top of Spark, a high performance in-
memory map-reduce system. This combination provides the following advantages:
1) Avro provides explicit data schema access in C/C++/C#, Java/Scala, Python,
php, and Ruby; 2) Parquet allows access by database systems like Impala and
Shark; and 3) Spark improves performance through in-memory caching and
reducing disk I/O. In addition to improving the formats cross-platform
portability, these changes lead to significant performance improvements. On a
single node, we are able to speedup sort and duplicate marking by 2. More
importantly, on a 250 Gigabyte (GB) high (60) coverage human genome, this
system achieves a 50 speedup on a 100 node computing cluster (see Table 1),
fulfilling the promise of scalability of ADAM. The ADAM format provides
explicit schemas for read and reference oriented (pileup) sequence data,
variants, and genotypes. As the schemas are implemented in Apache Avroa cross-
platform/language serialization formatthey eliminate the need for the
development of language-specific libraries for format decoding/encoding, which
eliminates the possibility of library incompatibilities. A key feature of ADAM
is that any application that implements the ADAM schema is compatible with
ADAM. This is important, as it prevents applications from being locked into a
specific tool or pattern. The ADAM stack is inspired by the narrow waist of
the Internet Protocol (IP) suite (see Figure 2). We consider the explicit use
of a schema in this format to be the greatest contribution of the ADAM stack.
In addition to the advantages outlined above, ADAM eliminates the file headers
in modern genomics formats. All header information is available inside of each
individual record. The variant and genotype formats also demonstrate two
significant improvements. First, these formats are co-designed so that variant
data can be seamlessly calculated from a given collection of sample genotypes.
Secondly, these formats are designed to flexibly accommodate annotations
without cluttering the core variant/genotype schema. In addition to the
benefits described above, ADAM files are up to 25% smaller on disk than
compressed BAM files without losing any information. The ADAM processing
pipeline uses Spark as a compute engine and Parquet for data access. Spark is
an in-memory MapReduce framework which minimizes I/O accesses. We chose
Parquet for data storage as it is an open-source columnar store that is
designed for distribution across multiple computers with high compression.
Additionally, Parquet sup- ports efficient methods (predicates and
projections) for accessing only a specific segment or fields of a file, which
can provide significant (2-10) additional speedup for genomics data access
patterns.

