# DryNetMC
Differential Regulatory Network-based Modeling and Characterization (DryNetMC) for Cancer Drug Resistance 

--Modeling and characterization of the dynamic gene regulatory networks underlying cancer drug resistance based on time course RNA-seq data



--- Work protocol---


The main codes were implemented in R (R version 3.5.1). The pipeline can be run in the following order:

1.	DEG.R

This piece of code performs analyzing conventional differentially expressed genes (DEGs) and temporally changing genes (TCGs) defined in our study, as well as normalization and heat map visualization. The following R packages are required to be installed: “plotrix”, "gplots", and “pheatmap”.  



2.	Clustering_visualization.m

This piece of code performs clustering and visualizing TCGs. 

3.	CorrelationNetwork.R

This piece of code performs constructing initial PPI networks and correlation networks. The following R packages should be installed: "ggm" and "ppcor".

4.	ODENet_Sensitive.R and ODENet_Resistant.R

This piece of code performs dynamic network reconstruction for sensitive cells or resistant cells. The output is a gene interaction matrix which is reformed for Cytoscape visualization. The following R packages should be installed:  "iterators" and " pracma".  


5.	Differential_Network.R 

This piece of code performs differential network analysis, visualization, and characterization (quantifying topological hubs, adaptation dynamics and local network entropy). The following R packages are required to be installed: “igraph” and "vioplot".

6.	FB_Motif_Detection.R

This piece of code detects various types of 2-node and 3-node feedback motifs in the sensitive network and resistant network. 

7.	PatternSimilarity.R

This piece of code performs calculation and comparison of the distance between the tested cell line and the sensitive or resistant cell line. The following R packages are required to be installed: “dtw” and "vioplot".  ‘PatternSimilarity.m’ can be alternatively used.

8.	DryNB_Survival.R

This piece of code performs D2NB identification, differential expression analysis of the identified genes and K-M analysis. The following R packages are required to be installed: "AnnotationDbi", "bit", “org.Hs.eg.db", "lattice", "survival", "reshape2", "data.table", "zoo", "survminer", "survival", "glmnet" and "pROC".  

9.	Validation_Network.R

This piece of code performs validation of the dynamic network reconstruction method based on a synthetic dataset in comparison to the following methods: PCC-based correlation network method (PCCNet), tree-based ensemble learning methods (GENIE3), the state-of-the-art ODE-LASSO method (OdeLasso), the method incorporating prior information (OdeLassoP) and a dynamic Bayesian network method (GRENITS). The following R packages are required to be installed: “pracma”, “glmnet” , "GRENITS" and “ROCR”. "ODE_coefficients.csv" used for generating sythetic data has been uploaded as well. 

10.	Validation_Network_MoreDatasets.R

This piece of code performs validation of the dynamic network reconstruction method based on 100 sets of synthetic dataset in comparison to the following methods: PCC-based correlation network method (PCCNet), tree-based ensemble learning methods (GENIE3), the state-of-the-art ODE-LASSO method (OdeLasso), the method incorporating prior information (OdeLassoP) and a dynamic Bayesian network method (GRENITS). The following R packages are required to be installed: “pracma”, “glmnet” , "GRENITS" and “ROCR”. "ODE_coefficients.csv" used for generating sythetic data has been uploaded as well. 
.R

11. Comparison_TemporalPatternBiomarker.R

This piece of code performs comparison of the effectiveness of the top 5 genes prioritized by the DryNetMC with that by other methods, including DEseq2 and GSNCA. This piece of code also performs Significance test of DryNetMC using a bootstraping appraoch. The following R packages are required to be installed: “DESeq2”, "dtw", and “GSAR”. 



The case study gene expression data are saved in “GBM_gene_RPKM.csv”. The file path in the codes for loading this dataset should be customized to the working folder.  

The above codes correspond to the following figures in the paper "Differential regulatory network-based quantification and prioritization of key genes underlying cancer drug resistance based on time-course RNA-seq data":

1.	DEG.R -- for Fig 2, Fig S2

2.	Clustering_visualization.m -- for Fig 2


3.	CorrelationNetwork.R -- for Fig 3

4.	ODENet_Sensitive.R and ODENet_Resistant.R  -- for Fig 3, Fig S5

5.	Differential_Network.R  -- for Fig 3, Fig 4, Table S1

6.	FB_Motif_Detection.R  -- for Fig 4

7.	PatternSimilarity.R  -- for Fig 6, Fig S8

8.	DryNB_Survival.R -- for Fig 5

9.	Validation_Network.R -- for Fig S3

10.	Validation_Network_MoreDatasets.R -- for Fig S4

11. Comparison_TemporalPatternBiomarker.R -- for Fig 7, Fig S9


