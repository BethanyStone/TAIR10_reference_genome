##### /home/bethany.stone/reference_genomes/TAIR10/README.md

## TAIR10 reference genomes info

##### **Download:**
TAIR10 reference genome sequence downloaded from TAIR (https://www.arabidopsis.org/).  

See FTP archive/Sequences/whole_chromosomes (ftp://ftp.arabidopsis.org/home/tair/Sequences/whole_chromosomes/).  TAIR10_chr1.fas, TAIR10_chr2.fas, TAIR10_chr3.fas, TAIR10_chr4.fas TAIR10_chr5.fas. TAIR10.chrC.fas, and TAIR10_chrM.fas were downoaded November 10 2017. Files were downloaded using wget command.  
See ftp://ftp.arabidopsis.org/home/tair/Sequences/whole_chromosomes/README_whole_chromosomes.txt for README_whole_chromosomes.txt file corresponding to fasta sequences downloaded. 

File names were changed from .fas to .fa upon download, as below:
```sh
mv TAIR10_chr1.fas TAIR10_chr1.fa
mv TAIR10_chr2.fas TAIR10_chr2.fa
mv TAIR10_chr3.fas TAIR10_chr3.fa
mv TAIR10_chr4.fas TAIR10_chr4.fa
mv TAIR10_chr5.fas TAIR10_chr5.fa
mv TAIR10_chrC.fas TAIR10_chrC.fa
mv TAIR10_chrM.fas TAIR10_chrM.fa
```

To get fasta file containing all chromosome sequences (names TAIR10_allchr.fa):
```sh
cat TAIR10_chr1.fa TAIR10_chr2.fa TAIR10_chr3.fa TAIR10_chr4.fa TAIR10_chr5.fa TAIR10_chrC.fa TAIR10_chrM.fa > TAIR10_allchr.fa
```


##### **Storage:**
All TAIR10 reference genome fasta files are kept in reference_genomes directory (/home/bethany.stone/reference.genomes/TAIR10.  
All fasta files are kept as gzipped files, unless being used.  
Any genome prep/index files built from TAIR10 reference genome fasta files are also kept insub-directories within the reference_genomes directory (all file names have TAIR10 prefix). 

##### **Bismark genome preparation:**
To prepare bowtie2 reference genome for use in bismark alignement (in wgbs_pipeline_v1.0):
```sh
bismark_genome_preparation --bowtie2 TAIR10_allchr.fa
```

To prepare bowtie1 reference genome (if needed - bowtie2 is used in wgbs_pipeline_v1.0):
```sh
bismark_genome_preparation TAIR10_allchr.fa
```

Bowtie1 and bowtie2 reference genomes are kept in TAIR10_bowtie1_genome and TAIR10_bowtie2_genome directories, respectively.


##### **Subread genome indexing:**
To prepare subread index reference genome for use in subread alignment (in RNA-Seq_pipeline_v1.0):
```sh
subread-buildindex -o TAIR10_subread_index TAIR10_chr1.fa TAIR10_chr2.fa TAIR10_chr3.fa TAIR10_chr4.fa TAIR10_chr5.fa TAIR10_chrC.fa TAIR10_chrM.fa
```

Subread indexed genome is kept in TAIR10_subread_index directory.


