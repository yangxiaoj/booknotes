Manucript




In this study, we collected 22 pairs of fresh, surgically removed tumors and corresponding adjacent tissues from patients diagnosed with primary hepatocellular carcinoma (HCC) and those with late relapse of the disease. These patients exhibited no signs of recurrence for a minimum period of two years following their initial surgical intervention. The primary aim was to delineate the distinctive cellular components characterizing late-relapsed HCC (LRT). For each sample, cells expressing $\mathrm{CD} 45^{+}$ were isolated using fluorescence-activated cell sorting, with subsequent samples mixed in a ratio of 2:1 for further examination. Our analysis encompassed droplet-based single-cell RNA sequencing (scRNA-seq), single-cell T cell receptor sequencing (scTCR-seq), and single-cell Assay for Transposase-Accessible Chromatin sequencing (scATACseq) on eleven primary HCC tumors (PHT) and seven LRT samples. Concurrently, we applied scRNA-seq and scTCRseq to the adjacent normal samples from both PHT and LRT groups, hereafter referred to as PHN and LRN, respectively. Furthermore, we conducted bulk whole-exome sequencing (WES) and RNA sequencing (RNA-seq) on both tumor samples and adjacent normal tissues to identify the genomic and transcriptomic alterations typically observed in HCC.

Our scRNA-seq analysis covered a total of 387,566 cells, with a specified percentage derived from PHT, LRT, PHN, and LRN groups. Through the application of graph-based uniform manifold approximation and projection (UMAP), we identified several highly-confident cell clusters corresponding to known cell lineages.

The study identified six principal cell types based on the canonical gene expression profiles, namely:

1. Myeloid cells, characterized by the expression of CD4, CD14, CD68, CD163, LAMP3, TPSAB1, CSF3R, S100A8.
2. T cells, identified through CD3D, CD8A, FOXP3 expression.
3. Natural killer (NK) cells, marked by NKG7 expression.
4. B cells, defined by CD79A, MS4A1, CD1C expression.
5. Tumor cells, expressing ALB and EPCAM.
6. Stromal cells, with VWF and COL1A1 as their markers.

This analysis also highlighted distinct compositions of infiltrating immune cells within the tumor microenvironment (TME) of PHT, LRT, and their respective adjacent normal tissues. We discerned 28 subpopulations of T cells, 4 subpopulations of B cells, 7 subpopulations of NK cells, and 21 subpopulations of myeloid cells. Moreover, 17 subpopulations of stromal cells were identified.

The cellular compositions, including the common and specific markers of each cell type, were visualized in a heatmap. The detailed fraction and comparison of immune cell types across different disease states and individual patients were further elucidated.



### SUGGESTIONS:

To enhance the manuscript, the following improvements are recommended:

1. **Quantitative Analysis:** Provide a more detailed quantitative analysis of the cell count differences among PHT, LRT, PHN, and LRN groups. This could involve statistical tests to highlight significant variations.
2. **Data Visualization:** Incorporate additional figures or tables to visually represent the distribution and frequency of the identified cell types across different sample groups. This will aid in the clearer interpretation of the results.
3. **Methodological Clarity:** Ensure that the methods section clearly delineates the procedures for cell isolation, sequencing, and analysis. This detail is crucial for reproducibility and scientific rigor.
4. **Discussion on Biological Significance:** Expand the discussion section to interpret the biological significance of the observed differences in cell compositions. How do these differences contribute to our understanding of HCC progression or recurrence?
5. **Comparative Analysis with Existing Literature:** Situate the study findings within the broader context of existing research on HCC. This comparison could highlight novel contributions or corroborate existing knowledge.

### IMPORTANT RESULTS OR CONCLUSION:

A pivotal conclusion from this study is the identification of distinct cellular compositions within the tumor microenvironment of primary and late recurrent hepatocellular carcinoma, facilitated by high-resolution single-cell RNA sequencing. The delineation of specific cell types and their subpopulations, particularly immune and stromal cells, across different disease states (PHT, LRT) and adjacent normal tissues (PHN, LRN) underscores the heterogeneity of the tumor

 microenvironment and its potential implications for disease progression, recurrence, and therapeutic targeting.




# Cancer cells
Cancer cells in LRT exhibited significant immune evasion characteristics
1. cancer cells immune evasion characteristics
2. cancer cells survival signature identification



## 1

