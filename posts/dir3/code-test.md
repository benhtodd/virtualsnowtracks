---
title: Code test
order: 3
---

Revision 1

```
library(data.table)
library(tidyverse)
library(methylKit)

# 5mC
fread("~/CEG1485-EL01-D1115-005.genome.GRCh38Decoy_primary_assembly.dedup.duet-evoC.CG_quant.CXreport.txt.gz",
col.names =c('contig', 'coordinate', 'strand', 'mC', 'hmC', 'C', 'context', 'trinucleotide', 'coverage') )%>%
## Chromosome Position Strand Count methylated. Count unmethylated. C-context Trinucleotide context
select(contig, coordinate, strand, mC, C, context, trinucleotide)%>%
fwrite("~/CEG1485-EL01-D1115-005.genome.GRCh38Decoy_primary_assembly.dedup.duet-evoC.CG_quant.CXreport_reformatted_mC.txt.gz",quote = FALSE,col.names = FALSE,row.names = FALSE,sep="\t")

#. 5hmC
fread("~/CEG1485-EL01-D1115-005.genome.GRCh38Decoy_primary_assembly.dedup.duet-evoC.CG_quant.CXreport.txt.gz",
col.names =c('contig', 'coordinate', 'strand', 'mC', 'hmC', 'C', 'context', 'trinucleotide', 'coverage') )%>%
## Chromosome Position Strand Count methylated. Count unmethylated. C-context Trinucleotide context
select(contig, coordinate, strand, hmC, C, context, trinucleotide)%>%
fwrite("~/CEG1485-EL01-D1115-005.genome.GRCh38Decoy_primary_assembly.dedup.duet-evoC.CG_quant.CXreport_reformatted_hmC.txt.gz",quote = FALSE,col.names = FALSE,row.names = FALSE,sep="\t")

##Read the reformatted files in methylkit
myobj<-methRead(list('~/CEG1485-EL01-D1115-005.genome.GRCh38Decoy_primary_assembly.dedup.duet-evoC.CG_quant.CXreport_reformatted_mC.txt.gz',
'~/CEG1485-EL01-D1115-005.genome.GRCh38Decoy_primary_assembly.dedup.duet-evoC.CG_quant.CXreport_reformatted_hmC.txt.gz'),
sample.id=list("mC","hmC"),
assembly="hg38",
treatment=c(0,0),
context="CpG",
mincov = 10,
pipeline='bismarkCytosineReport'
)
#Make the plots
getMethylationStats(myobj[[1]],plot=TRUE,both.strands=FALSE)
getMethylationStats(myobj[[2]],plot=TRUE,both.strands=FALSE)
```
