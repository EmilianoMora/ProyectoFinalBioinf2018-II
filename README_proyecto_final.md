# ProyectoFinalBioinf2018-II (Emiliano Mora)
# README

## Genome scan of _Primula tibetica_

This repo contains scripts and genomic data for population genetics analysis of _Primula tibetica_.

For this work I used sequences from 112 individuals of _Primula tibetica_ derived from the study of Ren et al. (2017). The sequences used were obtanied by using the method of ddRAD with single-end sequencing on a HiSeq2500 platform. This sequences where obtained from the Sequence Read Archive (SRA) under the BioProject:PRJNA339808. The original study generated 293 sequences (16 populations) but I only used 8 individuals from 14 populations.

In general the analysis contained in this repo includes: Aligment of each sample to genome of reference (_Primula veris_) with BWA; analysis of population genetics with Stacks and an analysis of genomic adaptation with PCADAPT.

This repository is composed by four folders:

- _bin_: Contain scripts to perform all the analysis
- _data_: Contain al genomica data to perform analysis of population genomics of P. tibetica.
    1. `datos_crudos`: contains processed sequences of 112 individuals from _P.tibetica_ in .fastq format.
    2. `fastqc`: contains .html results from Fastqc for all sequences.
    3. `referenceGenome`: genome assembly of _P. veris_ in .fa format as a genome of reference. This genomic assembly is derived from Nowak et al. (2016).
    4. `bwa`: contains the index of the reference genome made with BWA as well as other directory containing individual aligments of each sample into the reference genome (in .bam format),
    5. `stacks`: contains a directory with results derived from 'gstacks' (called variants sites in the populations and generation of genotypes for each sample); as well as other directory with results from 'populations' module..

- _meta_: contains information of the individuals, populations, etc, used in this study.
- _figures_: contains figures used in this work.

## Prerequisites
### Install the SRA tool kit

wget "https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/2.9.0/sratoolkit.2.9.0-ubuntu64.tar.gz"

tar -vxzf sratoolkit.2.9.0-ubuntu64.tar.gz

export PATH=$

### Install BWA (Burrow-Wheeler Alginer)

wget "https://sourceforge.net/projects/bio-bwa/files/bwa-0.7.17.tar.bz2/download"

tar -vxjf bwa-0.7.17.tar.bz2

cd bwa-0.7.17

sudo make

### Install samtools

wget "https://github.com/samtools/samtools/releases/download/1.8/samtools-1.8.tar.bz2"

tar -vxjf samtools-1.8.tar.bz2 

cd samtools-1.8 

./configure 

make 

make install 

### Install Stacks

wget "http://catchenlab.life.illinois.edu/stacks/source/stacks-2.0.tar.gz"

tar -vxjf stacks-2.0.tar.gz

./configure

make

sudo make install

## Citations
Ren G, Mateo RG, Liu J, Suchan T, Alvarez N, Guisan A, Conti E, Salamin N. 2017. Genetic consequences of Quaternary climatic oscillations in the Himalayas: _Primula tibetica_ as a case study based on restriction site-associated DNA sequencing. New Phytologist 213:1500-1512.

Nowak MD, Russo G, Schlapbach R, Huu CN, Lenhard M,Conti E. (2015) The draft genome of _Primula veris_ yields insights into the molecular basis of heterostyly. Genome Biol-ogy, 16, doi:10.1186/s13059-014-0567-z.
