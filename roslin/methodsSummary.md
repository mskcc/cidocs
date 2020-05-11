# Roslin Methods

{ver:2020-05-10}

Demultiplexed fastq files were aligned to the human reference genome
GRCh37 using BWA-MEM (Burrows-Wheeler Aligner v0.7.5a,
http://arxiv.org/abs/1303.3997), and PCR duplicates were identified by
MarkDuplicates in Picard Tools v1.96
(https://github.com/broadinstitute/picard). Genomic regions covered by
at least 20x read depth were identified using FindCoveredIntervals
from GATK Tool Kit2 and subjected to indel realignment using Assembly
Based ReAligner (ABRA) version 0.92. Variant calling was performed in
paired tumor/normal mode using a ciombination of MuTect software
version 1.1.44 and Vardict version 1.5.1. All variants were annotated
using vcf2maf v1.6.13 (https://github.com/mskcc/vcf2maf) which uses
Ensembl’s Variant Effect Predictor v86. Somatic structural aberrations
were identified using DELLY. We inferred allele-specific DNA copy
number, including shallow gains and deletions, using FACETS to
determine the zygosity of key mutant tumor suppressors as well as to
generate estimates of tumor purity.
