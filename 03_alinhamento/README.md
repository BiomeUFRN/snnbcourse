# Tutorial simplificado para alinhamento

* Primeiramente organize o genoma de referência que será utilizado (caso não, veja o tutorial "genoma-referencia.md" nessa mesma pasta)

## Instalar BWA e Samtools;

```
$ conda install -c bioconda bwa samtools -y
```

## Vá para a pasta `SAM-BAM` e de lá rode o BWA para alinhar os FASTQs e criar o arquivo SAM;

```
$ bwa mem $REF $R1 $R2 > bwa.sam
```

> Existem vários alinhadores, para diferentes propósitos. Se quiser saber mais sobre eles [clique aqui](https://en.wikibooks.org/wiki/Next_Generation_Sequencing_(NGS)/Alignment)

## Transformar um arquivo SAM para BAM usando `samtools`, seguido pela indexação do arquivo;

```
$ samtools sort bwa.sam > bwa.bam
$ samtools index bwa.bam
```

## Alinhando com um único comando sem criar arquivo SAM e passando os resultados diretamente para o arquivo BAM;

```
$ bwa mem $REF $R1 $R2 | samtools sort > bwa.bam
$ samtools index bwa.bam
```

