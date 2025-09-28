# Serologic-Biomarker-Data-Imputation-Applications-in-IBD-Research
Glance at the files



.
├── run_imputations.ipynb          # run all imputers; writes ZIPs per (imputer × missingness)
├── assessment.ipynb               # compute metrics & plots; writes statistics*.csv + figures
│
├── Complete_dataset_CS/           # unzip Complete_dataset_CS.zip to view complete cases
│   └── Complete_dataset_CS.zip
│
├── Data_without_NANs_CS/          # original, fully observed dataset
│   └── Original_dataset_IU.csv
│
├── Data_with_missingness_CS/       # (typo preserved) files with synthetic missingness
│   └── Data_with_missigness_CS.zip
│
├── Imputed_datasets_CS/           # imputed outputs (per missingness type and imputer)
│   ├── Imputed_AE_MNAR.zip
│   ├── Imputed_MICE (NORM.BOOT)_MNAR.zip
│   ├── AE_MCAR.zip
│   └── ... (more)
│
└── Phenotype_data_IU.csv          # phenotype labels; join key: Genetic ID



This repository focuses on imputing serologic datasets for IBD research. In this repository, we provide 3 cases (data with missingness) of the 100 cases that we used for our original study.  The main file from which we generated the files with missingness is provided (Original_dataset_IU.csv in /Data_without_NANs_CS). We have created datasets with missingness (unzip the file Data_with_missingness_CS.zip in  /Data_with_missingness_CS) from our original dataset (Original_dataset_IU.csv), encompassing all possible forms of missingness: MAR, MCAR, and MNAR. The notebook file Imputation_of_the_serologic_data.ipynb applies several imputation methods to address the missingness in the data. We provided all the imputed files, such as Imputed_AE_MNAR.zip and Imputed_MICE (NORM.BOOT)_MNAR.zip. Additionally, we have included the complete datasets (Complete_dataset_CS.zip in /Complete_dataset_CS) where missingness was removed instead of being imputed. The file Imputation_assessment.ipynb uses direct and indirect methods to assess the performance of the imputed datasets. Indirect assessment involves statistical analysis and supervised machine learning models. To facilitate this, a phenotype file 'Phenotype_data_IU.csv' is provided for conducting various types of association analyses, including CD vs non-IBD, CD vs UC, and UC vs non-IBD. Here we have provided the imputed dataset, in case you don't want to run the imputation, use the imputed dataset