In the study, differential gene expression analysis was conducted on single-cell RNA sequencing data from primary and late relapsed hepatocellular carcinoma tissues and their adjacent normal tissues. The enrichment dot plot highlights significant pathways in the primary hepatocellular carcinoma tumor (PHT) and the late relapsed hepatocellular carcinoma tumor (LRT) groups through the investigation of differentially expressed genes (DEGs).

For the PHT group, the analysis revealed a pronounced enrichment in several key cellular pathways including the Interferon Gamma Response, TNFα Signaling via NFκB, the p53 Pathway, Allograft Rejection, and the Complement System. These pathways are indicative of a heightened immune response, stress signaling, and tumor surveillance mechanisms in primary hepatocellular carcinoma tumors.

Conversely, the LRT group showed enrichment in pathways such as Oxidative Phosphorylation, Xenobiotic Metabolism, and Hypoxia. This suggests a metabolic adaptation of the cancer cells in late relapsed tumors, which may contribute to tumor progression and resistance to therapy by enhancing energy production, metabolizing drugs and other foreign compounds, and surviving in low-oxygen conditions.

## 2

The boxplot analysis, employing Manhattan distances to assess the similarity between patient-matched samples, reveals insightful contrasts across different hepatocellular carcinoma (HCC) stages and tissue types. Specifically, when examining single-cell RNA sequencing (scRNA-seq) and single-cell ATAC sequencing (scATAC-seq) data, distinct patterns emerge.

For the scRNA-seq group, we analyzed primary hepatocellular carcinoma tumor (PHT) data and its adjacent normal tissue (PHN), alongside late relapsed hepatocellular carcinoma tumor (LRT) data and its adjacent normal tissue (LRN). Similarly, in the scATAC-seq group, primary hepatocellular carcinoma tumor (PH) data and late relapsed tumor (LR) data were evaluated.

The boxplot centered on Euclidean distances distinctly shows that the Euclidean distance between the primary hepatocellular carcinoma tumor (PHT) and its adjacent normal tissue (PHN) is significantly larger compared to the Euclidean distance between the late relapsed tumor (LRT) and its adjacent normal tissue (LRN). This indicates a greater divergence in gene expression and chromatin accessibility patterns between the tumor and normal tissue in primary HCC compared to the late relapsed stage.

## 3

Comparative analysis between late relapsed hepatocellular carcinoma (LRT) and primary hepatocellular carcinoma (PH) revealed that differentially expressed genes (DEGs) in LRT are significantly enriched in hallmark gene sets associated with oxidative phosphorylation and xenobiotic metabolism.



## 4



In our analysis, we focused on the expression levels of genes that were identified as upregulated in Scissor+ cells, which are associated with poor survival outcomes. The violin plots generated from our single-cell RNA sequencing data reveal a distinct expression pattern for these genes across different groups. Notably, we found a significantly higher expression of these selected genes in the primary hepatocellular carcinoma tumor (PHT) group compared to the late relapsed hepatocellular carcinoma tumor (LRT) group. This observation suggests a differential regulatory landscape in primary versus late-stage relapsed tumors, which may underlie the aggressive nature and poor prognosis associated with Scissor+ cells in primary tumors.

## 5



Our single-cell RNA sequencing (scRNA-seq) and single-cell ATAC sequencing (scATAC-seq) analysis of primary hepatocellular carcinoma (HCC) and late-relapsed HCC revealed distinct immune cell compositions across different tissue samples. In late-relapsed normal adjacent tissue (LRN), we observed a significant enrichment of immune cell subtypes such as Mono-like_02_CD16, Mph_01_MARCO, DC_02_CD1C, Mono-like_01_CD14, DC_01_CLEC9A, DC_05_LILRA4M, Mo_02_CD16, DC_04_CD207, Mo_01_CD14, and DC_06_STMN1. Notably, Mo_02_CD16, DC_04_CD207, and Mo_01_CD14 showed a particularly high enrichment in LRN compared to other groups. In primary HCC normal adjacent tissue (PHN), cell subtypes including Mono-like_03_CD14CD16 and Mph_02_CCL20 were distinctly enriched, with Mono-like_03_CD14CD16 and Mph_02_CCL20 showing a specific enhancement. The primary hepatocellular carcinoma tumor (PHT) displayed a notable enrichment for Mph_O8_APOE, Mph_06_CXCL9, Mph_03_SPP1, Mph_O7_SLC40A1, Mph_05_IL1B, and Mph_09_STMN1, with Mph_03_SPP1, Mph_O7_SLC40A1, Mph_05_IL1B, and Mph_09_STMN1 being particularly abundant. Meanwhile, late-relapsed HCC tumor (LRT) samples showed a unique accumulation of Mph_04_TREM2, DC_03_LAMP3, and Mast cells, distinguishing them from other groups.






