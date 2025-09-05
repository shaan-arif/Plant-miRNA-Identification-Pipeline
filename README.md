# Plant-miRNA-Identification-Pipeline
This repository contains a complete pipeline for small RNA-seq data processing and miRNA discovery (both known and novel). The workflow is designed for plants and optimized for reads 18–34 nt long. It includes trimming, filtering, alignment, and prediction steps, enabling both conserved and novel plant miRNA identification from raw sequencing data.

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
- Conda (>=4.8)
- Python (>=3.8)

Tools used include:
- fastqc
- trimmomatic
- cutadapt
- fastx_toolkit
- bowtie
- miRDeep-P2
- ViennaRNA

The workflow uses conda environment for modular setup. If you are new to conda install it using below steps:

#### Install Miniconda (recommended lightweight Conda)
Download Miniconda installer for Linux (Python 3.8+) For other OS: see https://docs.conda.io/en/latest/miniconda.html
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```
Run installer
```bash
bash Miniconda3-latest-Linux-x86_64.sh
```
Follow the prompts, then activate conda
```bash
source ~/.bashrc
```
Update Conda to the latest version (>=4.8)
```bash
conda update -n base -c defaults conda
```
#### Environment Setup
Create and activate the environment:
```bash
conda create -n sRNAseq_analysis -y
conda activate sRNAseq_analysis
```
Then install the required tools:
```bash
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




