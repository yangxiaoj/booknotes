

## VolcanoPlot



### Figure Description

A volcano plot displaying the comparison of differentially expressed genes (DEGs) between {groupA} and {groupB}. The analysis utilized a two-sided Wilcoxon rank sum test to identify significant differences. Genes are marked as regulated based on a false discovery rate (FDR) adjusted p-value of less than 0.05, along with a fold change (FC) greater than 1.2 or less than -1.2.



### Figure Results


## FigureTcellUMAP

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



## TcellSubpopulationProportionBarPlot

![](images/2024-03-30-16-51-29.png)




### Figure Description


"A heatmap delineates the expression of canonical markers across T cell subpopulations, including CD8+ T cells, CD4+ T cells, and gamma delta (γδ) T cells. This visual representation highlights the differential expression patterns of key immunological markers, providing insights into the unique functional roles and activation states of these subpopulations within the hepatocellular carcinoma (HCC) context."


### Figure Results


The differentially expressed genes (DEGs) and marker genes，asshown in the tSNE plots, confirmed the accuracy of cell identity



## TumorCellBySampleIdUMAP


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


## UMAPByScissorStatusUMAP

![](images/2024-03-31-10-21-27.png)


### Figure Description

"Uniform Manifold Approximation and Projection (UMAP) visualizations illustrate the spatial distribution of tumor cells across diverse samples, providing a high-resolution insight into the cellular heterogeneity inherent in the samples studied."


### Figure Results



 ### Results:

Uniform Manifold Approximation and Projection (UMAP) analysis revealed that tumor cell clusters exhibit a patient-specific tendency, indicating distinct cellular architectures within tumors from different individuals.

Biological Explanation:
The observed patient-specific clustering of tumor cells suggests a high degree of heterogeneity in the cellular composition of tumors from different individuals. This heterogeneity could be driven by a variety of factors, including genetic mutations, environmental influences, and differences in immune response. The unique cellular architectures within each patient's tumor underscore the complexity of cancer and the need for personalized approaches to cancer treatment. Understanding these distinct cellular landscapes is crucial for developing targeted therapies that can effectively address the specific characteristics of each patient's tumor.






![](images/2024-03-31-10-49-21.png)


### Figure Description

Scissor Status UMAP plots showing the distribution of
poorsurvival and others . 


### Figure Results



## LRTDEGsHallmarkEnrichmentDotPlot

![](images/2024-03-31-11-10-28.png)


### Figure Description

Enrichment dot plot of enriched hallmark gene sets in differentially expressed genes (DEGs) between LRT and PHT tumor cells. x-axis: gene ratio, the ratio of the number of genes in the gene set to the total number of genes in the gene set. the color represents the p adjusted value of the enrichment analysis. dot size represents the number of genes in the gene set





### Figure Results


#### Results:
Comparative analysis between late relapsed hepatocellular carcinoma (LRT) and primary hepatocellular carcinoma (PH) revealed that differentially expressed genes (DEGs) in LRT are significantly enriched in hallmark gene sets associated with oxidative phosphorylation and xenobiotic metabolism.

#### Biological Explanation:

The enrichment of DEGs in oxidative phosphorylation and xenobiotic metabolism hallmark gene sets in late-relapsed HCC underscores a metabolic adaptation that may contribute to tumor recurrence and progression. Oxidative phosphorylation is central to energy production, indicating that relapsed tumors might have an enhanced capacity for energy metabolism, possibly to meet the increased demands of rapid cell proliferation. This shift could also reflect a reliance on mitochondrial metabolism, which is often associated with drug resistance and a more aggressive tumor phenotype. On the other hand, the enrichment in xenobiotic metabolism suggests an increased ability of the tumor cells to detoxify and expel harmful substances, including chemotherapeutic drugs, which could contribute to therapeutic resistance. Together, these findings highlight the complex metabolic reprogramming that occurs in late-relapsed HCC, offering insights into potential targets for therapeutic intervention aimed at disrupting these metabolic pathways to prevent recurrence or overcome drug resistance.




## MyeloidCellOddsRatioHeatmap

![](images/2024-03-31-14-40-04.png)


