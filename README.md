# nf_16S_metagen

This repository contains code for how LULU was implemented in ............

## Install
Create conda environment:
```
mamba env create -n nf_16S_metagen -f environment.yml
```

Activate environment:
```
mamba activate nf_16S_metagen
```

Open an R session and install lulu:

```
install.packages("remotes")
library("remotes")
install_version("devtools", "1.13.0")
library("devtools")
options(unzip = "internal")
install_github("tobiasgf/lulu@c8c1931")
```

Create fasta file:
```
cat dada_seqs.txt | awk '{print ">"$1"\n"$2}' > dada_seqs.fa
```

## Run

```
nextflow run main.nf -with-conda /path/to/conda/env/nf_16S_metagen/ --fasta /path/to/dada_seqs.fa
--otu_table /path/to/dada_table.txt --outfile lulu_out.txt
```
