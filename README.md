# SacCar Genome using braker1

## 17.04.2023 RepeatModeler

Build genome database for SacCar as input for RepeatModeler
```
BuildDatabase SacCar_genome.fa -name ~/repeatmodeler_database/SacCar_repeat_db
```

Runing RepeatModeler on SacCar genome 
```
nohup RepeatModeler -threads 19 -database ~/repeatmodeler_database/SacCar_repeat_db
```

## 18.04.2023

Building genome database for SemBal as input for RepeatModeler
```
BuildDatabase SemBal_genome.fa -name ~/Genomes/SemBal/repeat_modeler_db/SemBal_rmdel_db
```

```
nohup RepeatModeler -threads 19 -database ~/Genomes/SemBal/repeat_modeler_db/SemBal_rmdel_db
```



Softmasking of SacCar genome
```
nohup ~/Softwares/RepeatMasker/./RepeatMasker -s -pa 3 -lib ~/Genomes/SacCar/RM_1648467.SunApr300848432023/consensi.fa ~/Genomes/SacCar/SacCar_genome.fa -xsmall
```



Softmasking of SacCar genome










Test - 1
```
nohup braker.pl --genome ~/Genomes/SacCar/SacCar_genome_renamed_masked.fa --prot_seq /home/riwama/Genomes/SacCar/Transcriptomes/Ass/pep_transdecoder/SacCar_proteome_conc.pep --GENEMARK_PATH=/home/riwama/Softwares/gmes_linux_64 --PROTHINT_PATH=/home/riwama/Softwares/ProtHint/bin --softmasking --cores=20 --species=SacCar
```
Test - 2
```
nohup braker.pl --genome ~/Genomes/SacCar/SacCar_genome_renamed_masked.fa --prot_seq /home/riwama/Genomes/SacCar/Transcriptomes/Ass/pep_transdecoder/SacCar_proteome_conc.pep --GENEMARK_PATH=/home/riwama/Softwares/gmes_linux_64 --PROTHINT_PATH=/home/riwama/Softwares/ProtHint/bin --softmasking --cores=20 --species=SacCar --bam=/home/riwama/Genomes/SacCar/hisat_results/SacCar_alignment.out.bam --useexisting --etpmode
```


###### SacCar functional annotation using interproscan

for first 10 files
```
for file in /home/riwama/Genomes/SacCar/augustus_2nd/fasta_files/aa_divided/augustus.hints_dv.aa*; do /home/riwama/Softwares/interproscan-5.61-93.0/./interproscan.sh -cpu 5 -d /home/riwama/Genomes/SacCar/interpro -goterms -i $file; done
```

for second 10 files

```
for file in /home/riwama/Genomes/SacCar/augustus_2nd/fasta_files/aa_divided/2_run/augustus.hints_dv.aa*; do /home/riwama/Softwares/interproscan-5.61-93.0/./interproscan.sh -cpu 5 -d /home/riwama/Genomes/SacCar/interpro -goterms -i $file; done
```




