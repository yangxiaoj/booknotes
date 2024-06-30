你是一个生物信息学术专家，请详细阅读三引号中的文本，然后完成以下任务。 '''

# 标题：Single-cell and spatial transcriptomics analysis of non-small cell lung cancer

## Abstract

Lung cancer is the second most frequently diagnosed cancer and the leading
cause of cancer-related mortality worldwide. Tumour ecosystems feature
diverseimmunecelltypes.Myeloidcells,inparticular,areprevalentandhavea
well-established role in promoting the disease. In our study, we profile
approximately 900,000 cells from 25 treatment-naive patients with adeno-
carcinoma and squamous-cell carcinoma by single-cell and spatial tran-
scriptomics. We note an inverse relationship between anti-inflammatory
macrophagesandNKcells/Tcells,andwithreducedNKcellcytotoxicitywithin
the tumour. While we observe a similar cell type composition in both adeno-
carcinoma and squamous-cell carcinoma, we detect significant differences
in the co-expression of various immune checkpoint inhibitors. Moreover, we
reveal evidence of a transcriptional “reprogramming” of macrophages in
tumours, shifting them towards cholesterol export and adopting a foetal-like
transcriptionalsignaturewhich promotesironefflux.Ourmulti-omic resource
offers a high-resolution molecular map of tumour-associated macrophages,
enhancing our understanding of their role within the tumour
microenvironment.

## Introduction

Lung cancer is the second most commonly diagnosed cancer and the
first cause of cancer death worldwide 1 , with a 5-year survival of ~6% in
patients with the most advanced stages 2 . Non-small-cell lung cancer
(NSCLC) is the mostcommon type oflungcancer (~85%oftotal cases),
followedbysmall-celllungcancer(15%oftotalcases) 3 .Lungcancerisa
complex disease in which the tumour microenvironment plays a cri-
tical role and macrophages (Mɸ) are intimately involved in the pro-
gression of the disease. In particular, tumour-associated Mɸ (TAMs)
can exhibit a dual role, contributing to tumour promotion by
suppressing the immune response, facilitating angiogenesis, and aid-
ing in tissue remodelling, but also tumour suppression by promoting
inflammation and engaging in cytotoxic activity against cancer cells 4,5 .
The intricate interplay between lung cancer and Mɸ highlights the
importance of understanding their dynamic relationship in order to
develop more effective therapeutic strategies.
Within NSCLC, adenocarcinoma (LUAD) is the most common
histological subtype, followed by squamous-cell carcinoma (LUSC).
Lobectomy (i.e., the anatomical resection of a lung lobe) is currently the gold standard for the treatment of early stages of NSCLC (stage I/
II), while patients with unresectable stage III or metastatic stage IV
NSCLC are treated with a combination of chemotherapy and neoad-
juvant targeting vascular endothelial growth factor (VEGF) or immune
checkpoint inhibitors (ICIs) like PD1, PDL1 and CTLA4. Advancements
made in the last decade in uncovering predictive biomarkers have
paved the way for novel therapeutic prospects in the fields of targeted
therapy and immunotherapy on the basis of tumour histology and
PDL1 expression 6 .
A number of studies have employed single-cell technologies to
explore transcriptional changes in NSCLC 7–9 . They have extensively
examined the lung tumour microenvironment revealing diverse T-cell
functions linked to patient prognosis, relevance of diversity of B cells
in NSCLC for anti-tumour therapy, multiple states of tumour-
infiltrating myeloid cells, proposing them as a new target in immu-
notherapy, as well as the association of tissue-resident neutrophils
with anti-PDL1 therapy failure 7,10–14 . They further unveiled tumour
heterogeneity and cellular changes in advanced and metastatic
tumours 8,9 aswellastumourtherapy-inducedtransitionofcancercells
to a primitive cell state 15 . Inmany ofthesestudies, a limited number of
cells was analysed per patient, and often there was no systematic
collection of patient-matched non-tumour tissue, thus restricting dis-
section of the biological heterogeneity within tumour and adjacent
non-tumour tissue. Additionally, with some exceptions 9,14 , LUAD and
LUSC were considered as a single entity thus hindering the investiga-
tion of specific hallmarks of the two cancer types which are radically
distinct both at the molecular and pathological level. While single-cell
RNA-seq (scRNA-seq) can identify cell types and their states at high
resolutionwithintissues,itlacksthecapabilitytopinpointtheirspatial
distributionorcapturethelocalcell–cellinteractionsaswellasligands
and receptors that mediate these interactions. Therefore, impeding
our ability to fully explore the tumour microenvironment (TME) and
the complexity of cell–cell interactions therein.
To overcome above mentioned limitations, we combined scRNA-
seq data from nearly 900,000 cells from 25 treatment-naive patients
with LUAD or LUSC and spatial transcriptomics from eight patients to
investigate the differences in cellular organisation in tumour and
adjacentnon-tumourtissue.WefurtherexaminedMɸpopulationsand
molecular changes they undergo in the tumour environment, some of
which resemble those observed in Mɸ during human foetal
development.



## Results

### ScRNA-seq and spatial atlas of NSCLC samples
To determine the heterogeneity of immune and non-immune cellular
statesandtheirspatiallandscapeinLUADandLUSC,wecollectedlung
tissue resections from 25 treatment-naive patients with either LUAD
(n=13), LUSC (n=8) or undetermined lung cancer (LC, n=4), and two
healthy deceased donors (Fig. 1A, B and Supplementary Data 1). We
collected both tumour and matched normal non-tumorigenic tissue
(i.e., background), isolated CD45+ immune cells (Supplementary
Fig. 1A) as well as tumour and other non-immune populations (using
CD235a columnto deplete erythroidcells),andperformed scRNA-seq.
In addition, tumour and background tissue sections from eight
patients (of the aforementioned 25) were processed for spatial tran-
scriptomics using the 10x Genomics Visium platform (n=36 sections
in total) (Fig. 1A and Supplementary Data 1).
###  Tumours exhibit a higher diversity of immune and non-immune cells compared to adjacent lung tissue
Following qualitycontrol(QC) on the scRNA-seqdataset,we identified
895,806 high-quality cells in total, of which 503,549 were from
tumour and 392,257 from combined background and healthy tissue
(from here on referred to as B/H). After performing normalisation and
log1p transformation, highly-variable gene selection, dimensionality
reduction, batch correction, and Leiden clustering, cells originating
from tumour and B/H were separately annotated into distinct broad
cell types and visualised via Uniform Manifold Approximation and
Projection (UMAP) (Fig. 1C, Supplementary Fig. 1B, C, and “Methods”).
We identified clusters of myeloid cells with transcriptional signatures
ofmonocytes,macrophages,dendriticcells(DCs),aswellasmastcells,
natural killer (NK) cells, T cells, B cells and non-immune cells
(Fig. 1C, D). We did not detect neutrophilic granulocytes, most prob-
ably due to their sensitivity to degradation after collection and in
particular to the freezing-thawing cycle. Finally, we identified a cluster
characterisedbytheco-expressionofmyeloid(LYZ,CD68,CD14,MRC1)
and epithelial genes (KRT19, EPCAM) (Fig. 1D–F). These cells were
found within the tumour and exhibited similarities to previously
described cancer-associated macrophage-like cells (CAMLs) 16–18 .
CAMLs represent a distinct population of large myeloid cells with
concomitant epithelial tumour protein expression 19 . These unique
cells have been observed in blood samples of patients with various
malignancies, including NSCLC 20 . The abundance of CAMLs exhibits a
direct correlation with response to therapeutic interventions, high-
lightingtheirfunctionalsignificance 21 .Evenafterfurthersubclustering,
CAMLs maintained their distinct dual myeloid-epithelial signature
(Supplementary Fig. 1D). It is noteworthy that doublet detection soft-
wareScrubletassignedalowdoubletscoretoCAMLs,suggestingtheir
expression profile is unlikely to be explained as a combined signature
arising from the coincidental sequencing of a tumour cell and a mac-
rophage (Supplementary Fig. 1E). All clusters included cells from
multiple patients, with the cluster size ranging from 2520 to 124,459
cells (Supplementary Fig. 1F, G). Furthermore, we conducted
reference-query mapping using scArches 22 to confirm the consistency
of our annotations in the tumour and B/H dataset (Supplementary
Fig. 2A–C and Supplementary Notes).
The composition of the immune and non-immune compartment
was markedly different between the tumour and background. In the
tumour, we detected fibroblasts and a decrease in the fraction of
lymphatic endothelial cells (LECs) (P adj =0.0025, Fig. 1G and Supple-
mentary Data 2). Furthermore, the population of epithelial cells
showed higher diversity, with the presence of alveolar type II (AT2),
atypical epithelial cells which downregulated epithelial markers
(KRT19,EPCAM,CDH1),transitioningepithelialcellswhichupregulated
myeloid markers (LYZ), and cycling epithelial cells in tumour tissues
(Fig. 1G, Supplementary Notes, and Supplementary Fig. 2D, E). These
differences are in agreement with the fact that in tumour specimens,
epithelial cells are likely to be a mixture of mutant tumour and non-
mutant normal cells, and suggest that neoplastic transformation leads
tofurtherdiversityofcellstates.WedidnotdetectalveolartypeI(AT1)
or basal cells, possibly due to their loss during dissociations, as pre-
viously reported by others 8 .
As previously reported, the proportion of monocytes and imma-
ture myeloid cells was significantly reduced in tumour samples com-
pared to background (P adj = 0.022 and P adj =0.00001, respectively) 7 ,
while DCs and B cells were overall expanded 7 (P adj = 0.0023 and
P adj =0.0044, respectively; Fig. 1H and Supplementary Data 3). To get
further insight into the cellular composition of tumour versus back-
groundtissue,wesubclusteredeachofthebroadclustersandidentified
46 cell types/states (Supplementary Fig. 2D, E, Supplementary
Data 4 and 5, Supplementary Fig. 3, and Supplementary Notes). In the
tumour, we found that a significantly higher proportion of NK cells had
a lower cytotoxicity phenotype (Supplementary Notes), and that the
significantmajorityofDCswerederivedfrommonocytes(i.e.,mo-DC2),
(Supplementary Notes) compared to background (P adj = 0.00002 and
P adj =0.00002, respectively, Fig. 1I and Supplementary Data 6). This is
consistent with the monocytic origin of mo-DC2s under inflammatory
conditions 23 . Similarly, we found an expansion of B cells expressing LYZ
and TNF, and depletion of NKB cells (Fig. 1I and Supplementary Notes).
Among T cells, tumour samples showed an accumulation of regulatory T cells (Tregs), known to hinder the immune surveillance of tumours 24
(Fig.1I).Conversely,therewasareductionofexhaustedcytotoxicTcells
(P adj =0.00002) in the tumour and absence of γδ T cells, which have
been associated with survival in NSCLC 25 (Fig. 1I and Supplementary
Data 6). γδ T cells are capable of recognising and lysing diverse ranges
of cancer cells, and thus have been suggested for a role in pan-cancer
immunotherapy 26 . Finally, we saw an increase in heterogeneity and
proportion of anti-inflammatory Mɸ (AIMɸ), with a subset of cycling
anti-inflammatory Mɸ, STAB1+Mɸ (Fig. 1I) and CAMLs (Fig. 1H) being
abundantly present in tumour tissue. Interestingly, we found a strong negativecorrelationbetweenthefrequencyofSTAB1+Mɸ/AIMɸandT/
NK cells across patients, highlighting the key role of Mɸ in restraining
theinfiltrationofcytotoxiccellsinthelungtumourtissue(Fig.2A).This
is in line with a recent work describing that monocyte-derived Mɸ in
human NSCLC acquire an immunosuppressive phenotype and restrain
the infiltration of NK cells 27 .
### LUAD and LUSC have similar cellular composition but utilise different cell–cell interaction networks

LUAD and LUSC have very different prognoses and are often con-
sidered as different clinical entities 28 . To examine if differences in
clinicalfeaturesstemfromdistinctcellularcomposition,wecompared
the frequency of immune and non-immune cell subsets within CD235-
samples from LUAD versus LUSC patients. We observed minor differ-
encesincellfrequencythatdidnotreachstatisticalsignificanceafterP
value correction (Supplementary Fig. 4A and Supplementary
Data7and8).Furthermore,therewasnoclearassociationbetweenthe
frequency of immune and non-immune cells observed in patients and
the cancer subtype, cancer stage or sex (Supplementary Fig. 4B, C),
suggesting that the TME composition is rather similar in LUAD and
LUSC. While LUAD and LUSC shared similar cellular compositions, the
observed clinical distinctions may arise from varying intercellular interactions. Therefore, we examined whether different cell–cell
interaction networks were employed within the TME in LUAD versus
LUSC. To this end, we identified a putative list of cell–cell interactions
exclusively observed in each tumour type environment by inferring
statistically significant ligand–receptor pairs (L–Rs) that were not
detected in background or healthy and their corresponding celltypes,
using CellPhoneDB 29 . Although the two tumour subtypes showed a
similar interaction network that mostly involved interactions between
non-immune cells, AIMɸ and T cells (Fig. 2B), there were also some
notable differences.
First, we identified overall a higher number of L–Rs in the LUAD
dataset (Supplementary Fig. 4D and Supplementary Data 9–12), which
was not driven by a difference in the number of cells in the LUAD
(n=105,749 cells) vs LUSC (n=230,066 cells) dataset. Secondly, sev-
eral pairs of immune checkpoint inhibitors (ICI) and their respective
inhibitory molecules were differentially co-expressed in LUAD versus
LUSC (Fig. 2C, D). For example, LGALS9-HAVCR2 (TIM3), NECTIN2-
CD226(DNAM1)andNECTIN2/NECTIN3-TIGITwerefrequentlyidentified
inLUAD,andtheputativeICICD96-NECTIN1wasfoundpreferentiallyin
LUSC (Fig. 2C, D). In contrast, CD80/CD86-CTLA4 and HLAF-LILRB1/2
were found in both tumour subtypes (Fig.2C, D).LILRBs (leucocyte Ig-
like receptors) are emerging as potential targets for next-generation
immunotherapeutics as their blocking can potentiate immune
responses 30 . The most commonly used immunotherapies for lung
cancerblocktheinteractionbetweenPD1andPDL1,andrecentclinical
trials suggested that anti-CTLA4 and anti-PD1 combination therapy
improved the survival of patients independent of tumour PD1
expression 31,32 . Within our dataset, we did not observe PD1-PDL1
interactions in either of the tumour subtypes (Fig. 2C, D). Our initial
analysis suggests that other ICIs (such as CTLA4, TIGIT, LILRB1/2 and
TIM3) might be promising targets in the treatment of NSCLC.
OfthesignificantL–RsdetectedinbothLUADandLUSCwenoted
several pairs involved in angiogenic signalling in different populations
of myeloid cells such as VEGFA/B-FLT1, VEGFA-KDR and VEGFA-NRP1/2.
Although VEGFA and VEGFB were found to be expressed in both LUAD
and LUSC, their receptors were more frequently found in LUAD,
especially in fibroblasts (Fig. 2E and Supplementary Fig. 4E). Similarly,
we observed significant expression of EGFR ligands signalling in AT2
and cycling epithelial cells, such as EGFR-EREG, EGFR-AREG, EGFR-
HBEGF and EGFR-MIF, although MIF expression was found more fre-
quentlyin cellsfromLUSC(Fig. 2FandSupplementaryFig. 4F).Finally,
we observed key co-stimulatory signals required to support lymphoid
cell activation, such as CD40-CD40LG, CD2-CD58, CD28-CD86, CCL21-
CCR7, and TNFRSF13B/C-TNFSF13B (TACI/BAFFR-BAFF) (Supplementary
Fig. 4G), which are often associated with the presence of ectopic
lymphoid organs mainly consisting of B cells, T cells, and DCs i.e.,
tertiary lymphoid structures (TLS). TLS are usually correlated with the
longer relapse-free survival in NSCLC 33 .
### Integration of scRNA-seq and spatial transcriptomics validates L–R interactions in situ
The significant L–Rs and their interacting cell types were calculated
basedontheco-expressionofgenesindifferentcell-typeclustersfrom
the scRNA-seq dataset using CellPhoneDB. However, in order to dis-
cern biologically significant interactions, it is essential to ascertain
whether the cell types identified as interacting are indeed physically
co-located. To achieve this, we considered how the scRNA-seq-
identified cell types are spatially arranged on tissue sections. We
applied an integrative approach which combines the scRNA-seq of the
tumour and background samples with the spatialtranscriptomic (STx)
profileof the freshfrozen tumour and background tissue sections.We
performed 10× Visium on two consecutive, 10-µm sections, from eight
patients, seven ofwhichmatched the samples used for the scRNA-seq.
We analysed 36 sections in total (n tumour =20, n background =16) with an
average UMI count of 6894/spot in tumour and 3350/spot in the
background. Next, we used cell2location 34 and cell-type specific
expression profiles from our scRNA-seq dataset to deconvolute cell-
type abundances on the tissue (Fig. 3A, see “Methods”).
Once the cell types were resolved on the tissue sections, we
examined the frequencyof different celltypes across allsections from
tumour and background tissue. The cell-type abundance in tumour
and background were computed by summing up the posterior 5%
quantile (q05) value of estimated cell abundance by cell2location,
across spots that passed QC (“Methods”). Our analysis confirmed that
the differences in the frequency of cell types across all sections
in tumour versus background was in line with the results obtained
in the scRNA-seq data (Fig. 3B). For example, in tumours we found
an increase in the proportion of B cells (P adj =0.0372) and
cycling AT2 cells (P adj =0.0147) compared to the background tissue,
and a decrease in the proportion of immature cells (P adj =0.0012), NK
cells (P adj =0.0012), and LECs (P adj =0.00077, Supplementary
Data13and14).However,theproportionsofothercelltypesestimated
from the scRNA-seq data or the STx data within the tumour or back-
ground showed some discrepancies (Supplementary Fig. 4H, I). This
was particularly evident within the non-immune populations, where
STx estimated higher proportions of LECs, activated adventitial
fibroblasts and cycling subsets, compared to scRNA-seq. Disparities in
cell proportions between different methodologies were previously
shown by others 35,36 , underscoring the potential influence of distinct
samplingbiasesinherenttoscRNA-seqandSTxtechniqueslikeVisium.
InthecaseofscRNA-seq,variationsincelldigestionsensitivitycanlead
to differential representation of cell types. Meanwhile, with Visium,
discrepancies might arise from variations in the location of tumour
resections as well as differences in sample sizes compared to scRNA-
seq studies. Nevertheless, the overall concordance in the results
obtained by scRNA-seq and Visium suggests that our spatial “map” of
different cell types faithfully represents theirdistribution inthe tissue.
Next, we examined the spatial co-localisation of the L–Rs identi-
fied by cellphoneDB. The L–Rs were considered to co-localise if both
geneswereexpressedinthesamespotandabovemedianvalueforthe
givengenesacrossthesectionspots.Wethencomparedthefrequency
of spots in which L–R genes were colocalising versus non-colocalising
in the matched tumour versus background sections, using a χ 2 test
(“Methods”). Due to the low number of tissue blocks collected from
LUSC and LUAD patients (N LUSC =3, N LUAD =5), the statistical power
was not sufficient to perform a comparative analysis between spatial
localisation of LUAD/LUSC-specific L–Rs. Nevertheless, we confirmed
that several of the aforementioned tumour-specific L–Rs colocalized
significantly more in tumour than in background sections, including
NRP1-VEGFA and the ICIs NECTIN2-TIGIT, LGALS9-HAVCR2, and CD96-
NECTIN1 (Fig. 3C–E and Supplementary Data 15). Consistent with the
cellphoneDB results, we found no significant colocalization of PD1-
PDL1 in the tumour sections.
### CAMLs share similar copy number aberrations (CNAs) with tumour cells

Tumour samples obtained from surgical resection contain both
malignant and residual normal epithelial cells. A significant challenge
in scRNA-seq of human tumours lies in the differentiation of cancer
cells from non-malignant counterparts. Therefore, we applied Copy-
number Karyotyping of Tumors (CopyKAT 37 ) to discern genome-wide
aneuploidy within individual cells. The principle driving the compu-
tation of DNA copy number events from scRNA-seq data is rooted
in the notion that the expression levels of neighbouring genes
can provide valuable information to infer genomic copy numbers
within that specific genomic segment. Since aneuploidy is common in
human cancers, cells with genome-wide CNAs are considered as
tumour cells.
AnalysisusingCopyKATrevealedextensive,patient-specificCNAs
in tumour tissue (Fig. 4A and Supplementary Fig. 5A) but not in the background. Within individual tumour samples, the CNAs were
detected in AT2 and cycling AT2 cells, and in some patients these
genetic alterations were shared between AT2/cycling AT2 cells and
atypical epithelial cells, suggesting a close lineage relationship
between different epithelial subpopulations (Fig. 4A and Supplemen-
tary Fig. 5A). We confirmed this finding by inferring the trajectory of
non-blood cell populations in tumour using Partition-Based Graph
Abstraction (PAGA) 38 . PAGA showed differentiation continuity
between AT2 cells, cycling AT2/epithelial cells, and atypical epithelial
cellsononesideandciliatedepithelialcellsandtransitioningepithelial
cells on the other (Fig. 4B). Furthermore, blinded histological evalua-
tion confirmed the overlap between pathologist-defined tumour sites
and AT2 and cycling AT2 cells predicted by cell2location, suggesting
their tumour cells status (Fig. 4C). Less overlap was observed for aty-
pical epithelial cells (Fig. 4C). The differential expression analysis
(DEA) of AT2 cells from tumours compared to background showed
upregulation of genes involved in hypoxia, TP53 pathways, and
metabolic rewiring in tumours. AT2cells intumour-upregulated genes
involvedbothinglycolysisandoxidative phosphorylation(Fig.4Dand
Supplementary Data 16).While the importanceofglycolysis intumour cells is well-established 39 , it was recently reported that human NSCLC
use glucose and lactate to fuel the tricarboxylic acid (TCA) cycle 40 . In
addition, the tumour AT2 cells were noted to express more LYPD3
compared to background AT2 cells (log2FC=2.04, P adj =0.039, Sup-
plementary Data 16), an adhesion protein which has previously been
connectedtopoor prognosisin NSCLCandis currentlybeing targeted
in preclinical and clinical studies 41,42 .
Interestingly, the population of CAMLs also showed substantial
CNAs that were similar to those of AT2 cells and cycling AT2 cells
from the same patient (Fig. 4A, E and Supplementary Fig. 5A, B). To
measure the difference of the distribution of genomic gain and loss
between cell types in a statistically robust manner, we calculated the
Kullback–Leibler (KL) divergence (Fig. 4F and Supplementary Fig. 5C).
CAMLs had KL divergence values comparable to CNA-harbouring tumour cells, thus confirming the similarity of their CNA profiles
(Fig. 4F and Supplementary Fig. 5C). As CAMLs co-expressed a wide
arrayofmyeloidgenesaswellastypicalepithelialgenes(Fig. 1D–Fand
Supplementary Fig. 1D), had a low doublet score and shared the same
CNA signature as tumour cells, we hypothesised that these cells might
represent a subset of Mɸ tightlyattached to a cancer cell. It is possible
that these Mɸ were undergoing phagocytosis or fusion.
CAMLs have been previously isolated from peripheral blood of
cancer patients and described to facilitate circulating tumour cells
seedingofdistantmetastases 16 .OuranalysissuggestedthatCAMLscan
also be isolated from tumour tissue. To validate that CAMLs are in
physical proximity to tumour cells in situ we examined our STx sec-
tions. We calculated across all sections (8 patients, n sections =20) the
Pearson correlation between the relative abundance of the cell types
thatresideinthesamespotandarethereforeco-localised.Ouranalysis
showed that CAMLsindeed co-localised with AT2 cells (Fig. 4G, H). We
confirmed this finding using non-negative matrix factorisation (NMF)
on the absolute cell-type abundances estimated by cell2location that
defined factors of co-occurring cell states (Fig. 4I).
To determine the specific Mɸ population from which CAMLs
likely originate, we employed PAGA to elucidate the differentiation
path of the myeloid cell population in our tumour dataset (Supple-
mentary Fig. 5D). The analysis revealed continuity of the differentia-
tion transitions between diverse populations ofmyeloid cells 43 . Within
the PAGA trajectory, alveolar Mɸ (AMɸ) and AIMɸ showed high PAGA
connectivityindicating their high transcriptional similarity.Both AIMɸ
and AMɸ showed the strongest connectivity on the PAGA trajectory
with STAB1+Mɸ which, in turn, were linked with CAMLs. In line with
trajectory analysis, CAMLs co-expressed many of the genes specific to
STAB1+Mɸ (Supplementary Fig. 2A), supporting the hypothesis that
CAMLs are likely derived from STAB1+Mɸ following their close
interaction with tumour cells. Finally, DEA analysis between CAMLs
from LUSC versusLUADpatients,showed upregulation of KRT17, KRT5
andKRT6AinLUSCsamples(SupplementaryData17).TheseKRTgenes
were previously identified as markers of LUSC in multiple studies 44,45 ,
which supports hypothesis that CAMLs arise from the interaction
between Mɸ and tumour cell.
### TAMs promote cholesterol and iron efflux in tumour

Mɸ, traditionally categorised into distinct M1 (classically activated)
and M2 (alternatively activated) phenotypes, are now understood to
exist along a dynamic spectrum of functional states 46 . This concept of
Mɸ plasticity underscores their ability to seamlessly transition
between pro-inflammatory and anti-inflammatory roles in response to
intricate cues from their microenvironment (Supplementary Fig. 5D).
To better understand the transcriptional changes that different Mɸ
populations undergointhe TME,we performedDEA.In tumours,both
AMɸ and AIMɸ upregulated genes involved in cholesterol and lipid
transport and metabolism (such as ABCA1, APOC1, APOE, FABP3 and
FABP5) compared to the background tissue (Fig. 5A, B and Supple-
mentary Data 18 and 19). Cholesterol plays a vital role in tumour
growth due to the high demand of newly synthesised cellular mem-
branes during cancer cell proliferation. Hypoxia-related genes were
upregulated in AT2 cells in tumour compared to the background
(Fig. 4D), which can promote cholesterol auxotrophy in tumour cells
by suppressing cholesterol synthesis, thereby forcing them to rely on
exogenous cholesterol uptake 47 . In our dataset, we detected higher
expression of the cholesterol exporter ABCA1 and no expression of
low-density lipoprotein receptor (LDLR) in AMɸ and AIMɸ, the latter
gene being responsible for the uptake of cholesterol-carrying lipo-
protein particles into cells, suggesting preferential export of choles-
terol from TAMs to the TME (Fig. 5A). Interestingly, we also noted a
highexpressionofTREM2inbothAMɸandAIMɸ(Fig.5A),whichplays
a prominent role in efflux of cholesterol in microglia 48–50 . To validate
the increased levels of cholesterol in the TME, we stained matched
tumourandbackgroundtissuesectionswithBODIPY™493/503,astain
targeting cholesterol and other neutral lipids. We found a significant
increase in the BODIPY signal in the tumour sections, compared to
background tissue (Fig. 5C, D), confirming an increased availability of
neutrallipids in the tumour,possibly asa result of anincreased export
by TAMs.
STAB1+Mɸ were identified in the tumour resections (Fig. 5E–H,
Supplementary Fig. 2 and Supplementary Notes), so we used DEA to
identify a set of genes that were specific for STAB1+Mɸ compared to
tumourAIMɸorAMɸ.Weidentified20genes,fromhereonreferredto
as“STAB1signaturegenes”(Fig.5I).Interestingly,STAB1+Mɸuniquely
expressedSLC40A1,whichencodesfortheferroportin,theonlyknown
proteinthatexportsferrousironfromthecytoplasmacrosstheplasma
membrane and is key for the iron-releasing activity of macrophages
(Fig. 5I, J and Supplementary Data 20 and 21) 51 . Ferroportin-mediated
release of free iron by M2 Mɸ was reported to promote the pro-
liferation of renal carcinoma cells in vitro, possibly by supporting the
high iron requirement due to increased DNA synthesis 52 . Furthermore,
comparedtoAMɸ,STAB1+Mɸexpressedlowerlevelsofferritinheavy
chain1(FTH1)andferritinlightchain(FTL)encodingfortheironstorer
ferritin (Fig. 5J and Supplementary Data 20). Consistent with the
hypothesis of their sustained export of free iron to the extracellular
milieu, STAB1+Mɸ downregulated genes involved in iron sequestra-
tion (Fig. 5K). Taken together, our analysis suggests that macrophages
undergo “reprogramming” withinthe TMEand adopt a transcriptional
signature that facilitates cholesterol efflux and iron export, thus sup-
porting tumour progression.
### STAB1+Mɸ in tumour tissue undergo oncofoetal reprogramming

Embryonic development shares many characteristics with tumour
tissue, including rapid cell division, cellular flexibility, and a highly
vascular microenvironment. It has been recently reported that during
tumorigenesis, Mɸ can undergo oncofoetal reprogramming 53 and
acquire a foetal-like transcriptional identity that supports tumour
growthandmetastasis 53 .ConsideringthatsomeoftheSTAB1signature
genes are typically expressed by foetal Mɸ (such as STAB1, FOLR2,SLC40A1, MERTK, GPR34 and F13A1) 54 , we wanted to explore if further
transcriptional commonalities exist between tumour-originating
STAB1+Mɸ and Mɸ isolated from human foetal lung. To this end,
we combined tumour- and background-originating myeloid cells from
ourdataset(n=347,364cells)withmyeloidandprogenitorcellsfroma
publicly available foetal lung scRNA-seq dataset 55 (n=6,947 cells)
using Harmony. Next, we performed Leiden clustering on the neigh-
bourhood graph and examined how cell types are distributed within
the clusters (Supplementary Fig. 6A, B). To examine similarity in their
gene expression profile, we applied hierarchical clustering and built a dendrogramby estimating the correlation distancebetween celltypes
on the harmonised PC embedding space, under the complete linkage
criterion of hierarchical clustering (Fig. 6A).
We observed that tumour cDC2 exhibited the strongest corre-
lation with background cDC2, whereas tumour mo-DC2 displayed
the highest correlation with foetal DC2 and, in a broader context,
with background mo-DC2. The population of pDC from tumour,
background and foetal lung were closely correlated. Similarly,
tumour monocytes were correlated with foetal classical monocytes
and background monocytes. In contrast, macrophage populations in
tumour, and in particular STAB1+Mɸ, were correlated with foetal
macrophages. STAB1+Mɸ clustered predominantly with foetal
SPP1+Mɸ (Fig. 6A), which accounted for over 80% of all foetal
lung macrophages reported in ref. 55. Consistent with this
finding, SPP1+Mɸ had a high expression of the “STAB1 signature
genes” compared to other haematopoietic populations (Fig. 6B, C).
Our analysis substantiates the idea that monocytes within the
tumour environment, as they undergo differentiation into anti-
inflammatory macrophages, acquire a transcriptional signature akin
to that of foetal macrophages. This distinctive transcriptional sig-
nature was not observed in the macrophages from surrounding
normal tissue. To further examine the prevalence of STAB1+Mɸ in other
pathologies, including other cancers, we examined the expression of
“STAB1signaturegenes”acrossadiversegroupofmyeloidcellsusinga
published atlas of human monocytes and Mɸ collected from 12 dif-
ferenthealthyandpathologictissues(n=140,327cells),calledMoMac-
VERSE 56 . The cluster of “HES1+ macrophages” identified in MoMac-
VERSE showed the highest expression of the “STAB1 signature genes”
(Fig.6D,E).SimilartoSTAB1+Mɸ,HES1+macrophagesaccumulatedin
tumours of lung cancer patients but also liver cancer patients 57 and
were suggested to represent a cluster of “long-term resident-like” Mɸ
with foetal-like transcriptional signature 56 . In contrast, “C1Q” Mɸ from
MoMac-VERSE, which have been described as lung alveolar Mɸ, had a
high expression of genes unique to our tumour alveolar AMɸ (from
hereonreferredas“AMɸsignaturegenes”,Fig.6F,H).Inthecontextof
foetal lung, a rare population of APOE+Mɸ, which accounted for less
than 1% of all foetal lung macrophages reported in ref. 55, had a high
AMɸ signature genes score (Supplementary Notes and Fig. 6G, I, see
“Methods”).
Taken together, our analysis suggests that tumour macrophages,
especially STAB1+Mɸ, exhibited a transcriptional signature reminis-
cent of Mɸ during foetal lung development, suggesting that they have
undergone oncofoetal reprogramming within the NSCLC tumour
environment.

## 图例部分


Fig. 1 | Single-cell transcriptomics reveal the heterogeneity of NSCLC. A Study
overview. Single-cellsuspensions ofresected tumour tissue,adjacent non-involved
tissue (background) and healthy lung from deceased donors were enriched for
CD45+ or CD235− and subjected to scRNA-seq. Cryosections of fresh, flash-frozen
tumour, background and healthy tissues were used for 10x Visium spatial tran-
scriptomics. B Cohort overview. Symbols represent individual patients and per-
formed analyses. C UMAP projection of tumour and combined background
+healthy datasets. D Dotplot of representative genes used for broad cell-type
annotations in tumour samples. E Contour plot showing the co-expression of
myeloid(LYZ,CD68,MRC1) andepithelial(EPCAM)genesinAT2cells(44,399cells),
CAMLs (2520 cells) and AIMɸ (16,120 cells). Normalised, scaled and log-
transformed gene expression. F Boxplot showing normalised, scaled and log-
transformed gene expression of myeloid (LYZ, APOE, CD68, MRC1) and epithelial
(EPCAM, KRT8, KRT19) genes in AT2 cells, CAMLs and AIMɸ. Boxes: quartiles.
Whiskers: 1.5× interquartile range. G Relative proportion of non-immune cell sub-
sets in tumour and background, calculated within the CD235− enrichment. Arrows
indicate increase (↑) or decrease (↓) in tumour versus background. Pairwise
comparisons by two-sided Wilcoxon rank test and Bonferroni correction for mul-
tiple comparisons. **P<0.01. Arrows without asterisks indicate that the cell type
was found only in tumour or background. H Relative proportion of broad immune
cellsintumourandbackground,calculatedwithinallimmunecellsidentifiedinthe
CD235- enrichment. Arrows indicate an increase (↑) or decrease (↓) in tumour
versus background. Pairwise comparisons by two-sided Wilcoxon rank test and
Bonferroni correction for multiple comparisons. *P<0.05, **P<0.01, ***P<0.001.
Arrows without asterisks indicate that the cell type was found only in tumour or
background. I Relative proportion of NK, DC, B, T and macrophage subsets within
the broad annotations in tumour and background, calculated within the CD235-
enrichment. Arrows indicate increase (↑) or decrease (↓) in tumour versus back-
ground. Pairwise comparisons by two-sided Wilcoxon rank test and Bonferroni
correctionformultiplecomparisons.***P<0.001.Arrowswithoutasterisksindicate
that the cell type was found only in tumour or background.


Fig. 2 | Integrated single cell and spatial transcriptomics uncovers different
interaction networks in LUAD and LUSC. A Heatmap showing the Pearson cor-
relation between the relative cell-type abundance for each immune cell type (cal-
culated within the CD235− enrichment). Colour indicates the Pearson correlation
value, asterisks indicate the level of significance of the two-sided association test
computed on Pearson’s product-moment correlation coefficients (*P<0.05,
**P<0.01,***P<0.001).BHeatmapshowingthenumberofLRinteractionsbetween
allcelltypessummarisedbybroadcellannotationsinLUAD(left)andLUSC(right).
Rows were hierarchically clustered using the complete linkage method on eucli-
dean distances. C Sankey diagram showing the tumour-specific interactions in
LUAD and LUSC for selected ICIs detected by cellphoneDB. Line colour identifies
whether the LR interaction between each cell type was found in LUAD only
(orange),inLUSConly (green)orinboth tumourtypes (blue).DDotplot forthe ICI
genes and cell types highlighted in (C), split by tumour type. The size of each dot
represents the percentage of cells in the cluster expressing the gene, while the
colour represents the mean normalised scaled log-transformed expression of each
gene in each group. E Sankey diagram showing the tumour-specific interactions in
LUAD and LUSC for VEGFA/B interactors detected by cellphoneDB. Line colour
identifies whether the LR interaction between each cell type was found in LUAD
only (orange), in LUSC only (green) or in both tumours (blue). F Sankey diagram
showing the tumour-specific interactions in LUAD and LUSC for EGFR interactors
detected by cellphoneDB. Line colour identifies whether the LR interaction
betweeneachcelltypewasfoundinLUADonly(orange),inLUSConly(green)orin
both tumours (blue).


Fig. 3 | 10x Visium confirms the spatial colocalization of key
ligand–receptorpairs.ASpatialimagesdepictingthecellabundanceestimatedby
cell2location for AT2 cells, AIMɸ and Tregs on a representative tumour section.
B Relative proportion of immune (left) and non-immune (right) cell types calcu-
latedonthecellabundanceestimationsbycell2locationintumourandbackground
sections.Immunecellsweregroupedaccordingtotheirbroadannotations.Arrows
indicate an increase (↑) or a decrease (↓) in the tumour, compared to the back-
ground.Pairwisecomparisonswereperformedwithatwo-sidedWilcoxonranktest
and Bonferroni correction for multiple comparisons. *P<0.05, **P<0.01,
***P<0.001. Arrows without asterisks indicate that the cell type was found only in
the tumour or background. Please refer to Supplementary Data 13 and 14 for the
exact P values. C Heatmap of spatial LR colocalization. LR gene pair co-expression
was estimated in each spot for all sections, and the frequency of colocalising vs.
non-colocalising spotsin thetumourandbackgroundwascomparedusingaχ 2 test
followed by Bonferroni multiple comparison correction. Dark-grey tiles indicate
that the frequency of colocalising gene pairs was significantly different in tumour
and background sections. Green column annotations indicate the LR pairs which
were significant in at least four out of eight patients. Row annotations indicate
tumourtype.DBoxplotshowingthefrequencyofcolocalisingLRpairssignificantly
different in tumour vs background in each section analysed. N=8 patients. Boxes
are plotted with default settings in the Python Seaborn package, i.e., boxes show
quartiles with whisker length being 1.5 times the interquartile range. Source data is
provided as a Source Data file. E Spatial images depicting the location of spots in
which the LR pair was found co-expressed in tumour (top) and background (bot-
tom), for NRP1-VEGFA, NECTIN2-TIGIT, PD1-PDL1, CD96-NECTIN1 and HAVCR2-
LGALS9. Representative sections from one patient.


Fig. 4 | CAMLs share tumour CNAs and colocalise with tumour cells. A CNA
analysis. The plot shows chromosomal gains (red lines) and losses (blue lines)
estimatedbyCopyKatineachchromosomearmfordifferentcelltypesandpatients
in the tumour dataset. All immune cell types were grouped together for plotting
purposes.BPAGAgraphoverlaidonthediffusionmaps(force-directedlayout—FLE
embedding)computed for non-immune celltypes in tumour.C First three panels—
Representative blind annotations from a qualified pathologist, indicating the areas
oftumourinfiltration(left),binningofthetumourareaontheVisiumspots(centre)
andthespotsthatpassedQC(right).Thelastthreepanels—cell2locationestimation
for AT2 cells (left), Cycling AT2 cells (centre) and Atypical epithelial cells (right) on
the same sections, overlaid with the pathologist’s annotation for the tumour infil-
tration (green contour). D Overrepresentation analysis on gene ontology—biolo-
gical processes (GO:BP) and REACTOME database by clusterProfiler R package,
using DEGs upregulated by AT2 cells in tumour vs background. Source data is
providedasaSourceDatafile.EDetailedoverviewofCNAsinAT2andCAMLsfrom
the tumour of one representative patient. Bars indicate the frequency of cells
harbouring chromosomal gains (red bar) or losses (blue bars) in specific chromo-
somal regions. F Scatterplot of the KL divergence for losses (x axis) and gains (y
axis) between each cell type in the tumour dataset calculated using their gain and
loss distribution. All immune cell types were grouped together for plotting pur-
poses.GSpatialimagesdepictingthecellabundanceestimatedbycell2locationfor
AT2 cells and CAMLs on three representative tumour sections. H Hierarchical
clustering of the correlation distance calculated on cell-type composition (as esti-
mated by cell2location) across spots that passed QC in all tumour sections. I Non-
negative matrix factorisation built on the q05 estimation of cell-type abundance
across spots that passed QC (as estimated by cell2location) in all tumour sections.


Fig. 5 | Tumour macrophages undergo oncofoetal reprogramming. A Volcano
plot of DEGs (red) for AIMɸ in tumour vs background, extracted using the py_DE-
Seq2 package. B Overrepresentation analysis on gene ontology—biological pro-
cesses database by clusterProfiler R package, using the DEGs upregulated by
Alveolar Mɸ and AIMɸ in tumour vs background. Source data is provided as a
Source Data file. C IHC for CD68 and neutral lipids (BODIPY 493/503) on tumour
and background tissue sections. Maximum intensity projection of Z-stacks. Scale
bar50µm.DAreacoveredbytheBODIPYsignalintumourandbackgroundsection.
The difference in BODIPY area coverage was determined with a paired, two-sided t
test, matching tumour and background sections from the same patients. N=5
patients.SourcedataisprovidedasaSourceDatafile.EIHCforCD68andSTAB1on
tumour(left)andbackground(right)tissuesections.Maximumintensityprojection
of Z-stacks. Inlets show a detailed magnification on a single cell. Scale bar 20µm.
F Quantification of STAB1+ cells within the CD68+ macrophage population. The
fraction of the STAB1+CD68+ area is shown as a percentage of the total CD68+
area. Data are presented as mean value and standard deviation (n=3 biological
replicates). Source data is provided as a Source Data file. G Staining for CD68,
STAB1 and PanCK on tumour tissue sections. Maximum intensity projection of
Z-stacks. Inlets show a detailed magnification on a single cell. Scale bar 20µm.
HQuantificationofSTAB1+CD68+cells withinthe CD68+ macrophage population
in NSCLC. Data are presented as mean value and individual data points (n=2 bio-
logical replicates). Source data is provided as a Source Data file. I Dotplot showing
the expression of the “STAB1 signature genes” across all macrophage subsets and
CAMLsintumour.JVolcanoplotofDEGsidentifiedbypy_DESeq2(red)forAlveolar
Mɸ vs STAB1 Mɸ in tumour. K Overrepresentation analysis on gene ontology—
biological processes database by clusterProfiler R package, using the DEGs from
Alveolar Mɸ vs STAB1 Mɸ (top) and AIMɸ vs STAB1 Mɸ (bottom) in tumour (left—
upregulated by STAB1 Mɸ; right—upregulated by Alveolar Mɸ or AIMɸ). Source
data is provided as a Source Data file.


Fig. 6 | STAB1+Mɸ undergo oncofoetal reprogramming. A Hierarchical clus-
teringofthecorrelationdistancecalculatedoneachcellintheharmonised(tumour
myeloid + background myeloid + foetal lung myeloid) PC space. B Violin plot
showing the expressionlevelofthe “STAB1genesignature”acrossmyeloidcelland
progenitor populations identified in a publicly available human foetal lung atlas.
C Dotplot of the expression of each gene in the “STAB1 gene signature” in selected
foetal lung macrophage populations. The size of each dot represents the percen-
tage of cells in the cluster expressing the gene, while the colour represents the
meanexpressionofeachgene ineachcluster.DViolinplotshowingthe expression
level of the “STAB1 gene signature” across the clusters identified in the publicly
available MoMac-VERSE dataset. E Dotplot of the expression of each gene in the
“STAB1 gene signature” in selected macrophage populations from the MoMac-
VERSE. The size of each dot represents the percentage of cells in the cluster
expressingthe gene,while thecolourrepresentsthemeanexpressionofeachgene
in each cluster. F Violin plot showing the expression level of the “AMɸ gene sig-
nature” across myeloid cell and progenitor populations identified in the publicly
available “MoMac-VERSE” dataset. G Violin plot showing the expression levelofthe
“AMɸ gene signature” across myeloid cell and progenitor populations identified in
a publicly available human foetal lung atlas. H Dotplot of the expression of each
gene in the “AMɸ gene signature” in selected macrophages populations identified
in the “MoMac-VERSE” dataset. The size of each dot represents the percentage of
cells in the cluster expressing the gene, while the colour represents the mean
expression ofeach gene ineach cluster. I Dotplot of the expressionof eachgenein
the“AMɸgenesignature”inselectedfoetallungmacrophagepopulations.Thesize
of each dot represents the percentage of cells in the cluster expressing the gene,
while the colour represents the mean expression of each gene in each cluster.


Supplementary Figure 1: Sorting strategy and scRNA-seq quality control
A. Representative plots showing the gating strategy used to enrich CD45+ and MDSCs. Debris was
excluded by gating on FSC-A/SSC-A; singlets were gated on FCS/TPW; dead cells were excluded by
gating on Zombie-aqua negative cells, then CD45+ cells were sorted. MDSCs were identified as CD45
positive, Lineage (CD3, CD19, CD56) negative, CD33 positive, HLA-DR dim/negative cells.
B and C. UMAP projection of the tumour (B) and combined B/H (C) datasets after batch correction. Colours
represent each library sequenced.
D. Violin plot showing the scaled, normalised, log-transformed gene expression of myeloid- (LYZ, APOE,
CD68, MRC1), immune- (PTPRC) and epithelial- (EPCAM, KRT8, KRT19) specific genes in AT2 cells,
anti-inflammatory macrophages and 10 CAML subclusters calculated by k-means. The values above each
plot indicate the number of cells in each sub-cluster.
E. Scatterplot showing the doublet score estimated by Scrublet for each individual cell (y axis) versus total
counts (x axis - left) and number of genes by counts (x axis - right). CAMLs are highlighted in brown, all
other cell types are in light blue.
F and G. Relative proportion of broad immune and non-immune cells in the tumour (F) and background
and healthy (G) datasets, calculated within all libraries in each patient.


Supplementary Figure 2: Detailed annotation of the scRNA-seq dataset
A. Heatmap representing the results of label transfer. Each square represents the fraction of cells in each
broad category on the B/H dataset (original labels) that was assigned to each tumour label (predicted
labels).
B. Scatterplot representing the relative abundance of each broad immune cell in the B/H dataset before
(original labels) and after label transfer (predicted labels).
C. Dotplot showing the expression of myeloid marker genes in the B/H dataset for monocytes that were
labelled as monocytes (mono→mono), monocytes that were labelled as DCs (mono→DCs), and DCs that
were labelled as DCs (DCs→DCs). The size of each dot represents the percentage of cells in the cluster
expressing the gene, while the colour represents the mean normalised scaled log-transformed expression
of each gene in each cluster.
D. UMAP projection (top) and dotplot (bottom) of representative genes used for detailed cell type
annotations in the tumour dataset. Colours and numbers represent detailed cell type annotations. The size
of each dot represents the percentage of cells in the cluster expressing the gene, while the colour
represents the mean normalised scaled log-transformed expression of each gene in each cluster.
E. UMAP projection (top) and dotplot (bottom) of representative genes used for detailed cell type
annotations in the B/H dataset. Colours and numbers represent detailed cell type annotations. The size of
each dot represents the percentage of cells in the cluster expressing the gene, while the colour represents
the mean normalised scaled log-transformed expression of each gene in each cluster.


Supplementary Figure 3: scRNA-seq metrics for detailed annotations
A and B. Number of UMIs (A) and genes (B) per cell type in the tumour dataset.
C and D. Number of UMIs (C) and genes (D) per cell type in the B/H dataset.


Supplementary Figure 4: LUAD and LUSC have similar cellular composition
A. Relative proportion of NK, B, DC, T and macrophages subsets within the broad annotation in LUAD
(left) and LUSC (right), calculated within the CD235- enrichment.
B and C. Heatmap showing the relative proportion of all immune cell subsets (B) and non-immune cell
subsets (C) in each patient within the CD235- enrichment. Annotations indicate the broad tumour stage
(T1-T4), cancer type (LUAD, LUSC and non-annotated lung cancer LC), and sex. Rows and columns were
hierarchically clustered using the complete linkage method on euclidean distances.
D. Venn diagram showing the number of significant cell-cell L-R pairs identified by cellphoneDB
independently on the tumour dataset split on LUAD and LUSC, the background dataset, and the healthy
dataset.
E. Dotplot showing the expression of the genes highlighted in the Sankey diagram in Figure 2E.
F. Dotplot showing the expression of the genes highlighted in the Sankey diagram in Figure 2F.
G. Sankey diagram showing the tumour-specific interactions in LUAD and LUSC for co-stimulatory
molecules detected by cellphoneDB. Line colour identifies whether the LR interaction between each cell
type was found in LUAD only (orange), in LUSC only (green) or in both tumours (blue).
H. Barplot showing the relative abundance of broad immune cell types calculated from the scRNA-seq
dataset (green) and from the VIsium dataset (orange).
I. Barplot showing the relative abundance of non-immune cell types calculated from the scRNA-seq dataset
(green) and from the VIsium dataset (orange).


Supplementary Figure 5: Detailed CNA results for each patient
A. CNA analysis. The plot shows chromosomal gains (red lines) and losses (blue lines) estimated by
CopyKat in each chromosome arm, for different cell types and all patients in the tumour dataset. All
immune cell types were grouped together for plotting purposes.
B. Detailed overview of CNAs in AT2 and CAMLs from each patient where we detected CAMLs and AT2
cells. Bars indicate the frequency of cells harbouring chromosomal gains (red bar) or losses (blue bars) in
specific chromosomal regions in the tumour dataset.
C. Scatterplot of the KL divergence of losses (x-axis) and gains (y-axis) between each cell type calculated
using their gain and losses distribution for the same patient in panel B. All immune cell types were grouped
together for plotting purposes.
D. PAGA graph overlaid on the diffusion maps (force-directed layout - FLE embedding) computed for
macrophage clusters, immature myeloid cells and CAMLs in tumour.


Supplementary Figure 6: Foetal, tumour and background data integration
A. UMAP of the integrated foetal lung myeloid, background myeloid and tumour myeloid dataset, coloured
by the origin of each cell. In the inlet, same UMAP coloured by Leiden cluster.
B. Distribution of each cell group in the leiden clusters of the integrated foetal lung myeloid, background
myeloid and tumour myeloid dataset.
C. Median log(fold-change) and adjusted p-value for each DEA iteration between AMɸ and STAB1+ Mɸ.
Coloured lines depict the moving median value across 100 iterations.




'''
任务描述： 请根据描述详细讲解Fig.1a的结果和图例描述（不要用比喻的方式）,并根据结果和图例描述讲解完成这个图例的目的,输出格式如下：

    结果描述：
    图例描述：
    关键结论:
    分析目的：
