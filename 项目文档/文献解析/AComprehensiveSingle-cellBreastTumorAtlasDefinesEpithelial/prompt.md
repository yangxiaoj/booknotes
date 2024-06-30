你是一个生物信息学术专家，请详细阅读三引号中的文本，然后完成以下任务。 '''

# 标题：A comprehensive single-cell breast tumor atlas defines epithelial and immune heterogeneity and interactions predicting anti-PD-1 therapy response

## Abstract:

We present an integrated single-cell RNA sequencing atlas of the primary breast tumor microenvironment
(TME) containing 236,363 cells from 119 biopsy samples across eight datasets. In this study, we leverage
this resource formultipleanalysesofimmuneand cancerepithelial cell heterogeneity. We define naturalkiller
(NK) cell heterogeneity through six subsets in the breast TME. Because NK cell heterogeneity correlates with
epithelial cell heterogeneity, we characterize epithelial cells at the level of single-gene expression, molecular
subtype, and 10 categories reflecting intratumoral transcriptional heterogeneity. We develop InteractPrint,
which considers how cancer epithelial cell heterogeneity influences cancer-immune interactions. We use
TcellInteractPrinttopredictresponsetoimmunecheckpointinhibition(ICI)intwobreastcancerclinicaltrials
testing neoadjuvant anti-PD-1 therapy. T cell InteractPrint was predictive of response in both trials versus
PD-L1 (AUC = 0.82, 0.83 vs. 0.50, 0.72). This resource enables additional high-resolution investigations of
the breast TME.

## INTRODUCTION


Breast cancer is the most common cancer among women. 1 The
development of breast cancer is driven by both cancer
epithelial cell-intrinsic factors 2–4 and the tumor microenvironment
(TME). 5,6 Themedicaltreatmentofbreastcancerthereforetargets
these diverse cell populations and includes traditional chemo-
therapy,targetedagentsinhibitingcancercellhormonereceptors,
kinases, cell cycle entry, and immune cell modulators. To further
improve these therapies, a deeper understanding of the cellular
and molecular composition of breast tumors is required.
Single-cell RNA sequencing (scRNA-seq) technology has
been applied to better characterize tumor microenvironments.
For breast cancer, several scRNA-seq studies have been per-
formed to identify key immune, cancer cell, and stromal popula-
tions of the breast TME. 7–14 These studies provided insight into
molecular phenotypes of cancer cells, multiple immune popula-
tions, and other stromal cells. However, each study was limited
by the number of samples and cells analyzed. This poses chal-
lenges to performing comprehensive analysis of heterogeneous
cell populations and their cellular interactions in the TME.
For example, natural killer (NK) cells are innate lymphoid
immune cells critical to anti-tumor defense. In breast cancer, tu-
mor-infiltratingNKcellsarerare, 15–19 representing1%–6%ofto-
tal tumor cells in published scRNA-seq datasets of primary
breast tumors. 7–9,11–14 Their cytotoxic activity is regulated by a
series of functionally activating and inactivating receptors. After
tumorexposure, thebalance ofNKcell-activating and -inactivat-
ing receptors can change, and they can lose their cytotoxic
activity or proliferative capacity or even become tumor promot-
ing. 20–22 Because of the small numbers of NK cells processed in
most human studies, scRNA-seq analyses of NK cells are often
underpowered to capture their distinct functional phenotypes.
Additionally, breast cancer is known to have substantial heterogeneity within the tumor of a single patient and between
patients of a clinical subtype. 23,24 Therefore, comprehensive
analysis of cancer epithelial cell heterogeneity requires large
and diverse datasets with adequate numbers of samples from
all clinical breast cancer subtypes.
In this study, we created an integrated scRNA-seq atlas of the
breast TME, consisting of 236,363 cells from 119 biopsy sam-
ples across 8 publicly available datasets. 7–14 This resource en-
ablesseparation ofcell populations withinprimarybreasttumors
and robust characterization of cellular heterogeneity at the sin-
gle-cell level. This integrated dataset is more statistically power-
fulthan traditional meta-analyses of original source datasets and
enables evaluation of correlations with clinical features. We used
this resource to define immune and cancer epithelial cell
heterogeneity along with their interactions. It is the first, to our
knowledge, to define NK cell subsets in breast cancer and
provides evidence that cancer epithelial cell heterogeneity influ-
ences immune interactions and response to anti-PD-1 therapy.
This dataset provides a comprehensive resource to better un-
derstand the composition of the breast TME.


## Results

### An integrated scRNA-seq dataset of breast cancer samples reveals distinct NK cell subsets that exhibit diverse functional characteristics

To develop a high-resolution atlas of the breast TME, we
analyzed scRNA-seq data from 119 samples collected from
primary tumor biopsies of 88 patients across 8 publicly available
breast cancer datasets (Figures 1A and S1A–S1C; Data S1). 7–14
After processing each dataset separately to filter out low-quality
cells and doublets, we integrated a total of 236,363 cells across
all clinical subtypes and a wide spectrum of clinical features
(Data S1). We assessed batch effect to ensure no cluster was
driven by a single dataset or technology (STAR Methods;
Figures S1D–S1L and S2A–S2I). Cell types were identified by
taking the top call resulting from a three-step process that
labeled clusters based on a signature score of canonical cell
markers, marker count coupled with average expression, and
greatest average expression of the marker genes alone (Data
S2; STAR Methods). Uniform manifold approximation and pro-
jection (UMAP) visualization showed clustering of cells by line-
age. Immune and stromal cell populations clustered together
acrossclinicalsubtypes,whileepithelialcellsshowedseparation
by subtype (Figures 1B and S1F), which is consistent with other
studies. 11,13 For all datasets, single-cell copy number variant
(CNV) profiles were estimated to distinguish cancer from normal
epithelial cells (Figures S3A–S3D).
Because the number of cells in this dataset permits statistically
poweredanalysisofrareimmunecellpopulationsinhumanbreast
cancers, we first leveraged the integrated dataset to better char-
acterize the heterogeneity of NK cells. While NK cells are key me-
diators of anti-tumor control, our understanding of their varied
phenotype and function in the breast TME is limited and incom-
plete. To our knowledge, there are no prior studies that dissect
NK cell subsets in the human breast TME. To address this gap,
were-clusteredNK cells fromthe integrateddataset (Figure S4A).
Unsupervisedgraph-based clustering uncovered 6 clustersof NK
cells, designated NK-0 through NK-5 (Figures 1C, S4B, and S4C).
Differential gene expression analysis between clusters re-
vealed upregulated genes defining each NK subset (Figures 1D
and S4D; Table 1; Data S3; STAR Methods). NK-0 and NK-2 ex-
press high levels of FCGR3A (CD16) and cytolytic molecules
(granzymes and PRF1), which suggests that they are similar to
CD56 dim NK cells. 25–29 NK-0 is enriched for KLRC2, ETS1, and
effector genes (GZMH and CCL5), which closely resembles
gene expression profiles described previously for ‘‘memory-
like’’NKcells. 25 NK-2isdefinedbyincreasedexpressionofcyto-
toxicity-related genes (GZMA, GZMB, PRF1, and SPON2) and
S1PR5, which has been described previously in CD56 dim bone
marrow NK cells. 25 NK-4 is predominated by genes involved in
interferon signaling (IFI6 and ISG15), suggesting that this subset
may be influenced by interferon-high tumor microenvironments
and consists of activated NK cells involved in the direct anti-tu-
mor response. 30 NK-3 cells appear to have features of tissue-
resident NK cells, with upregulated expression of SELL, IL7R,
and GZMK as well as reduced expression of cytolytic genes
and FCGR3A (CD16). 31 In contrast, genes of inactivity and
reduced cytotoxicity were upregulated in clusters NK-1 and
NK-5. Most notably, NK-1 was marked by genes related to the
NR4A family, 32,33 JUN, FOS, and DUSP1. NR4A is a family of
orphan nuclear receptors that act as transcription factors;
they are thought to negatively regulate T cell cytotoxicity 32 and
have been described as marking specific NK cells with reduced
interferon gamma production. 29,33 NK-5 had reduced expres-
sion of cytolytic genes and FCGR3A (CD16) and increased
expression of KLRC1 and CD96, which are inactivators of NK
cell activity. 34,35 To further define the function of NK cell subsets,
we performed gene set enrichment analysis of individual clus-
ters, which confirmed their functional phenotypes (Figure S4E).

### Reprogrammed NK cells are most similar to the NK-1 subset and are observed in patient samples independent of subtype


Previously in ex vivo and mouse models, we observed that NK
cells can be ‘‘reprogrammed’’ after exposure to malignant mam-
mary epithelial cells to promote tumor outgrowth. 20,21 To deter-
mine the human significance of this finding, we first generated a
signature of mouse reprogrammed NK (rNK) cells based on an
experiment 20 comparing the transcriptomes of healthy NK cells
with tumor-exposed NK cells that we found to be tumor promot-
ingandreprogrammed (FigureS5A).Wenextconvertedtheorig-
inal signature to the human analog (Figure S5B; Table 2) and
applied it to theNK cell subsets. NK-1scoredsignificantly higher
for the rNK signature than all other NK cell subsets (p < 0.0001)
(Figure 1E). Differential gene expression analysis of rNK cells
compared with non-rNK cells revealed that the NR4A family
(NR4A1, NR4A2, and NR4A3), FOS, JUN, and DUSP1 were
among the most differentially expressed genes (Figure 1F;
Data S4; STAR Methods), similar to the transcriptional profile
of the NK-1 subset.
To test whether rNK cells were associated with a specific
breast cancer subtype, we examined the expression of rNK cells
across clinical subtypes. We found no significant differences in
rNK cell expression across all subtypes (p > 0.05, n = 3,720
NK cells total) (Figures 1G and S5C). Additionally, we found
shared receptor-ligand pairs between NK cells and cancer
epithelial cells across all subtypes (Figure 1H), including
LGALS3_SPN, RPS19_ICAM1, and HSP90B1_TNFRSF1B.
Further, the average Pearson correlation in gene expression
levels between rNK cells was greater than between rNK and
non-rNK cells (p < 0.0001) (Figures 1I and S5D). Together, these
findings demonstrate that rNK cells are not defined by specific
breast cancer subtype biology but suggest that a shared but still
unknown mechanism contributes to NK cell reprogramming.
To further investigate the clinical significance of rNK cells, we
observed that higher expression of rNK cells correlates with
older age (R = 0.33, p < 0.01) (Figure 1J). Survival analysis was
performed on patients in The Cancer Genome Atlas (TCGA)
breast cancer cohort, and we first confirmed that age was not
a confounder of this analysis (Figure S5E). Given the limitations
of applying the rNK cell signature to bulk RNA-seq samples
from TCGA, which include a substantial fraction of non-NK cells,
only samples with a relatively high fraction of tumor-infiltrating
NK cells were selected for analysis (STAR Methods). Increased
expression ofthe rNKcell signature in tumorswitha high fraction
of NK cells correlates with worse overall survival (p < 0.05)
(Figures 1K and S5F).
We then asked whether NK cell subsets were uniformly
expressed across individuals and breast cancer subtypes. To
answer this question, we characterized the degree of NK cell
heterogeneity across patients in the integrated dataset. We
observed remarkable heterogeneity in the proportions of NK
cell subsets across patients (Figure 1L). Additionally, no NK
cell subset was driven by a single patient, and all NK cell subsets
were present across each breast cancer clinical subtype. How-
ever, NK cell subset heterogeneity as quantified using ROGUE
analysiswas observedto besignificantly higherin certainclinical
subtypes than others (Figure S5G). While there have been multi-
ple reports of NK cell subsets in other cancers, 28,29 none have
yet explored the diversity of NK cell subsets within individual pa-
tient samples. Our findings provide further evidence of the
diverse phenotypes of NK cells within individual primary breast
tumors.
### Individual breast tumors have varying degrees of cancer epithelial cell heterogeneity

Because we observed that NK cell heterogeneity is associated
with certain clinical subtypes of breast cancer (Figure 1L), we
reasoned that heterogeneity within breast cancer subtypes
would be important when further characterizing the breast
TME. We then used our dataset to explore the heterogeneity of
cancer epithelial cells at different resolutions: at the level of Reprogrammed NK cells are most similar to the NK-1
subset and are observed in patient samples
independent of subtype
Previously in ex vivo and mouse models, we observed that NK
cells can be ‘‘reprogrammed’’ after exposure to malignant mam-
mary epithelial cells to promote tumor outgrowth. 20,21 To deter-
mine the human significance of this finding, we first generated a
signature of mouse reprogrammed NK (rNK) cells based on an
experiment 20 comparing the transcriptomes of healthy NK cells
with tumor-exposed NK cells that we found to be tumor promot-
ingandreprogrammed (FigureS5A).Wenextconvertedtheorig-
inal signature to the human analog (Figure S5B; Table 2) and
applied it to theNK cell subsets. NK-1scoredsignificantly higher
for the rNK signature than all other NK cell subsets (p < 0.0001)
(Figure 1E). Differential gene expression analysis of rNK cells
compared with non-rNK cells revealed that the NR4A family
(NR4A1, NR4A2, and NR4A3), FOS, JUN, and DUSP1 were
among the most differentially expressed genes (Figure 1F;
Data S4; STAR Methods), similar to the transcriptional profile
of the NK-1 subset.
To test whether rNK cells were associated with a specific
breast cancer subtype, we examined the expression of rNK cells
across clinical subtypes. We found no significant differences in
rNK cell expression across all subtypes (p > 0.05, n = 3,720
NK cells total) (Figures 1G and S5C). Additionally, we found
shared receptor-ligand pairs between NK cells and cancer
epithelial cells across all subtypes (Figure 1H), including
LGALS3_SPN, RPS19_ICAM1, and HSP90B1_TNFRSF1B.
Further, the average Pearson correlation in gene expression
levels between rNK cells was greater than between rNK and
non-rNK cells (p < 0.0001) (Figures 1I and S5D). Together, these
findings demonstrate that rNK cells are not defined by specific
breast cancer subtype biology but suggest that a shared but still
unknown mechanism contributes to NK cell reprogramming.
To further investigate the clinical significance of rNK cells, we
observed that higher expression of rNK cells correlates with
older age (R = 0.33, p < 0.01) (Figure 1J). Survival analysis was
performed on patients in The Cancer Genome Atlas (TCGA)
breast cancer cohort, and we first confirmed that age was not
a confounder of this analysis (Figure S5E). Given the limitations
of applying the rNK cell signature to bulk RNA-seq samples
from TCGA, which include a substantial fraction of non-NK cells,
only samples with a relatively high fraction of tumor-infiltrating
NK cells were selected for analysis (STAR Methods). Increased
expression ofthe rNKcell signature in tumorswitha high fraction
of NK cells correlates with worse overall survival (p < 0.05)
(Figures 1K and S5F).
We then asked whether NK cell subsets were uniformly
expressed across individuals and breast cancer subtypes. To
answer this question, we characterized the degree of NK cell
heterogeneity across patients in the integrated dataset. We
observed remarkable heterogeneity in the proportions of NK
cell subsets across patients (Figure 1L). Additionally, no NK
cell subset was driven by a single patient, and all NK cell subsets
were present across each breast cancer clinical subtype. How-
ever, NK cell subset heterogeneity as quantified using ROGUE
analysiswas observedto besignificantly higherin certainclinical
subtypes than others (Figure S5G). While there have been multi-
ple reports of NK cell subsets in other cancers, 28,29 none have
yet explored the diversity of NK cell subsets within individual pa-
tient samples. Our findings provide further evidence of the
diverse phenotypes of NK cells within individual primary breast
tumors.
Individual breast tumors have varying degrees of cancer
epithelial cell heterogeneity
Because we observed that NK cell heterogeneity is associated
with certain clinical subtypes of breast cancer (Figure 1L), we
reasoned that heterogeneity within breast cancer subtypes
would be important when further characterizing the breast
TME. We then used our dataset to explore the heterogeneity of
cancer epithelial cells at different resolutions: at the level of non-HER2+ tumors did not show significant association with
nodal status (p = 0.25) (Figures 2G, S7A, and S7B). However, tu-
mors with an increased proportion of TACSTD2-expressing cells
were significantly associated with higher nodal status (p = 0.015)
(Figure 2H). When performing this analysis separately in each
cohort, the combined result by Fisher’s combined probability
was not statistically significant, though it trended toward signifi-
cance (X = 11.227, p = 0.08) (Figure S7C). This again highlights
the value of our data integration approach, which creates a
more statistically powered dataset and enables evaluation of
correlations with clinical features over traditional meta-analysis
methods.
Our study joins several reports noting the heterogeneous
expression of single genes within single tumors. 48–51 Recog-
nizing that intratumoral heterogeneity occurs beyond single
genes, we next characterized the ITTH of cancer epithelial cells
in primary breast tumors. To do so, we applied a well-character-
ized SC50 molecular subtype classifier 13 that scores the four
molecular subtypes (luminal A, luminal B, Her2, and basal) to
cancer epithelial cells in the integrated dataset. We found that
each patient tumor expressed differing proportions of cells
from each molecular subtype with a varied degree of concor-
dance with the clinical subtype diagnosis (Figure 2I). This finding
prompted us to explore how cancer epithelial cell ITTH may be
influenced by features beyond molecular subtype. We quantified
the degree of heterogeneity across all cancer epithelial cells in a
patient tumor using ROGUE analysis (Figure 2I). 52 The ROGUE
score for each individual tumor sample also reflected molecular
subtype heterogeneity to some degree; however, we noticed
discordance in 33.3% of samples, which demonstrated homo-
geneity based on molecular subtype but high heterogeneity
based on ROGUE score (Figure 2J; STAR Methods). This sug-
gests that other factors beyond molecular subtype-associated
genes drive the observed heterogeneity and underscores a
need for different approaches to study cancer epithelial cell
ITTH at higher resolution than that of existing subtype classifiers.
### Cancer epithelial cell heterogeneity can be defined by 10 unifying groups of gene signatures

To develop a high-resolution classifier of heterogeneous cancer
epithelial cells, we first performed unsupervised clustering on all
cancer epithelial cells in the integrated dataset to generate sig-
naturesofupregulatedgenesthatcapturedistinctmolecularfea-
tures of cancer epithelial cell clusters. Next, supervised classifi-
cation was performed based on expression of 12 clinical
therapeutic targets (ESR1, ERBB2, ERBB3, PIK3CA, NTRK1/
NTRK2/NTRK3, CD274, EGFR, FGFR1/FGFR2/FGFR3/FGFR4,
TACSTD2, CDK4/CDK6, AR, and NECTIN2) to ensure that clini-
cally relevant associations were captured by upregulated gene
signatures (STAR Methods). The motivation for including thera-
peutic targets was to create classifications grounded in relevant
clinical approaches. We additionally supervised classification of
all cancer epithelial cells based on molecular subtype to
generate upregulated gene signatures that reflect subtype fea-
tures. Consensus clustering of all generated gene signatures
identified 10 unifying groups, which we defined as ‘‘gene ele-
ments’’ (GEs) (Figures S8A and S8B). We defined each GE by
the top 100 genes that occurred most frequently across gene
signatures assigned to the group (Table 3; STAR Methods). We
scored each cancer epithelial cell by the individual 10 GEs and
assigned GE-based cell labels (Figure 3A; STAR Methods).
When assessing for molecular subtypes, GE3-labeled cells
were predominantly assigned to the basal subtype, while the
majority of GE9-labeled cells were assigned to the Her2 subtype
(Figure 3B). Cells labeled by GE1 and GE7 were almost exclu-
sively assigned as luminal A and luminal B. In contrast, GE5-
and GE10-labeled cells were assigned to all molecular subtypes.
Next, we used gene set enrichment analysis (Figure 3C) to iden-
tify functional annotations for each GE. This analysis identified
shared and distinct functional features for all GEs. GE4 was
uniquely enriched for cell cycle and proliferation hallmarks
(MKI67, PCNA, and CDK1). GE2 and GE3 contained hallmark
genes of EMT (VIM and ACTA2). GE1, GE6, GE7, and GE9 con-
tained genes associated with estrogen response (ESR1, AREG,
and TFF3). GE5 and GE10 were enriched for hallmarks of allo-
graft rejection (HLA-DRA and HLA-DRB1) and complement
(C1QA/B/C and C1R).
To assess how GE-based cell labels allow us to characterize
cancer epithelial cell heterogeneity within a tumor sample, we
appliedourGEstotheintegrateddatasettodeconstructeachin-
dividual patient tumor into the 10 GEs (Figure S8C). Notably, GE-
based heterogeneity was not constrained by clinical or molecu-
lar subtype. This again confirms that significant cancer epithelial
cell ITTH exists even within cells from a tumor labeled by a single
clinical or molecular subtype. Overall, we generated 10 GEs to
characterize cancer epithelial cell ITTH and deconstruct a het-
erogeneous tumor into its diverse cellular phenotypes.
### GEs predict individual patient predominant immune response
To examine how cancer epithelial cell ITTH influences immune
interactions in the TME, we generated a decoder matrix of pre-
dicted GE-immune interaction strength. GE-immune interaction
strength is determined based on the scaled number of predicted
receptor-ligand pairings between GEs and immune cells
(Figures 3D and S8D; STAR Methods).
To experimentally validate the decoder matrix, we tested
these predictions with human breast cancer cell lines. In the decoder matrix, cancer epithelial cells labeled by GE1 and GE6
were predicted to highly interact with NK cells (GE1 and GE6
have the highest scaled number of curated receptor-ligand pair-
ings). We applied the GEs to human breast cancer cell lines from
the Cancer Cell Line Encyclopedia to quantify GE expression
across cell lines (Figure S8E). Given that GE1 and GE6 have
the greatest predicted interaction strength with NK cells (Fig-
ure 3D), we hypothesized that expression of these GEs will
have a significant influence on NK cell function (i.e., sensitivity
or resistance of cancer cell lines to NK cell killing). To test this,
we selected breast cancer cell lines with differing expression
of GE1 and GE6. BT-474 had increased expression of GE1 and
GE6, while MDA-MB-436 had decreased expression of GE1
and GE6. Using these selected cell lines, we assessed the relationship between GE1 and GE6 expression and sensitivity to
NK cell killing. We co-cultured BT-474 (GE1 and GE6 high) and
MDA-MB-436 (GE1 and GE6 low) with NK-92, a human NK cell
line. As hypothesized, GE1 and GE6 expression had a statisti-
cally significant impact on NK cell function. NK cell cytotoxicity
against BT-474 at 24 h was significantly reduced (p < 0.0001)
compared with NK cell cytotoxicity against MDA-MB-436 (Fig-
ure S8F). This finding suggests that GE1 and GE6 confer resis-
tance to NK cell cytotoxicity. Next, to expand on these experi-
mental findings, we used a study by Sheffer et al., 53 which
reports experimental sensitivity orresistanceof 26breastcancer
cell lines to NK cell cytotoxicity (STAR Methods). 53,54 Increased
GE1 and GE6 expression was significantly correlated with
increased resistance to NK cell killing (R = ?0.54, p < 0.05 for
GE1; R = ?0.54, p < 0.05 for GE6) (Figure 3E), consistent with
the decoder matrix and our experimental findings. Other GEs
with fewer predicted NK cell interactions in the decoder matrix
did not have statistically meaningful correlations with sensitivity
to NK cells (Figure S8G). To investigate interactions that
contribute to these phenotypes, we assessed predicted recep-
tor-ligand pairs between cells that highly express GE and NK
cells (Figure 3F). We observed that GE1- and GE6-labeled cells
were predicted to have receptor-ligand pairs that have been
characterized as inactivators of NK cell activity (e.g., NECTIN2_
TIGIT, THBS1_CD47, and CD320_TGFRB2). These functional
studies validate two of the predictions made by the decoder ma-
trix by showing that GE1 and GE6 are predictive of significant
resistance to NK cell killing for breast cancer cell lines.
Overall, this decoder matrix provides a blueprint for quanti-
fying the degree of interactions between each GE and different
immune cell types. Moreover, this decoder matrix curates key
activating and inhibitory receptors that can be used to infer
how GE-immune interactions affect immune cell behavior.
### Spatial mapping of GEs reflects predicted immune interactions


To validate the predicted interactions curated by the decoder
matrix, we used a spatial transcriptomics dataset containing
published data from 103 Genomics and from Wu et al. 13 We first
deconvoluted the underlying composition of cell types through
integration of the spatial transcriptome data with the integrated
dataset(STARMethods).BecauseTcellinfiltrationwasrelatively
high across spatial transcriptomics samples (Figure S9A), we
chose to explore T cell interactions using this dataset. To do so,
we applied the 10 GEs to each sample in the dataset. Using the
decoder matrix, we inferred which GE-labeled cells interact
with T cells and which ones do not. Thus, we hypothesized that
these GE-labeled cells and CD8 + T cells would be spatially orga-
nized in breast tumors. To test this, we examined the co-expres-
sion of the GEs and the presence of neighboring CD8 + T cells.
Notably, GE5 expression demonstrated positive correlations
with CD8 + T cells in all samples (mean R = 0.33, all p < 0.0001)
(Figure 4A). In one representative image, we determined the
co-localization of CD8 + T cells with GE5 expression (Figure 4B).
For areas with high presence of CD8 + T cells, we observed
increased colocalization of select curated receptor-ligand pairs
(ITGB2_ITGAL, LTB_TNFRSF1A, and ALOX5AP_ALOX5) (Fig-
ure 4B). As expected, GEs with limited predicted interactions
did not consistently co-localize with CD8 + T cells (Figure S9B).
### InteractPrint: A weighted score to predict the predominant tumor-interacting immune cell for an individual patient tumor

We then hypothesized that the GE-immune interaction decoder
matrix could be applied to individual tumor tissues. To account
for how cancer epithelial cell ITTH within a tumor influences im-
mune cell interactions, we developed InteractPrint. InteractPrint
reflectsinteractionsbetweenthepredominanttumor-responsive
immune cells from the decoder matrix and cancer cells that
highly express each GE, weighted by the GE composition of an
individual patient tumor. This approach permits real-world appli-
cation of InteractPrint since it accounts for heterogeneity of GEs
within a tumor.
### InteractPrint predicts anti-PD-1 therapeutic response

We then sought to use InteractPrint to characterize the predom-
inant immune response within patients for therapeutically
targeted immune cells. Because current immune checkpoint in-
hibitors (ICI) target CD8 + T cell-driven cancers, we developed
T cell InteractPrint to predict who might respond to ICI. For the
comparator,averagePD-L1expressiononcancerepithelialcells
was selected, as PD-L1 remains the main biomarker used clini-
cally to determine who should receive ICI for many solid tumors,
including patients with recurrent unresectable or metastatic
triple-negative breast cancer (TNBC). 55,56
We applied our approach to a separate scRNA-seq dataset
published by Bassez et al., 57 which contains tumor biopsies
from breast cancer patients pre and post anti-PD-1 therapy
(FiguresS8CandS8D).Deconstructionofeachindividualpatient
tumorintothe10GEsrevealedconsiderablecancerepithelialcell
ITTH priorto anti-PD-1 treatment (Figure4C),similar towhatwas
observed in the integrated dataset (Figure S8C). To assess the
capacity of the T cell InteractPrint to predict responders to anti-
PD-1 therapy, we derived receiver operating characteristic
(ROC) curvesin thisdataset (Figure 4D).Across clinical subtypes
of breast cancer, the T cell InteractPrint demonstrated an area under the curve (AUC) of 81.87% (p = 0.0061) in predicting
response to anti-PD-1 therapy, inferred from T cell clonotype
expansion. 53 This was a significant improvement (p = 0.019)
over average PD-L1 expression on cancer epithelial cells, the
current clinical biomarker to predict patients who will respond
to anti-PD-1 therapy in breast cancer, which had an AUC of
49.71% (p > 0.05).
Next, weapplied our predictor to a separate validation dataset
containing results from the I-SPY2 trial. I-SPY2 is an ongoing,
multicenter, open-label, adaptively randomized phase 2 trial of
neoadjuvant chemotherapy for early-stage breast cancer at
high risk of recurrence. 57 In this trial, patients with breast cancer
received anti-PD-1 therapy (the same as patients from Bassez
et al. 57 ) combined with paclitaxel. We applied the 10 GEs to mi-
croarray data from pre-treatment tumor samples from the
I-SPY2 trial and observed levels of heterogeneity that were
comparable with those described in the scRNA-seq datasets
(Figure 4E). In the I-SPY2 trial dataset, T cell InteractPrint
(AUC = 83.02%, p = 8.1 3 10 ?7 ) demonstrated significant
improvement (p=0.034)overaverage PD-L1expression oncan-
cer epithelial cells (AUC = 72.33%, p = 0.001) in predicting
response to anti-PD-1 therapy (Figure 4F).
Across two trials, T cell InteractPrint demonstrated significant
improvement over PD-L1 at predicting response to anti-PD-1
therapy. This highlights the ability of T cell InteractPrint to
decode how cancer epithelial cell ITTH impacts CD8 + T cell
response for each individual patient.

图例部分

Figure 1. Integrated scRNA-seq dataset of primary breast cancer identifies six NK cell subsets in breast cancer
(A) Brief overview of the processing and integration pipeline for 8 primary breast cancer datasets.
(B) UMAP visualization of 236,363 cells across 119 samples from 88 patients analyzed by scRNA-seq.
(C) UMAP visualization showing major subsets of natural killer (NK) cells.
(D) Bubble heatmap showing expression of upregulated differentially expressed genes for each major NK cell subset (Bonferroni-adjusted p < 0.05).
(E) Boxplot showing expression of the rNK cell signature in each NK cell subset. NK-1 was significantly different from all other clusters (Kruskal-Wallis p < 0.0001,
with post hoc Dunn test p values shown; ****p < 0.0001).
(F) MA plot of differentially expressed genes between rNK and non-rNK cells (Bonferroni-adjusted p < 0.05).
(G)Boxplot showing theexpressionlevel oftherNKsignature byclinicalsubtype.Nosignificantdifference wasfoundbetweensubtypes(Kruskal-Wallisp>0.05).
(H) Circos plots showing representative predictive receptor-ligand pairs between rNK cells and all cancer epithelial cells separated by clinical subtype. Shared
receptors across all subtypes are colored in red.
(I) Boxplot showing the Pearson correlations of rNK signature gene expression in reprogrammed NK (rNK) cells compared with non-rNK cells versus rNK cells
compared with rNK cells (across all clinical subtypes of breast cancer). Pearson correlations between rNK cells and rNK cells are higher than those between rNK
cells and non-rNK cells (two-sided Wilcoxon test, ****p < 0.0001).
(J) Scatterplot showing the Pearson correlation of age and proportion of rNK cells by sample (p <0.01).
(K) Kaplan-Meier plot showing worse clinical outcome in breast cancer patients with high expression of the rNK cell gene signature (log rank test, p < 0.05).
(L) Bar plot showing relative proportions of NK subsets across tumor samples and clinical subtypes.
See also Figures S1–S5 and Data S1 and S4.


Figure 2. Cancer epithelial cells demonstrate substantial ITTH
(A) Bar plot showing proportions of ERBB2 Hi , ERBB2 Med , and ERBB2 Lo cells by sample.
(B) Bar plot showing proportions of TACSTD2 Hi , TACSTD2 Med , and TACSTD2 Lo cells by sample.
(C) Heatmap of Z-scored average expression of clinically actionable targets in ERBB2 Hi , ERBB2 Med , and ERBB2 Lo cells.
(D) Heatmap of Z-scored average expression of clinically actionable targets in TACSTD2 Hi , TACSTD2 Med , and TACSTD2 Lo cells.
(E) MA plot showing differentially expressed genes between ERBB2 Hi vs. ERBB2 Med and ERBB2 Lo cells (Bonferroni-adjusted p < 0.05).
(F) MA plot showing differentially expressed genes between TACSTD2 Hi vs. TACSTD2 Med and TACSTD2 Lo cells (Bonferroni-adjusted p < 0.05).
(G) Boxplot showing the proportion of ERBB2-expressing cells per sample by nodal status (two-sided Wilcoxon test, p > 0.05).
(H) Boxplot showing the proportion of TACSTD2-expressing cells per sample by nodal status (two-sided Wilcoxon test, p < 0.05).
(I) Percentage of cancer epithelial cells by molecular subtype, sorted by sample score by the ROGUE metric.
(J) Plot showing discordance in predicted heterogeneity by molecular subtype and by ROGUE metric by sample. Samples with >50% difference between the
normalized ROGUE metric and the maximum percentage of cells within the sample that belonged to a single molecular subtype are classified as discordant.


Figure 3. Cancer epithelial cell heterogeneity can be defined by 10 GEs that influence immune cell interactions
(A) Heatmap of Z-scored signature scores of the 10 identified gene elements (GEs) representing all cancer epithelial cells, ordered based on the maximum Z-
scored GE signature score. Annotations represent dataset origin, clinical subtype, PAM50 subtype,and SC50subtype. The‘‘sample’’annotation wasincludedto
demonstrate that no individual patient sample contributed heavily to a particular GE.
(B) Percentage of cancer epithelial cells assigned to each GE by molecular subtype.
(C) Gene set enrichment using ClusterProfiler of the differentially expressed genes by GE. Significantly enriched gene sets from the MSigDB Hallmark collection
are shown (Benjamini-Hochberg-adjusted p < 0.05).
(D) Heatmap of the scaled number of curated predicted receptor-ligand pairs between cancer epithelial cells by GE and interacting immune and stromal cells.
(E) Scatterplots showing Spearman correlations of expression of NK-cell related GE1 and GE6 with sensitivity to NK cell killing (Benjamini-Hochberg-adjusted
p < 0.05).
(F) Circos plots showing curated receptor-ligand pairs between cancer epithelial cells that highly express NK cell-related GE1 and GE6 with NK cells. NK cell
activating receptor-ligand pairs are colored blue; NK cell inactivating receptor-ligand pairs are colored red.
See also Figure S8.


Figure 4. GE-immune interactions predict response to anti-PD-1 therapy
(A) Heatmap of Pearson correlations between expression of each of the 10 GEs and the presence of CD8 + T cells for 6 spatial transcriptomics samples across
spots containing CD8 + T cells (n.s., Benjamini-Hochberg-adjusted p > 0.05).
(B) For a representative TNBC sample, pathological annotation of morphological regions into distinct categories. UCell signature scores of CD8 + T cells are
overlaid onto spatial tumor sample spots (red). A UCell signature score of GE5 (a CD8 + T cell activating GE) is overlaid onto tumor sample spots (red). A co-
localization score for ITGB2_ITGAL, LTB_TNFRSF1A, and ALOX5AP_ALOX5 (predicted receptor-ligand pairs for GE5 and CD8 + T cells) is overlaid onto tumor
sample spots (red).
(C) Heatmap of average expression of each of the 10 GEs across cancer epithelial cells in each sample from Bassez et al. 57 T cell InteractPrint is shown below.
(D) Boxplot showing T cell InteractPrint prediction of response to anti-PD-1 therapy across all clinical subtypes in Bassez et al. 57 (R, responder; NR, non-
responder; p < 0.05). Also shown is the AUC of ROC comparing the performance of T cell InteractPrint (AUC = 81.87) and of PD-L1 expression (AUC = 49.71) in
Bassez et al. 57 samples (bootstrap test with n = 10,000, p < 0.05).
(E) Heatmap of average expression of each of the 10 GEs across cancer epithelial cells in each sample from the I-SPY2 trial. T cell InteractPrint is shown below.
(F) Boxplot showing T cell InteractPrint prediction of response to anti-PD-1 therapy across all clinical subtypes in I-SPY2 trial samples (two-sided Wilcoxon test p
<0.0001). Also shown is the AUC of ROC comparing the performance of T cell InteractPrint (AUC = 83.02) and of PD-L1 expression (AUC = 72.33) in the I-SPY2
trial (bootstrap test with n = 10,000, p <0.05).
(G) Schematic of T cell InteractPrint to predict patient response to anti-PD-1 therapy.
See also Figure S9.


Supplemental Figure 1. Metadata of integrated dataset and visualization of integrated
dataset following batch correction, Related to Figure 1 and STAR Methods.
A. Pie chart of composition of integrated scRNA-seq data by original study.
B. Pie chart of composition of integrated scRNA-seq data by clinical subtype. The proportion of
clinical subtypes within this integrated dataset is close to real-life clinical subtype
distributions.
C. Bar plot showing number of patients per age group. Most of the original datasets stayed
within a sole age group, whereas the integrated dataset includes a much broader age range.
D. UMAP visualization of integrated dataset following batch correction, grouped by source
dataset.
E. UMAP visualization of integrated dataset following batch correction, grouped by capture
technology.
F. UMAP visualization of integrated dataset following batch correction, grouped by clinical
subtype. This shows lineage drives clustering of non-epithelial populations, while epithelial
populations cluster by clinical subtype. This matches the observed subtype clustering seen
in other datasets.
G. PCA plot of first 2 PCs for all cells in the integrated dataset following batch correction,
labeled by original source dataset. No cluster is driven by a single study, thus confirming
there is no batch effect due to different studies.
H. PCA plot of first 2 PCs for all cells in the integrated dataset following batch correction,
labeled by technology. No cluster is driven by a single technology, thus confirming there is
no batch effect due to differing technologies.
I. PCA plot of first 2 PCs for all cells in the integrated dataset following batch correction,
labeled by clinical subtype.
J. Violin plots of mean PC loadings across top 20 PCs for the integrated dataset following
batch correction, stratified by source dataset.
K. Violin plots of mean PC loadings across top 20 PCs for the integrated dataset following
batch correction, stratified by capture technology.
L. Violin plots of mean PC loadings across top 20 PCs for the integrated dataset following
batch correction, stratified by clinical subtype. 


Supplemental Figure 2. Visualization of combined original source datasets prior to batch
correction, Related to Figure 1 and STAR Methods.
A. UMAP visualization of combined original source datasets prior to batch correction, grouped
by source dataset.
B. UMAP visualization of combined original source datasets prior to batch correction, grouped
by capture technology.
C. UMAP visualization of combined original source datasets prior to batch correction, grouped
by clinical subtype.
D. PCA plot of first 2 PCs for combined original source datasets prior to batch correction,
labeled by source dataset.
E. PCA plot of first 2 PCs for combined original source datasets prior to batch correction,
labeled by capture technology.
F. PCA plot of first 2 PCs for combined original source datasets prior to batch correction,
labeled by clinical subtype.
G. Violin plots of mean PC loadings across top 20 PCs for combined original source datasets
prior to batch correction, stratified by source dataset.
H. Violin plots of mean PC loadings across top 20 PCs for combined original source datasets
prior to batch correction, stratified by capture technology.
I. Violin plots of mean PC loadings across top 20 PCs for combined original source datasets
prior to batch correction, stratified by clinical subtype. 


Supplemental Figure 3. Classification of epithelial cells as cancer versus normal using
CNV profile analysis, Related to Figure 1 and STAR Methods.
A. Scatter plot showing classification of epithelial cells in the integrated dataset as cancer
(malignant) versus normal (non-malignant) on inferCNV signal (x-axis) and CNV correlation
(y-axis). Thresholds shown in red dashed lines. CNV signal reflects the extend of CNVs,
while CNV correlation reflects the similarity between the cellular CNV pattern and that of
other cells from the same tumor. Cells assigned as cancer (malignant) are shown in blue,
while the rest are shown in red.
B. UMAP visualization of all epithelial cells in the integrated dataset, grouped by classification
as cancer (malignant) versus normal (non-malignant). Cancer cells are shown in blue, while
normal cells are shown in red. Unassigned cells are shown as NAs and are colored grey.
C. Scatter plot showing classification of epithelial cells in the Bassez et al. dataset as cancer
(malignant) versus normal (non-malignant) on inferCNV signal (x-axis) and CNV correlation
(y-axis).
D. UMAP visualization of all epithelial cells in the Bassez et al. dataset, grouped by
classification as cancer (malignant) versus normal (non-malignant). Cancer cells are shown
in blue, while normal cells are shown in red.


Supplemental Figure 4. Unsupervised clustering of NK cells and analysis of NK cell
subsets, Related to Figure 1.
A. UMAP visualization of all NK cells in the integrated dataset, grouped by source dataset.
UMAP visualization of all epithelial cells in the integrated dataset, grouped by patient. UMAP
visualization of all epithelial cells in the integrated dataset, grouped by capture technology.
B. Silhouette scores for clustering of NK cells at various resolutions (0.1, 0.2, 0.3, 0.4, 0.5, 0.6,
0.7, 1.0). Mean silhouette score is shown as a red dashed line. Maximum mean silhouette
score was observed at resolution 0.1 (2 clusters), and second highest mean silhouette score
was observed at resolution 0.3 (6 clusters).
C. Feature plots showing expression of NK subset markers across all NK cells in our integrated
dataset. Feature plots showing expression of functional NK cell genes across all NK cells in
our integrated dataset.
D. MA plots showing differentially expressed genes between individual NK cell subsets and all
other NK cell subset types (Bonferroni adjusted p-value < 0.05).
E. Gene set enrichment of the differentially expressed genes by each NK cell subset.
Significantly enriched gene sets from the MSigDB HALLMARK collection are shown
(Benjamini-Hochberg adjusted p-value < 0.05).


Supplemental Figure 5. rNK signature development and analysis, Related to Figure 1.
A. Heatmap showing z-scores for the variance-stabilized transformed expression of
differentially expressed genes between healthy NK cells and tumor-promoting NK cells from
previous study.
B. Bubble heatmap showing expression of upregulated and downregulated human rNK
orthologs for each major NK cell subset.
C. Boxplot showing the expression level of the rNK signature by clinical subtype, stratified by
age. No significant difference was found between subtypes (Kruskal-Wallis p > 0.05).
D. Boxplot showing the Pearson correlations of rNK signature gene expression in
reprogrammed NK (rNK) cells compared to non-rNK cells versus rNK cells compared to rNK
cells, stratified by age. Pearson correlations between rNK cells and rNK cells are higher
than those between rNK cells and non-rNK cells for both age strata (two-sided Wilcoxon
test, ****p-value < 0.0001).
E. Scatterplot showing the Pearson correlation between age at initial diagnosis and survival
across TCGA samples (p-value > 0.01).
F. Kaplan-Meier plots evaluating the influence of rNK cell gene signature expression on
survival outcomes in TCGA patients with relatively high fraction of NK cells, stratified by age.
For patients ≥45yo, high rNK cell gene signature expression is associated with worse
survival outcomes (log-rank test, p-value < 0.05).
G. Boxplot showing heterogeneity calculated as 1 – ROGUE score for NK cells in each sample
by breast cancer clinical subtype (*p-value < 0.05). 


Supplemental Figure 6. Differential gene expression and gene set enrichment analyses
for each ERBB2 and TACSTD2 population, Related to Figure 2.
A. UMAP visualization of all epithelial cells in the integrated dataset, grouped by patient.
Consistent with other tumor type and breast tumor datasets, epithelial cells appear to cluster
by patient.
B. UMAP visualization of all epithelial cells in the integrated dataset, grouped by capture
technology.
C. UMAP visualization of all epithelial cells in the integrated dataset, grouped by source
dataset.
D. Boxplot showing % ERBB2+ cells by clinical subtype across samples in the integrated
dataset. As anticipated, % ERBB2+ cells were significantly enriched in HER2+ samples
compared to HR+ and TNBC samples (Kruskal-Wallis p < 0.05, with post-hoc Dunn test p-
values shown).
E. Scatterplot showing the Pearson correlation between HER2+ protein expression and ERBB2
mRNA expression across TCGA samples (p < 0.0001).
F. Gene set enrichment of the differentially expressed genes by ERBB2 Hi , ERBB2 Med , and
ERBB2 Lo cells. Significantly enriched gene sets from the MSigDB HALLMARK collection are
shown (Benjamini-Hochberg adjusted p-value < 0.05).
G. Gene set enrichment of the differentially expressed genes by TACSTD2 Hi , TACSTD2 Med ,
and TACSTD2 Lo cells. Significantly enriched gene sets from the MSigDB HALLMARK
collection are shown (Benjamini-Hochberg adjusted p-value < 0.05).
H. MA plot showing differentially expressed genes between ERBB2 Hi  vs. ERBB2 Med and
ERBB2 Lo cells (Bonferroni adjusted p-value < 0.05).
I. MA plot showing differentially expressed genes between ERBB2 Lo  vs. ERBB2 Hi and
ERBB2 Med cells (Bonferroni adjusted p-value < 0.05).
J. MA plot showing differentially expressed genes between TACSTD2 Med  vs. TACSTD2 Hi and
TACSTD2 Lo cells (Bonferroni adjusted p-value < 0.05).
K. MA plot showing differentially expressed genes between TACSTD2 Lo  vs. TACSTD2 Hi and
TACSTD2 Med cells (Bonferroni adjusted p-value < 0.05). 

Supplemental Figure 7. Analysis of clinical features and associations across samples in
the integrated dataset, Related to Figure 2.
A. Boxplots showing the proportion of TACSTD2-expressing cells per sample by nodal status,
split by clinical subtype (two-sided Wilcoxon test p-value as shown).
B. Boxplots showing the proportion of ERBB2-expressing cells per sample by nodal status,
split by clinical subtype (two-sided Wilcoxon test p-value as shown).
C. Boxplots showing the proportion of TACSTD2-expressing cells per sample by nodal status,
split by original source dataset (two-sided Wilcoxon test p-value as shown). The combined
result was not a statistically significant finding, though it does trend toward significance
(Fisher’s combined probability test, X = 11.227, p = 0.08). 

Supplemental Figure 8. Generation of the 10 gene elements of cancer epithelial cell
heterogeneity and exploration in breast cancer cell lines, Related to Figure 3.
A. Metrics used to select the number of clusters (10) for consensus clustering of signatures of
cancer epithelial cell ITTH.
B. Spherical k-means (skmeans) consensus clustering of the Jaccard similarities between
signatures of cancer epithelial cell ITTH, showing the probability (p1-p10) of each generated
signature of being assigned to one of 10 classes. Silhouette scores are shown for each
class or GE.
C. Heatmap of average z-scored expression of each of the 10 GEs across cancer epithelial
cells in each sample in our integrated dataset.
D. Heatmap of the absolute number of curated predicted receptor-ligand pairs between cancer
epithelial cells by GE and interacting immune and stromal cells.
E. Heatmap of average z-scored expression of each of the 10 GEs across human breast
cancer cell lines. Cell lines are annotated by molecular subtype (luminal, basal A, basal B,
HER2-amplified).
F. Cytotoxicity of NK-92 cells against BT-474, MDA-MB-436, and K562 cell lines, assessed by
% DAPI+ cells at 24 hr timepoint. BT-474 highly expressed NK-resistance GEs (GE1 and
GE6), while MDA-MB-436 has low expression of NK-resistance GEs. Cytotoxicity was
significantly reduced for the BT-474 cell line compared to the MDA-MB-436 cell line (3
biological replications; Benjamini-Hochberg adjusted, ***p-value < 0.001, ****p-value <
0.0001).
G. Scatterplots showing Spearman correlations of expression of GEs with limited predicted
interactions with NK cells (all but GE1 and GE6) and sensitivity to NK cell killing across
human breast cancer cell lines (Benjamini-Hochberg adjusted p-values > 0.05). 

Supplemental Figure 9. Predicted GE-immune interactions and spatial analysis of the 10
gene elements, Related to Figure 4.
A. Heatmap showing the proportion of spatial tumor sample spots within a sample that contain
each of the GEs and immune or stromal cell populations.
B. For a representative sample, UCell signature scores of each GE overlaid onto spatial tumor
sample spots with >10% presence of cancer epithelial cells.




'''
任务描述： 请根据描述详细讲解Fig.1a的结果和图例描述（不要用比喻的方式）,并根据结果和图例描述讲解完成这个图例的目的,输出格式如下：

    结果描述：
    图例描述：
    关键结论:
    分析目的：
