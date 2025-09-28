# Serologic-Biomarker-Data-Imputation-Applications-in-IBD-Research
Glance at the files



run_imputations.ipynb – runs all imputers and writes imputed datasets (ZIPs such as MICE(PMM)_MNAR.zip, AE_MCAR.zip, …). 

assessment.ipynb – computes NRMSD, Rubin-combined −log10(P), AUC, and produces statistics*.csv and figures. 

Complete_dataset_CS - directory where all the complete cases are stored (unzip Complete_dataset_CS.zip to see the files) 

Data_without_NANs_CS - directory where the original file Original_dataset_IU.csv from which all the missingness was created is 

stored Data_with_missingness_CS - directory where all the files with missingness are located (unzip Data_with_missingness_CS.zip to see the files) 

Imputed_datasets_CS - directory where all the imputed files are located (unzip all the files to see the imputed files per missingness type and imputation) 

Phenotype_data_IU.csv - contains the current diagnosis information (use Genetic ID to map to serology data)





This repository contains pipelines and data for imputing serologic datasets in IBD research. It includes 3 example missingness cases (out of the original 100 used in our study) generated from the fully observed source file Data_without_NANs_CS/Original_dataset_IU.csv. Synthetic missingness covers MCAR, MAR, and MNAR (unzip Data_with_missigness_CS/Data_with_missigness_CS.zip to access them).

Use run_imputations.ipynb to apply multiple imputation methods (e.g., MICE variants, Autoencoder) and write imputed archives (e.g., Imputed_AE_MNAR.zip, Imputed_MICE (NORM.BOOT)_MNAR.zip) into Imputed_datasets_CS/.

For a complete-case alternative (rows with any missing values removed), unzip Complete_dataset_CS/Complete_dataset_CS.zip.

Evaluate imputations with assessment.ipynb, which performs direct (e.g., NRMSD) and indirect assessments (statistical tests and supervised ML; reports AUC and Rubin-combined −log10(P)).

A phenotype file, Phenotype_data_IU.csv, is provided for downstream association analyses (CD vs non-IBD, CD vs UC, UC vs non-IBD). Join using Genetic ID.

Don’t want to rerun imputations? You can directly use the datasets in Imputed_datasets_CS/ (unzip first).
