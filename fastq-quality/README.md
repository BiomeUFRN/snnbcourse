# Usando FASTQC para análise de qualidade

## Instalando FASTQC
```
$ conda install -c bioconda fastqc
```


## Donwload de um exemplo de FASTQ

```
$ wget http://data.biostarhandbook.com/data/sequencing-platform-data.tar.gz
$ tar xzvf sequencing-platform-data.tar.gz
```

## Rodar FASTQC nos exemplos

```
$ fastqc ../fastq/510-7-BRCA_S8_L001_R1_001.fastq.gz --nogroup
$ fastqc ../fastq/510-7-BRCA_S8_L001_R2_001.fastq.gz --nogroup 
```

## Caso a qualidade não esteja boa, use alguma das opções indicadas nos slides. Aqui usaremos o `cutadapt`.

```
$ conda install -c bioconda cutadapt
$ cutadapt -q 20 -o 510-7-BRCA_S8_L001_R1_001.trimmed.fastq.gz 510-7-BRCA_S8_L001_R1_001.fastq.gz
```
