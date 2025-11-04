# Clustering of chemical and toxic elements

![Made with RStudio](https://img.shields.io/badge/Made%20with-RStudio-blue?logo=rstudio)

This repository contains the **statistical report** of an observational study involving the quantification of **chemical elements and environmental compounds** in biological samples.  
All references that could identify the study, institution, cohort, or specific diagnosis, as well as any related conclusions have been removed or generalized.

## Scope

- **Objective:** Descriptive and multivariate characterization of concentrations and interrelationships among compounds (e.g., trace elements, macroelements, POPs/PCBs).  
- **Audience:** Scientific and technical teams.

## Workflow

1. **Data processing and cleaning:**
   - Data import.  
   - Variable renaming/transformation, handling of missing and outlier values.  
   - Standardization of continuous variables.  
   - Construction of correlation matrices and subset selection.  

2. **Descriptive analysis:**
   - Numerical summaries and distribution/correlation plots.  

3. **Multivariate modeling:**
   - **PCA** for latent structure exploration.  
   - **Unsupervised clustering:** hierarchical agglomerative clustering (Ward linkage with Euclidean distance; average/complete linkage with Manhattan and Canberra distances for robustness against skewness and outliers), *k*-means (initialized from Ward centroids), PAM/*k*-medoids (Manhattan), and Gaussian Mixture Models (GMM) with component and shape selection via BIC.  
   - **Cluster characterization:** for each clustering algorithm, the following were computed and reported:  
     - **Cluster size distribution**.  
     - **Defining variables per cluster**, based on mean |z|-scores. A positive z_mean indicates that a variable is elevated relative to the overall study mean, whereas a negative value indicates a decreased level; |z| reflects the magnitude of deviation.  
     - **Global ranking of variables by discriminative power**, quantified through η² (eta squared) from ANOVA tests. Variables were ordered by η² (proportion of explained variance), with F statistics summarizing between-cluster contrasts and *p* / *p_adj* (FDR) providing significance after multiple testing correction.  
     - Prioritization was based primarily on η² (effect size) and supported by *p_adj*, while the direction of the effect was interpreted using the z_mean table.  
   - **Quality metrics:** internal validity assessed by silhouette width; partition concordance by Adjusted Rand Index (ARI). A consensus label was generated. 

4. **Results communication:**
   - Tables and figures generated with `kableExtra`, `ggplot2`, and `ggpubr`.  
   - Fully reproducible document built with **RMarkdown**.  

## Main Packages
`tidyverse`, `ggplot2`, `ggpubr`, `factoextra`, `FactoMineR`, `cluster`, `mclust`, `clue`, `kableExtra`, `compareGroups`, `ggfortify`, `Hmisc`.
