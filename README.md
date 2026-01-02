# Serologic-Biomarker-Data-Imputation-Applications-in-IBD-Research

# Glance at the files



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




# Benchmarking models for serologic data imputation

In many inflammatory bowel disease (IBD) studies, serologic biomarkers are informative but often incomplete, and missing values can quietly bias both statistics and machine-learning results. In this project, we benchmarked a range of imputation approaches, from classic multiple imputation (MICE) to iterative ML imputers and neural-network models (autoencoders and VAEs). Using three real IBD cohorts plus thousands of simulated missingness scenarios (including MCAR, MAR, and MNAR at 5–40% missingness), we compared methods based on accuracy, preservation of association signals, and downstream predictive performance. The key takeaway is practical: there is no single “best” imputer, so the right choice depends on how much data is missing and whether the goal is inference or prediction.


The serologic markers in this study capture immune responses to microbial and self antigens that are commonly altered in IBD. Together, markers such as ASCA, pANCA, anti-OmpC, anti-CBir1, and anti-I2 have been used to help distinguish IBD from non-IBD, support differentiation between Crohn’s disease (CD) and ulcerative colitis (UC), and in some settings relate to disease behavior and prognosis. Because these antibodies can carry clinically meaningful signal, handling missingness carefully is essential to avoid bias and preserve downstream interpretability. 

The study benchmarks classical statistical imputers alongside modern machine-learning and deep-learning models. Iterative methods, tree-based approaches, and autoencoders capture complementary patterns in the data. Evaluating them across diverse missingness scenarios highlights their strengths and limitations in practice.



<img width="1536" height="1024" alt="serolgy_impute" src="https://github.com/user-attachments/assets/fe6892db-07ed-4be9-a633-70e102bdf39c" />



The results show that no single imputation method works best in all situations. Simpler iterative models tend to perform well when missingness is low to moderate, while autoencoder-based approaches are more robust as missingness increases. Overall, carefully chosen imputation consistently outperforms ignoring missing data and helps preserve both statistical signal and predictive performance.



<img width="1011" height="686" alt="Screenshot 2025-12-28 at 11 28 06 PM" src="https://github.com/user-attachments/assets/e0a0a3e2-6a36-41be-a07b-3c9f166ebbd3" />

