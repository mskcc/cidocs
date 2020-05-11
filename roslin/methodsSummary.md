# Roslin Methods

{ver:unkown}

Demultiplexed fastq files were aligned to the human reference genome
GRCh37 using BWA-MEM (Burrows-Wheeler Aligner v0.7.5a,
http://arxiv.org/abs/1303.3997), and PCR duplicates were identified by
MarkDuplicates in Picard Tools v1.96
(https://github.com/broadinstitute/picard). Genomic regions covered by
at least 20x read depth were identified using FindCoveredIntervals
from GATK Tool Kit2 and subjected to indel realignment using Assembly
Based ReAligner (ABRA) version 0.92. Variant calling was performed in
paired tumor/normal mode using MuTect software version 1.1.44 for
single nucleotide variants and SomaticIndelDetector2 and Pindel
software version 0.2.5a75 for small insertions and deletions. All
variants were annotated using vcf2maf v1.6.13
(https://github.com/mskcc/vcf2maf) which uses Ensembl’s Variant Effect
Predictor v86. Copy number variation was identified by analyzing
sequence coverage of targeted regions in a tumor sample in comparison
to a standard diploid normal sample after performing sample wide LOESS
normalization for GC percentage across exons and normalizing for
global differences in “on-target” sequence coverage, as previously
described. Somatic structural aberrations were identified using DELLY.
We inferred allele-specific DNA copy number, including shallow gains
and deletions, using FACETS to determine the zygosity of key mutant
tumor suppressors as well as to generate estimates of tumor purity.

