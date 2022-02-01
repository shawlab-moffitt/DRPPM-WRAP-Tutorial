
# DRPPM WRAP Tutorial

## DNA RNA Proteome Post-translational Modifications

[DRPPM](https://github.com/gatechatl/DRPPM) is a library collection of scripts for analyzing DNA/RNA/Proteome/Post-translational Modifications. Below is a example RNA-seq analysis workflow using the DRPPM software on FASTQ files from a study observing the knockdown of the USP7 gene in humans.

## DRPPM Installation

### Dependencies

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| RSEQC_2.6.4 | STAR_2.7.6a | ucsctools_1.04.00 | GCC_5.5.0 | python_2.7.9 |
| glibc_2.14.1 | samtools_1.1 | fastqc_0.11.7 | R_3.5.1 | Bedtools_2.27.1 |

### Git Checkout

```
git clone git@github.com:gatechatl/DRPPM.git # Clone the repo
```

More information on installation and dependencies can be found on the [DRPPM GitHub Page](https://github.com/gatechatl/DRPPM).

## Pipeline Preparation

### Generate .lst file

1. Gather list of FASTQ files and run through -Fastq2FileList function.
   * This will pair the FASTQ files on the same line
   * For our example we gathered the path and file name for all the FASTQs in a preliminary [fastq.lst]() file
```
drppm -Fastq2FileList [inputFile] [outputFile]
drppm -Fastq2FileList fastq.lst USP7.lst
```

2. The .lst file will then need to be edited with further information on each line in the format below.
   * This was done manually but a script is in development to assist in generation of this file.
```
[Sample_Name]\t[FASTQ_1]\t[FASTQ_2]\t[Read_Length]\t[Forward_or_Reverse]
```

### Construct Config File

1. Edit the config file, [hg38_WRAP.config](), which will configure which functions to generate for the pipeline
   * This file contains the location of various files used within the pipeline and some configuration options.


