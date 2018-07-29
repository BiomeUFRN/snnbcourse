# Anotação das variantes chamadas pelo Freebayes utilizando SnpEff

* Olhar o [manual](http://snpeff.sourceforge.net/SnpEff_manual.html#cmdline);

## Fazer a instalação do SnpEff, além dele também é necessário ter o java jvm instalado.

```
$ conda install -c bioconda snpeff
$ conda install -c cyclus java-jdk
```

## Fazer download das anotações referentes ao genoma GRCh37

```
$ snpEff download GRCh37.75
```

> Para saber mais sobre os bancos disponíveis:

```
$ snpEff databases | grep GRCh37
```

> Ignorar o código a partir do pipe se quiser ver tudo disponível

## Rodar o SnpEff

```
$ snpEff -Xmx4G -spliceSiteSize 10 -v GRCh37.75 ../04_chamada-de-variante/510-7-BRCA_S8.vcf > 510-7-BRCA_S8.anno.vcf
```

> O parâmetro `-spliceSiteSize 10` identifica as regiões +10 e -10 como sendo regiões de splicing.

> Ficar de olho na memória requerida, isso pode acarretar erro ao rodar e não ter memória suficiente para que funcione.

## Opicional - Para anotar outros bancos de dados é preciso usar o SnpSift

```
$ conda install -c bioconda snpsift
```

> Ver o [manual](http://snpeff.sourceforge.net/SnpSift.html#intro) caso queira anotar preditores, bancos de frequência populacional, intervalos de interesse, etc.
