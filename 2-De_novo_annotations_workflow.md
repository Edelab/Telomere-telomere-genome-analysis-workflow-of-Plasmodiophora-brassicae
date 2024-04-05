# De novo annotations of _P_. _brassicae_ genome assembly using BRAKER3 pipeline

1. **Repeat content prediction and soft-masking** 
   
# Repeat content prediction by RepeatModeller

Repeat content prediction along genome assembly was carried out using RepeatModeller using Galaxy_Europe plateform [Link](https://usegalaxy.eu/)

# Soft-masking of repeat region using RepeatMasker

Predicted repeat content was softmasked using RepeatMasker using Galaxy_Europe plateform [Link](https://usegalaxy.eu/)

2. **De novo annotations using BRAKER3**

```
singularity exec braker3.sif braker.pl --genome=genome_masked.fa --species=pb 

     --prot_seq=proteins.fa  --rnaseq_sets_ids=S001A93_ID1,S001E7A_ID2,21dpi_ID3,7dpi_ID4 \

        --rnaseq_sets_dirs=./rnaseq  --threads 20 --busco_lineage eukaryota_odb10 &> pb3a.log
```
**Paramters Note:**

 1. ```--genome=genome_masked.fa``` stands for the repeat contents masked fasta file of final genome assembly

 2. ```--species=pb```

3. ```--prot_seq=proteins.fa``` reference _Pb_ proteome file  

4. ```--rnaseq_sets_ids=S001A93_ID1,S001E7A_ID2,21dpi_ID3,7dpi_ID4``` RNA seq data of 4 time points (7, 16, 21, 26 dpi)

5. ```--rnaseq_sets_dirs=./rnaseq``` 


