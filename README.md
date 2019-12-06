# run_hashtag_data

This information was written based on other's works and website. 

1. Install CITE-seq-Count<br>
https://github.com/Hoohm/CITE-seq-Count

```
pip install CITE-seq-Count --user 
```


2. Pre-required data

2.1. tags.csv<br>
2.2. whitelist = barcodes.tsv

Download the file from https://github.com/10XGenomics/cellranger/blob/master/lib/python/cellranger/barcodes/translation/3M-february-2018.txt.gz <br>
(This file is same as the barcodes.tsv from raw_feature_bc_matrix)	<br>
or get barcodes.tsv from "filtered_feature_bc_matrix", one of the output from CellRanger 


3. Run 

```
#!/usr/XXX/bin/zsh
#SBATCH -J CITE-seq-Count
#SBATCH -t 100:00:00
#SBATCH --mem-per-cpu=10240M
#SBATCH --output=output.%J.txt
/XXX/CITE-seq-Count -R1 /XXX/XXX_S1_L001_R1_001.fastq.gz,/XXX/XXX_S1_L002_R1_001.fastq.gz -R2 /XXX/XXX_S1_L001_R2_001.fastq.gz,/XXX/XXX_S1_L002_R2_001.fastq.gz -t /XXX/tags.csv -cbf 1 -cbl 16 -umif 17 -umil 28 -cells 0 -wl /XXX/barcodes.tsv -o /XXX/XXX_ouput/
```

XXX should be full directory or file name 

**References & Good Q&A web source**

https://github.com/Hoohm/CITE-seq-Count<br>
https://github.com/Hoohm/CITE-seq-Count/issues/82<br>
https://github.com/Hoohm/CITE-seq-Count/issues/62<br>

