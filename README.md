# Hackbio_Transcriptomics
Welcome to the Hackbio Transcriptomics biostack repository



RNA-Seq Analysis Using Galaxy

In this tutorial we identified genes and pathways regulated by the Pasilla gene (the Drosophila homologue of the mammalian splicing regulators Nova-1 and Nova-2 proteins) using RNA-Seq data generated by Brooks et al. 2011.

We compared the genes expression in; 

4 untreated samples: GSM461176, GSM461177, GSM461178, GSM461182

3 treated samples (Pasilla gene depleted by RNAi): GSM461179, GSM461180, GSM461181

Method

## 1. Dataset upload into Galazy
## 2. Quality Control : FastQC and Cutadapt
## 3. Mapping: RNA STAR visualized using IGV
## 4. Quantification: featureCounts
## 5. Differential Expression: Deseq2-read count,normalize and extract differentially expressed genes. (Heatmap2-for visualization)

## 6. Fuctional Enrichment Analysis using goseq

### Gene Ontology analysis
    
Once we have obtained the list of differentially expressed genes between the Drosophila Wildtype and PasillaDepleted samples, the aim is to find out which biological      processes are most affected by these genes. For this purpose, using Galaxy's goseq tool, we performed a gene ontology (GO) analysis for three types of ontology: 
- MF (Molecular Function - molecular activities of gene products)
- CC (Cellular Component - where gene products are active)
- BP (Biological Process - pathways and larger processes made up of the activities of multiple gene products)
    
As in the tutorial, we obtained 31 over-represented Go terms (0.27%) and 83 under-represented Go terms (0.72%) (P-value < 0.05).

Over-represented GO terms:
![image](https://user-images.githubusercontent.com/92274646/139449957-a00378fd-9b84-4910-b2e2-5fa7cc57b76a.png)

Under-represented Go terms:
![image](https://user-images.githubusercontent.com/92274646/139451652-1d8d6aaf-8dab-478c-a05b-b736f2a4604e.png)
(continue...)

In addition, the analysis also returns a graph showing the most over-represented GO categories. In this graph, we observe that more than 60% of the genes of the "blood-brain barrier establishment" caterogy have been identified as differentially expressed. Furthermore, the graph ranks the GO terms according to how significant their involvement is (starting with those with a lower Adj P value). Finally, the larger the size of the circle, the greater the number of genes involved. 

![image](https://user-images.githubusercontent.com/92274646/139452867-5333a357-a0cf-4eef-bb52-864314580dc4.png)

To complete the GO analysis, goseq also provides a list of the genes involved in each GO term in tabular format:
![image](https://user-images.githubusercontent.com/92274646/139453243-4017b1ae-f5f7-43d0-816a-bbcef0bd2d3c.png)

### KEGG Pathway analysis