## 1 


The bar plot illustrates the distribution of Scissor+ cells, indicative of poor survival, across various samples derived from both primary hepatocellular carcinoma (PHT and PH for scRNA-seq and scATAC-seq data, respectively) and late relapsed tumors (LRT and LR). Additionally, it includes adjacent normal tissues from primary (PHN) and late relapsed cases (LRN). Notably, Scissor+ cells, which are associated with a poor prognosis, were identified in all patient samples under study. This observation underscores the pervasive presence of these prognostically significant cells within both cancerous and adjacent normal tissues, highlighting their potential role in the progression and recurrence of hepatocellular carcinoma.


## 2

Our analysis identified significant differential gene expression between Scissor+ cells, associated with poor survival, and Scissor− cells, indicative of good survival. Notably, genes such as MT-CO1, TF, CD74, FN1, SPP1, CYP2E1, CES1, FOS, AOX1, and ATF3 were particularly enriched in the Scissor+ cell population.


## 3


Our analysis revealed distinct gene expression signatures that significantly differentiate between patients with poor survival outcomes and others .


## 4

Our analysis established a clear correlation between the expression levels of specific upregulated genes and clinical outcomes in hepatocellular carcinoma (HCC) patients. Individuals exhibiting elevated expression of these genes experienced significantly reduced survival times compared to those with lower expression levels.





# Tcells

1.CD8 T cells further confirm immune evasion characteristics in LR group.(CCR7，PDCD1)
2.
3. scTCR in cD8 is not an independent process but undergone an extensive state transition.


## 1









为什么在LRT中富集这些配体受体CRLF2_TSLPR，
TNFSF4_TNFRSF4，
cOL9A2_a2b1_complex，cOL6A2_a2b1_complex，cOL4A4_a2b1_
complex，
cOL4A3_a2b1_complex，cOL24A1_a2b1_complex，cOL19A1_a2b1_complex，CDH1_a2b1_complex，c5_C5AR2，
c5_c5AR1，
TNFSF11_TNFRSF11A，IL2_receptor_1_L2
2_receptor_HA_IL2 and FN1_a2b1_complex




富集于晚期复发性肝癌（LRT）中的这些配体-受体复合体和细胞外基质（ECM）与整合素相互作用的复合体的存在，可能与肿瘤的生物行为、微环境相互作用以及肿瘤细胞的免疫逃逸机制密切相关。这些分子通路的具体作用如下：

### 细胞外基质（ECM）与整合素相互作用的复合体

1. **COL（胶原蛋白）与整合素α2β1复合体（例如COL9A2, COL6A2, COL4A4, COL4A3, COL24A1, COL19A1）**：
   - **结构与功能**：胶原蛋白是ECM的主要组成部分，与整合素结合影响细胞附着、迁移和信号传导。
   - **癌症中的角色**：在癌症中，这些复合体可增强肿瘤细胞的侵袭能力和迁移性，促进肿瘤微环境的重塑，并可能影响肿瘤的生长和转移。

2. **FN1（纤维连接蛋白）与整合素α2β1复合体**：
   - **功能**：纤维连接蛋白是一种主要的ECM蛋白，涉及细胞黏附和组织修复。
   - **在肿瘤中的影响**：纤维连接蛋白的表达改变在许多类型的癌症中常见，与肿瘤细胞的生存、增殖和转移能力增强相关。

### 细胞因子与其受体的相互作用

1. **CRLF2_TSLPR**：
   - **功能**：这种受体与其配体的结合激活JAK/STAT信号通路，影响细胞生长和分化。
   - **在肿瘤中的作用**：可能涉及调节免疫反应和细胞存活。

2. **TNFSF4_TNFRSF4（OX40与其配体）**：
   - **免疫调节**：这对分子在激活和增强T细胞反应中起重要作用，尤其是在抗肿瘤免疫中。
   - **癌症治疗潜力**：激活这一途径可能增强对抗肿瘤的免疫反应。

3. **TNFSF11_TNFRSF11A（RANKL与RANK）**：
   - **功能**：调节骨骼代谢和淋巴结发育。
   - **在癌症中的角色**：在骨转移中尤为重要，可促进肿瘤细胞在骨组织中的存活和增殖。

