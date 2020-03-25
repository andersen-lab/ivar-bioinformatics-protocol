<img src="Andersen_lab.jpg" alt="hi" class="inline" width="500">

# iVar

## bioinformatics protocol

#### This document is for the iVar package: https://github.com/andersen-lab/ivar

```Instructions for setting up the environment for running ivar```

## Software Setup

These instructions are for a 64-bit UNIX, Linux or similar envrionment.

#### Conda

iVar is installed using [Conda](https://conda.io/en/latest/)

#### Installing ivar
Install the ivar repository:

```
git clone https://github.com/andersen-lab/ivar-bioinformatics-protocol
```

Create a custom environment for ivar. Please wait while required packages are installed.

```
conda env create -f environment-ivar.yml
```

Activate the ivar environment.

```
conda activate ivar
```

After use, deactivate the environment.

```
conda deactivate
```

To remove the ivar environment use the following command.

```
conda remove --name ivar --all
```

## Commands

alignment using [bwa](https://github.com/lh3/bwa)
```
bwa index ref.fa
bwa mem ref.fa read-se.fq.gz | gzip -3 > aln-se.sam.gz
./bwa mem ref.fa read1.fq read2.fq | gzip -3 > aln-pe.sam.gz
```

ivar trim
```
ivar trim <input.bam> <primers.bed> <prefix>
```

ivar consensus
```
ivar filtervariants <prefix> replicate-one.tsv replicate-two.tsv ... OR ivar filtervariants <prefix> <text file with one variant file per line> 
```
