
# Enrichment test for gene sets associated with a trait of interest for drugs profiled by Connectivity Map (CMAP) that act to reverse observed transcriptional changes

To run enrichment, install addR - contains all relevant functions, including dependencies for cmapr()


```
devtools::install_github("ks4471/addR")
```

gene set of interest split into up or down regulated in the phenotype of interest, if unknown, set all as up or down
```
input_gene_set=list(up=c("ABCA4","ABCG4","ACOT7","ACSM4"),down=c("AASDHPPT","ABCE1","ABHD13","ABRAXAS2"))
```

background - include all genes with a detectable signal in the experiment

```
all_genes_profiled=c("ABCA4","ABCG4","ACOT7","ACSM4","AASDHPPT","ABCE1","ABHD13","ABRAXAS2","AARS" "AARS2" "ABCE1" "ABCF1")
```

```
cnet=cmapr(modg=input_gene_set,bkg=all_genes_profiled)
write.file(cnet$pval,file='out/cmap_enrichment_results.txt')

```




# raw connectivity map CMAP data re-analysed with correction for batch and covariates
https://www.broadinstitute.org/connectivity-map-cmap