4. **IL2与IL2受体复合体**：
   - **免疫应答**：IL2是调节T细胞生长和活化的关键细胞因子。
   - **在肿瘤免疫治疗中的应用**：通过激活和扩展特异性T细胞，IL2被用于某些癌症的免疫治疗。

### 补体系统组分与受体

1. **C5与C5AR1/C5AR2**：
   - **功能**：补体系统的组分，涉及炎症和免

疫反应。
   - **癌症中的作用**：可能通过调节肿瘤微环境中的炎症反应影响肿瘤生长和免疫逃逸。

这些配体-受体复合体和细胞外基质相互作用的富集在晚期复发性肝癌中，可能是由于肿瘤微环境的独特需求，肿瘤细胞为了适应这些需求，可能选择性表达这些分子以促进其存活、增殖和免疫逃逸。这种现象指示了潜在的治疗靶点，其阻断或调节可能对抗复发性肝癌提供新的治疗策略。



## 2
为什么在LRN中富含这些配体受体cCR1_cCL14,
AcvR_1A2A_receptor_BMP8A，ccR3_CCL8，
cCR3_CCL28，ccR3_CCL14，cCL5_CCR3，cCL3_CCR3，cCL3L1_cCR3，CCL24_cCR3
BMPR1A_BMPR2_BMP8A,TNFSF18_TNFRSF18,
NCR3_NCR3LGi，
L27_IL27_receptor，
ACVR1_BMPR2_BMP8A,IL13_TMEM219,
IL13_ receptor_ IL13


在晚期复发性肝癌的正常邻近组织（LRN）中富含各种配体-受体复合体可能与几个关键因素相关，这些因素涉及肿瘤微环境的调节、免疫监视、炎症响应以及细胞生长和修复的信号。这些配体-受体的表达可能反映了身体试图对抗肿瘤、修复组织损伤或调节免疫反应的机制。下面详细解释这些配体-受体的潜在作用：

### 免疫调节和炎症反应
1. **CCR1_CCL14, CCR3_CCL8, CCR3_CCL28, CCR3_CCL14, CCL5_CCR3, CCL3_CCR3, CCL3L1_CCR3, CCL24_CCR3**：
   - 这些是属于趋化因子及其受体的配对，主要功能是调节白细胞（如T细胞、单核细胞、嗜酸细胞）的迁移和定位。这些趋化因子在肿瘤邻近组织中的表达可能是身体对肿瘤生长作出的反应，试图通过招募免疫细胞到肿瘤周围来对抗肿瘤或减缓其扩散。

### 细胞增殖和组织修复
2. **BMPR1A_BMPR2_BMP8A, ACVR1_BMPR2_BMP8A**：
   - 这些配体-受体复合体涉及骨形态发生蛋白（BMP）信号通路，主要参与细胞分化、增殖以及组织发育和修复。在肝脏的正常邻近组织中表达这些信号可能是为了修复由肿瘤扩散或治疗引起的组织损伤。
   
### 免疫激活
3. **TNFSF18_TNFRSF18 (GITR与其配体)**、**IL27_IL27 receptor**：
   - GITR是一种调节性T细胞和效应性T细胞的共刺激分子，有助于调节免疫应答。IL-27是一种具有抗炎和免疫调节作用的细胞因子，通过其受体作用于多种免疫细胞，可能在调控局部免疫反应中发挥重要角色。
   
### 免疫抑制和调节
4. **IL13_TMEM219, IL13_receptor_IL13**：
   - IL-13是一种主要由Th2细胞产生的细胞因子，与调节免疫反应、炎症反应以及纤维化相关。其在LRN中的表达可能与肿瘤微环境的免疫调节以及抗炎和抗纤维化过程有关。
   
### 自然免疫反应
5. **NCR3_NCR3LGi**：
   - NCR3 (NKp30) 是自然杀伤细胞表面的一个活性受体，与其配体的互作对NK细胞介导的细胞毒性反应至关重要。这可能反映了在肿瘤邻近组织中对增强自然免疫反应的需求。

这些分子的表达模式揭示了正常邻近组织在免疫监

视、组织修复、免疫调节和反应肿瘤生长的复杂相互作用中的角色。了解这些相互作用有助于开发更有效的治疗策略，特别是在针对肿瘤微环境及其对周围正常组织的影响方面。