### Figure Description

Figure Description:
Analysis of myeloid cell cluster distribution across different hepatocellular carcinoma (HCC) sample types, including late-relapsed normal tissue (LRN), primary hepatocellular carcinoma normal tissue (PHN), primary hepatocellular carcinoma tumor tissue (PHT), and late-relapsed tumor tissue (LRT), was performed utilizing the Ro/e metric (the ratio of observed cell number to expected cell number). This approach facilitated the identification of preferential myeloid cell cluster presence within these distinct HCC contexts, elucidating the variances in immune cell landscape associated with tumor progression and relapse.

### Figure Results

#### Results:
Our single-cell RNA sequencing analysis identified distinct immune cell subpopulations enriched in various tissue types from hepatocellular carcinoma (HCC) patients. In adjacent late-relapsed normal tissue (LRN), we observed an enrichment of Mono-like_02_CD16, DC_02_CD1C, Mono-like_01_CD14, DC_01_CLEC9A, and C_04_CD207. For primary hepatocellular carcinoma adjacent normal tissue (PHN), the enriched subpopulations include Mph_01_MARCO, Mono-like_03_CD14CD16, and Mph_02_CCL20. In primary hepatocellular carcinoma tumor tissue (PHT), we found an enrichment of Mph_03_SPP1, Mph_07_SLC40A1, and Mph_05_IL1B. Lastly, in late-relapsed hepatocellular carcinoma tumor tissue (LRT), the enriched cell subpopulations are Mph_08_APOE, Mph_06_CXCL9, and Mph_04_TREM2.

#### Biological Explanation:
The enrichment of specific immune cell subpopulations in different tissue types reflects the dynamic immune landscape associated with HCC progression and recurrence. The presence of Mono-like and DC (Dendritic Cell) subpopulations in LRN suggests an active immune surveillance mechanism in adjacent normal tissues, potentially resisting tumor invasion or recurrence. The enrichment of macrophage subpopulations (Mph) in PHN and PHT, characterized by markers such as MARCO, SPP1, and IL1B, indicates a pro-inflammatory environment that may support tumor growth and metastasis. Conversely, the distinct macrophage signatures in LRT, including APOE, CXCL9, and TREM2, point towards a unique immune microenvironment in late-relapsed tumors, possibly contributing to tumor immune evasion or modulating the response to therapy. This intricate interplay between tumor cells and the immune microenvironment underscores the necessity of considering the immune contexture in therapeutic strategies for HCC, highlighting potential targets for immunotherapy in both primary and relapsed HCC.






## NeutrophilCellUMAP

![](images/2024-03-31-15-22-21.png)


### Figure Description

The UMAP of Neutrophil cells from different Neutrophil subpopulations. Each dot represents a cell, and the color represents the subpopulation.

### Figure Results


## NeutrophilCellBySubpopulationMarkerHeatmap

![](images/2024-03-31-15-38-18.png)

### Figure Description


"A heatmap delineates the expression of canonical markers genes  across Neutrophil subpopulations. 

x-axis: canonical marker genes of Neutrophil subpopulations

y-axis: Neutrophil subpopulations

values: mean expression level of the marker genes across the Neutrophil subpopulations


### Figure Results

#### Results:
The heatmap analysis distinctly demonstrates that each neutrophil subpopulation expresses unique canonical marker genes, highlighting the presence of highly defined subpopulations within the neutrophil community.

#### Biological Explanation:
Neutrophils, traditionally viewed as a homogenous population in the context of innate immunity, actually comprise diverse subpopulations with specialized functions, as revealed by the expression of specific canonical markers. This diversity suggests a more nuanced role of neutrophils in immune responses, including inflammation, pathogen clearance, and modulation of the adaptive immune system. The identification of these subpopulations through their unique gene expression profiles indicates potential functional specialization, which could be linked to different pathways of neutrophil development, activation states, or responses to various microenvironmental cues. Understanding the complexity and functional diversity of neutrophil subpopulations opens new avenues for targeted therapeutic strategies in diseases where neutrophils play a critical role.




## NeutrophilCellOddsRatioHeatmap

![](images/2024-03-31-16-04-19.png)




