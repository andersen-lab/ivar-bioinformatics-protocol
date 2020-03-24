
![image](https://github.com/andersen-lab/ivar-bioinformatics-protocol/blob/master/Andersen_lab.jpg)

# ivar

## bioinformatics protocol

#### This document is for the ivar package: https://github.com/andersen-lab/ivar

```Instructions for setting up the environment for running ivar```

### Software Setup

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
