# Project-Winland
Repository for all code related to Project Winland 

## PCA replication

### UK_Filter, merge_chrom.sh, flashPCA.sh 
These files are necessary to run flashPCA with chromosomes 1-22. Further instructions on these files can be found in the UKBiobank preprocessing document

### ukb_download :
this file must be editited based on your application number <appNum>, ukbkey sent in the email from ukbiobank with the MD5 hash
  
### visualize.py : 
 visualize.py and visualizePCA.py
  
## StructLMM 
The StructLMM method is taken from the original paper (Moore 2018) [^1]
from repo: https://github.com/limix/struct-lmm

### winland-structlmm.py
The Winland Project can run 3 analyses: random, pseudo, research 
- random : uses random data generated by the Random module
- pseudo: uses pseudo data from LMM documentation
- research: uses data from real UKBiobank variables

Requires python3.9
`usage: python winland-structlmm <research | pseudo | random> [...path]`

  - random_analysis: uses randomly generated data created using the python Random library
  - example_analysis: uses [pseudo data](https://github.com/limix/limix-lmm/tree/0f0a9875e6d0ed0511db54c911992332b76baa13/doc/data_structlmm) referenced in structlmm [documentation](https://buildmedia.readthedocs.org/media/pdf/struct-lmm/stable/struct-lmm.pdf)
  - init_analysis: uses data from the ukbiobank to analysis interaction & association tests for the height variable (UK biobank field ID 50) 
  - mygaussianize: modified function from [gaussianize](https://github.com/limix/limix-core/blob/master/limix_core/util/preprocess.py#L64) 
  - remove_withdraws: removes subjects that have rescinded their data to the UK biobank
  - make_df_dict(path , li) : internal function to convert file paths to dataframes 
  - clean_data: cleans data for the research analysis 
  
[^1] : Moore, R., Casale, F. P., Bonder, M. J., Horta, D., Franke, L., Barroso, I., & Stegle, O. (2018).[ A linear mixed-model approach to study multivariate gene–environment interactions](https://www.nature.com/articles/s41588-018-0271-0) (p. 1). Nature Publishing Group.
