# Hypoxia Classifier

This repository contains supplementary data for the paper "Hypoxia classifier for transcriptome datasets" ([10.1101/2021.11.15.468572](https://www.biorxiv.org/content/10.1101/2021.11.15.468572v1) ) 

* **Tree_collection.RData** : Collection of 276 *rpart* decision trees.
* **Validation_datasets.RData**: list of four validation datasets:
    *  "clearCellRenalCarcinoma": 90 paired samples of ccRCC and healthy adjacent tissue from TCGA-KIRK and GSE102101.
    *  "mouse": 34 paired samples of mouse cells grown in normoxic or hypoxic conditions
    *  "timeSeries": 45 samples of HUVEC cells grown at different O2% concentrations (0%, 1%, 3%, 5%, 21%) for several timespans (1h, 2h, 3h, 5h, 7h, 9h, 12h, 24h, and 48h)
    *  "RNAfractions": 22 paired samples of specific RNA fractions (newly transcribed, actively translated) from human cells grown in normoxic or hypocix conditions.

Each of the elements of the **Validation_datasets.RData** list contains a metadata table with information on each RNA-seq sample and a gene expression matrix. 
Gene expression is quantified as a ranking percentile, with 100 being the most expressed gene in the sample, and 0 the least.

* **GeneExpression_example.RData**: gene expression matrix (in pseudocounts), output from [salmon](https://salmon.readthedocs.io/en/latest/) corresponding to [GSM2390150](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSM2390150), an RNA-seq of HUVEC cells grown in hypoxia for 8h.
* **Tutorial.pdf**: Step by step guide to classify a gene expression profile using one of the decision trees.
* **classification_TCGA.RDS**: classification of 8520 samples from TCGA. This object contains a list of 19 data frames, one for each tumor major primary site. In every data frame each row represents a sample, and columns contain "sample ID", "patient ID", and the class assigned by each of the 276 decision trees in the collection.
