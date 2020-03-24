<img src="Andersen_lab.jpg" alt="hi" class="inline" width="500">

# ivar

## bioinformatics protocol

#### This document is for the ivar package: https://github.com/andersen-lab/ivar

```Instructions for setting up the environment for running ivar```

## Software Setup

These instructions are for a 64-bit UNIX, Linux or similar envrionment.

#### Conda

ivar is installed using [Conda](https://conda.io/en/latest/)

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
ivar trim -i <input.bam> -b <primers.bed> -p <prefix> [-m <min-length>] [-q <min-quality>] [-s <sliding-window-width>]

Input Options    Description
           -i    (Required) Sorted bam file, with aligned reads, to trim primers and quality
           -b    (Required) BED file with primer sequences and positions
           -m    Minimum length of read to retain after trimming (Default: 30)
           -q    Minimum quality threshold for sliding window to pass (Default: 20)
           -s    Width of sliding window (Default: 4)
           -e    Include reads with no primers. By default, reads with no primers are excluded
Output Options   Description
           -p    (Required) Prefix for the output BAM file
```

ivar consensus
```
ivar filtervariants -p <prefix> replicate-one.tsv replicate-two.tsv ... OR ivar filtervariants -p <prefix> -f <text file with one variant file per line> 

Input: Variant tsv files for each replicate/sample
Input Options    Description
           -t    Minimum fration of files required to contain the same variant. Specify value within [0,1]. (Default: 1)
           -f    A text file with one variant file per line.
Output Options   Description
           -p    (Required) Prefix for the output filtered tsv file
```
