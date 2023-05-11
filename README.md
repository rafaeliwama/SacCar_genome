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

## 18.04.2023 repeat modeler for SemBal

Building genome database for SemBal as input for RepeatModeler
```
BuildDatabase SemBal_genome.fa -name ~/Genomes/SemBal/repeat_modeler_db/SemBal_rmdel_db
```

```
nohup RepeatModeler -threads 19 -database ~/Genomes/SemBal/repeat_modeler_db/SemBal_rmdel_db
```

## 03.05.23 Softmasking of SacCar e SemBal genome

SacCar genome

```
nohup ~/Softwares/RepeatMasker/./RepeatMasker -s -pa 3 -lib ~/Genomes/SacCar/RM_1648467.SunApr300848432023/consensi.fa ~/Genomes/SacCar/SacCar_genome.fa -xsmall
```

SemBal genome

```
nohup ~/Softwares/RepeatMasker/./RepeatMasker -s -pa 3 -lib /home/riwama/Genomes/SemBal/RM_2742576.TueApr252054222023/consensi.fa ~/Genomes/SacCar/SacCar_genome.fa -xsmall
```

## 04.05.23 braker structural annotation of SacCar genome

Braker2 run on SacCar genome using protein sequences predicted from transcriptomes
```
nohup braker.pl --genome ~/Genomes/SacCar/SacCar_genome.fa.masked --prot_seq /home/riwama/Genomes/SacCar/Transcriptomes/Ass/pep_transdecoder/SacCar_proteome_conc.pep --GENEMARK_PATH=/home/riwama/Softwares/gmes_linux_64 --PROTHINT_PATH=/home/riwama/Softwares/ProtHint/bin --softmasking --cores=10 --species=SacCar --gff3 --useexisting
```

Braker2 run on SemBal genome using protein sequences predicted from transcriptomes
```
nohup braker.pl --genome /home/riwama/Genomes/SemBal/SemBal_genome.fa.masked --prot_seq /home/riwama/Genomes/SemBal/Transcriptomes/pep/SemBal_transcriptomes_pep_conc.fa --GENEMARK_PATH=/home/riwama/Softwares/gmes_linux_64 --PROTHINT_PATH=/home/riwama/Softwares/ProtHint/bin --softmasking --cores=10 --species=SemBal --gff3 --useexisting
```

## 06.05.2023 Functional annotation

# interproscan - SacCar
```
for file in SacCar_genome_augustus*;do ~/Softwares/interproscan-5.61-93.0/interproscan.sh -cpu 10 -i $file -goterms $file.interpro; done
```



## 11.05.2023 RepeatModeler on PlatSpe

Building PlatSpe RepeatModeler database
```
/Softwares/RepeatModeler/./BuildDatabase PlatSpe_genome_renamed.fa -name /home/riwama/Genomes/PlatSpe/RepeatModeler/PlatSpe_RepeatModeler_db
```

Running RepeatModeler
```
nohup ~/Softwares/RepeatModeler/./RepeatModeler -threads 19 -database /home/riwama/Genomes/PlatSpe/RepeatModeler/PlatSpe_RepeatModeler_db
```









