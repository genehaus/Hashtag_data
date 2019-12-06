# run_hashtag_data

1. Install CITE-seq-Count
 
https://github.com/Hoohm/CITE-seq-Count

```
pip install CITE-seq-Count --user 
```

2. Pre-required data

2-1. tags.csv 

2-2. barcodes.tsv

https://github.com/10XGenomics/cellranger/blob/master/lib/python/cellranger/barcodes/translation/3M-february-2018.txt.gz

3. Run 

'''
#!/usr/XXX/bin/zsh
#SBATCH -J CITE-seq-Count
#SBATCH -t 100:00:00
#SBATCH --mem-per-cpu=10240M
#SBATCH --output=output.%J.txt
/XXX/CITE-seq-Count -R1 /XXX/XXX_S1_L001_R1_001.fastq.gz,/XXX/XXX_S1_L002_R1_001.fastq.gz -R2 /XXX/XXX_S1_L001_R2_001.fastq.gz,/XXX/XXX_S1_L002_R2_001.fastq.gz -t /XXX/tags.csv -cbf 1 -cbl 16 -umif 17 -umil 28 -cells 0 -wl /XXX/barcodes.tsv -o /XXX/XXX_ouput/
'''

References & Good Q&A

https://github.com/Hoohm/CITE-seq-Count<br>

https://github.com/Hoohm/CITE-seq-Count/issues/82<br>

https://github.com/Hoohm/CITE-seq-Count/issues/62<br>

