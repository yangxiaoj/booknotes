

## VolcanoPlot



### Figure Description

A volcano plot displaying the comparison of differentially expressed genes (DEGs) between {groupA} and {groupB}. The analysis utilized a two-sided Wilcoxon rank sum test to identify significant differences. Genes are marked as regulated based on a false discovery rate (FDR) adjusted p-value of less than 0.05, along with a fold change (FC) greater than 1.2 or less than -1.2.



### Figure Results


![](images/2024-03-30-16-12-22.png)

### Figure Description

Uniform Manifold Approximation and Projection (UMAP) visualizations delineate the distinct subpopulations within T cells, including CD8+ T cells, CD4+ T cells, and gamma delta (γδ) T cells.






### Figure Results 

Results:

Through our comprehensive multi-omic analysis focusing on the single-cell architecture of late-relapsed hepatocellular carcinoma (HCC), we identified significant heterogeneity within the immune cell populations. The single-cell RNA sequencing (scRNA-seq) data revealed distinct subpopulations among T cells, characterized as CD4+ T cells, CD8+ T cells, and gamma delta (γδ) T cells, across both primary and late-relapsed HCC samples. Similarly, the single-cell ATAC sequencing (scATAC-seq) data provided insights into the chromatin accessibility landscape, underscoring the epigenetic variations that accompany the transcriptional diversity observed in T cell subpopulations. Notably, the late-relapsed HCC samples exhibited a unique immune cell composition and activation state, suggesting an adapted immune microenvironment in response to the recurrent tumor challenge.


Biological Explanation:

The distinct subpopulations of T cells identified in late-relapsed HCC samples highlight the complexity of the tumor microenvironment and its evolution over time. CD4+ T cells, known for their helper functions, and CD8+ T cells, recognized for their cytotoxic activities, along with γδ T cells, which play roles in both innate and adaptive immunity, exhibit specific transcriptional and epigenetic profiles suggesting their unique roles in the immune response to late-relapsed HCC. The observed heterogeneity implies a nuanced immune landscape that evolves in response to the tumor's recurrence, potentially influenced by previous treatments and the tumor's acquired mutations. This adaptation might reflect the immune system's attempt to control tumor growth, despite the challenges of overcoming immune evasion tactics developed by the tumor. Understanding these dynamics is crucial for developing effective therapeutic strategies targeting the immune system's interaction with late-relapsed HCC, highlighting the importance of personalized medicine approaches in treating complex cancers.


### Figure Methods 


"To investigate the diversity and distribution of T cell subpopulations within hepatocellular carcinoma (HCC), we employed Uniform Manifold Approximation and Projection (UMAP) for dimensionality reduction and visualization. This analysis facilitated the identification and representation of distinct T cell subsets, specifically CD8+ T cells, CD4+ T cells, and gamma delta (γδ) T cells, across the collected HCC samples. UMAP plots were generated to illustrate the intricate patterns of these subpopulations, offering insights into their spatial distribution and relative abundance."





![](images/2024-03-30-16-51-29.png)




### Figure Description


"A heatmap delineates the expression of canonical markers across T cell subpopulations, including CD8+ T cells, CD4+ T cells, and gamma delta (γδ) T cells. This visual representation highlights the differential expression patterns of key immunological markers, providing insights into the unique functional roles and activation states of these subpopulations within the hepatocellular carcinoma (HCC) context."


### Figure Results


The differentially expressed genes (DEGs) and marker genes，asshown in the tSNE plots, confirmed the accuracy of cell identity






![](images/2024-03-31-09-28-07.png)


### Figure Description

"A stacked bar plot illustrates the proportional distribution of major T cell subsets across different tissue types, including primary hepatocellular carcinoma, late-relapsed hepatocellular carcinoma, and their adjacent normal tissues. "


### Figure Results 

### Results:
Our analysis revealed distinct immune cell type distributions across various tissue types in hepatocellular carcinoma (HCC). Specifically, the subpopulations CD8T_08_GZMK and CD4T_10_FOXP3_CTLA4 were found to be significantly enriched in late-relapsed tumor (LRT) and primary hepatocellular carcinoma tumor (PHT) tissues. Conversely, these subpopulations were less prevalent in adjacent normal liver tissues (LRN and PHN). In contrast, the subpopulations CD8T_11_SLC4A10 and gamma delta T (gdT_03_KLRD1) cells exhibited higher frequencies in normal liver tissues (LRN and PHN) compared to their presence in LRT and PHT samples.

### Biological Explanation:
The observed distribution patterns of immune cell subpopulations across different tissue types shed light on the complex immune landscape of HCC and its recurrence. The enrichment of CD8T_08_GZMK and CD4T_10_FOXP3_CTLA4 subpopulations in tumor tissues (LRT and PHT) suggests a heightened immune response or regulatory T cell activity within the tumor microenvironment, potentially contributing to tumor immune evasion or suppression of anti-tumor immunity. These subpopulations are known for their roles in cytotoxicity (GZMK-expressing CD8+ T cells) and immune regulation (FOXP3+CTLA4+ CD4+ Tregs), highlighting their significance in the context of tumor immunology.

Conversely, the increased presence of CD8T_11_SLC4A10 and gdT_03_KLRD1 cells in normal adjacent liver tissues points to a distinct immune setting outside the tumor microenvironment, possibly reflecting a state of surveillance or readiness to respond to malignant cells. Gamma delta T cells (gdT), in particular, are recognized for their potent antitumor activity and can serve as an important line of defense against tumor development and progression.

These findings underscore the dynamic interplay between tumor cells and the immune system in HCC, revealing how immune cell compositions differ markedly between tumor and normal tissues. This heterogeneity within the immune landscape offers critical insights into mechanisms of tumor immune evasion, the role of specific T cell subpopulations in cancer immunity, and potential targets for immunotherapy in HCC.




![](images/2024-03-31-10-21-27.png)


### Figure Description

"Uniform Manifold Approximation and Projection (UMAP) visualizations illustrate the spatial distribution of tumor cells across diverse samples, providing a high-resolution insight into the cellular heterogeneity inherent in the samples studied."


### Figure Results



 ### Results:

Uniform Manifold Approximation and Projection (UMAP) analysis revealed that tumor cell clusters exhibit a patient-specific tendency, indicating distinct cellular architectures within tumors from different individuals.

Biological Explanation:
The observed patient-specific clustering of tumor cells suggests a high degree of heterogeneity in the cellular composition of tumors from different individuals. This heterogeneity could be driven by a variety of factors, including genetic mutations, environmental influences, and differences in immune response. The unique cellular architectures within each patient's tumor underscore the complexity of cancer and the need for personalized approaches to cancer treatment. Understanding these distinct cellular landscapes is crucial for developing targeted therapies that can effectively address the specific characteristics of each patient's tumor.


