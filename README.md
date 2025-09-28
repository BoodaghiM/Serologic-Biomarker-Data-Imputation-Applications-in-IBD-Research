# Serologic-Biomarker-Data-Imputation-Applications-in-IBD-Research
Glance at the files


run_imputations.ipynb – runs all imputers and writes imputed datasets (ZIPs such as MICE(PMM)_MNAR.zip, AE_MCAR.zip, …).

assessment.ipynb – computes NRMSD, Rubin-combined −log10(P), AUC, and produces statistics*.csv and figures.

Complete_dataset_CS - directory where all the complete cases are stored (unzip Complete_dataset_CS.zip to see the files)

Data_without_NANs_CS - directory where the original file Original_dataset_IU.csv from which all the missingness was created is stored

Data_with_missigness_CS - directory where all the files with missingness are located (unzip Data_with_missigness_CS.zip to see the files)


Imputed_datasets_CS - directory where all the imputed files are located (unzip all the files to see the imputated files per missingness type and imputation)




This repository focuses on imputing serologic datasets for IBD research. In this repository, we provide 3 cases (data with missingness) of the 100 cases that we used for our original study.  The main file from which we generated the files with missingness is provided (Original_dataset_IU.csv in Data_without_NANs_CS). We have created datasets with missingness (unzip the file Data_with_missingness_CS.zip in the folder ) from our original dataset (Original_dataset_IU.csv), encompassing all possible forms of missingness: MAR, MCAR, and MNAR. The notebook file Imputation_of_the_serologic_data.ipynb applies several imputation methods to address the missingness in the data. We provided all the imputed files, such as Imputed_AE_MNAR.zip and Imputed_MICE (NORM.BOOT)_MNAR.zip. Additionally, we have included the complete datasets (Complete_dataset_CS.zip) where missingness was removed instead of imputed. The file Imputation_assessment.ipynb uses direct and indirect methods to assess the performance of the imputed datasets. Indirect assessment involves statistical analysis and supervised machine learning models. To facilitate this, a phenotype file 'Phenotype_data_IU.csv' is provided for conducting various types of association analyses, including CD vs non-IBD, CD vs UC, and UC vs non-IBD. Here we have provided the imputed dataset, in case you don't want to run the imputation, use the imputed datasets
