# Plant-miRNA-Identification-Pipeline
This repository contains a complete pipeline for small RNA-seq data processing and miRNA discovery (both known and novel). The workflow is optimized for reads 18–34 nt long and includes trimming, filtering, alignment, and prediction steps.

### What is Small RNA Sequencing (sRNA-Seq)?
Small RNA sequencing (sRNA-Seq) is a high-throughput method used to profile small regulatory RNA molecules, typically ranging from 18 to 34 nucleotides. These include:

- microRNAs (miRNAs)

- small interfering RNAs (siRNAs)

- piwi-interacting RNAs (piRNAs)

- tRNA fragments (tRFs)

- other non-coding small RNAs

These small RNAs play crucial roles in gene regulation, development, stress responses, and epigenetic regulation, especially in plants. Unlike mRNA-seq, small RNA-seq data requires specialized preprocessing steps.This pipeline performs:

- Quality check and adapter trimming

- rRNA/tRNA/snRNA/snoRNA filtering using Rfam

- Known miRNA identification using miRBase

- Novel miRNA prediction using miRDeep-P2

### Requirements
The workflow uses conda environment for modular setup. Tools used include:

fastqc

trimmomatic

cutadapt

fastx_toolkit

bowtie (not bowtie2)

miRDeep-P2

ViennaRNA

#### Environment Setup
Create and activate the environment:

```
bash
conda create -n sRNAseq_analysis -y
conda activate sRNAseq_analysis
```
Install Required Tools:
Note: Java is a prerequisite for tools like Trimmomatic.
Check if Java is installed using:
```
bash
java --version
```
If not installed, install it with:
```
bash
conda install -c conda-forge openjdk
```
Then install the required tools:
```
bash
conda install -c bioconda fastqc trimmomatic cutadapt fastx_toolkit bowtie=1.3.1 mirdeep-p2 viennarna
```

### Directory Structure
```
.
├── data/                      # Raw and intermediate files
│   ├── fastq/
│   ├── adapters/
│   ├── rfam/
│   └── mirbase/
├── scripts/                   # Shell and Perl scripts
├── results/                   # Output from known and novel prediction
│   ├── fastqc/
│   ├── trimmed/
│   ├── alignment/
│   └── predictions/
├── genome/                    #  Genome and index
├── README.md
```




