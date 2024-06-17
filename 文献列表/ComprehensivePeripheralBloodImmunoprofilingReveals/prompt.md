你是一个生物信息学术专家，请详细阅读三引号中的文本，然后完成以下任务。 '''

# 标题：Comprehensive peripheral blood immunoprofiling reveals five immunotypes with immunotherapy response characteristics in patients with cancer

## Abstract:

The lack of comprehensive diagnostics and consensus analytical models for evaluating the status of a pa-
tient’s immune system has hindered a wider adoption of immunoprofiling for treatment monitoring and
response prediction in cancer patients. To address this unmet need, we developed an immunoprofiling plat-
form that uses multiparameter flow cytometry to characterize immune cell heterogeneity in the peripheral
blood of healthy donors and patients with advanced cancers. Using unsupervised clustering, we identified
five immunotypes with unique distributions of different cell types and gene expression profiles. An indepen-
dent analysis of 17,800 open-source transcriptomes with the same approach corroborated these findings.
Continuous immunotype-based signature scores were developed to correlate systemic immunity with pa-
tient responses to different cancer treatments, including immunotherapy, prognostically and predictively.
Our approach and findings illustrate the potential utility of a simple blood test as a flexible tool for stratifying
cancer patients into therapy response groups based on systemic immunoprofiling.

## Introduction

Humanpopulationsaregeneticallyanddevelopmentallydiverse,
with their immune systems shaped by unique immunological
challenges from aging, microbial exposure, metabolic changes,
and chronic diseases such as cancer. 1 The composition of each
immune system determines how an individual responds to
different immunological stimuli, including those from anti-cancer
therapies.
Increasingly, immunotherapies have become an essential part
of treatment plans that typically also include aggressive chemo-
therapy and radiation, for patients with advanced solid tumors. 2
These treatments affect the patient’s immune system and can
interfere withits capacity to respond to subsequent therapy lines
and combinations. 3 Although immunotherapies such as immune
checkpoint blockade (ICB) have been clinically successful over
the last decade, response rates are still largely unpredictable in
most patients, and serious immune-related adverse events often
emerge. 4,5 Unfortunately, analysis of gold-standard molecular
biomarkers such as PD-L1, microsatellite instability (MSI), DNA
mismatch repair alterations (dMMR), and tumor mutational
burden (TMB) in tumors have only marginally improved response
rates in some cancers, 6,7 and do not fully reflect the complexity
of a patient’s functional immunity.
Recently, the characterization of the tumor microenvironment
(TME), including analyses of tumor-infiltrating T cells, functional
genomic signatures from RNA expression, and the distribution
of inflammatory and immunosuppressive cells within different
tissue microdomains, have improved the positive predictive
value for ICB response. 8–10 While direct characterization of im-
mune responses in tumor tissues is clinically useful, limitations
to tissue-only approaches remain, including tumor heterogene-
ity, sampling bias, sample acquisition, and longitudinal moni-
toring. Additionally, these methods fail to assess a patient’s sys-
temic immune status, which is intricately linked to tumor
development, prognosis, and treatment response. 11,12
Growing evidence suggests that analysis of peripheral blood
leukocytes can inform immunotherapy selection in patients
with solid tumors. 13 Findings from a pan-cancer study have
shown that high levels of naive B cells in peripheral blood asso-
ciate with improved survival after ICB treatment. 14 High levels of
dendritic cells correlate with favorable responses to ICB in pa-
tients with non-small cell lung cancer (NSCLC) and pancreatic
ductal adenocarcinoma (PDAC). 15,16 NSCLC patients respond-
ing to anti-PD-1 treatment exhibit proliferation of PD-1 + CD8 +
T cells in the peripheral blood after four weeks of treatment, 17
while patients with dysfunctional CD4 + T cells in the periphery
fail to respond to PD-1 pathway inhibition. 18 As such, this
emerging consensus suggests that effective ICB treatment re-
quires the early activation of tumor-specific T cells in the periph-
ery. Ideally, these T cells then differentiate into exhaustion-resis-
tant subtypes competent to infiltrate into the TME to perform
their antitumor function. 19
Currently, comprehensive analysis of systemic immunity isnot
routine when evaluating patients with cancer. Moreover, there
are no consensus methods for profiling a patient’s immune sys-
tem. Most approaches that focus on individual cell populations
are subject to technical and natural variation, often leading to
conflicting results in similar cohorts. 20 On the other hand, unbi-
ased yet resource-intensive approaches like single-cell RNA
sequencing (RNA-seq) pose significant challenges in sample/
data handling and bioinformatics analysis because of their low
throughput, high coefficients of variation, and considerable
cost per sample. 21 This technique, while optimal for hypothesis
generation and discovery in certain settings, is currently imprac-
tical for prospective validation and eventual clinical deployment.
Recently, systems immunology has emerged to address crit-
ical gaps in the study of human immunology by applying multi-
dimensional machine-learning (ML) techniques to complex
clinicaldatasets. 22 Importantly,theseapproacheshaveusedpe-
ripheral blood immunophenotyping data to develop predictive
models for patient responses to different immunological stimuli,
including vaccination. 23 However, the translation of systems
immunology to a wider breadth of clinical questions, including
the evaluation ofimmunotherapy responses in patients withcan-
cer, have been bottlenecked by a lack of standardized ap-
proaches that can be deployed to support large biomarker vali-
dation trials.
Overall, the aim of this study is to understand if a core group of
immune response modules can be identified in different patient
populations, quantified with a standardized platform and flexible
analytical framework, and utilized to stratify patients with
different advanced cancers into therapy-specific response
groups. To accomplish these aims, we established a clinical im-
munoprofiling assay by pairing multiparameter flow cytometry
with an automated high-throughput cytometry analysis platform.
This platform was then used to evaluate immunological variation
in cancer patients and identify associations between this varia-
tion and clinically significant responses to different cancer treat-
ments, including immunotherapy.

## Results

### Cell-typing analysis of peripheral blood using flow cytometry to develop a robust clinical immunoprofiling platform

A comprehensive immunoprofiling assay was developed using
conventional flow cytometry of red blood cell (RBC)-depleted
peripheralbloodsamplestoevaluatethesystemicimmunechar-
acteristics of cancer patients. An end-to-end process was es-
tablished with integrated wet- and dry-lab systems for sample
processing, data acquisition, population identification, markup,
and quantification, all supported by multiple layers of specimen
and data quality control (Figure 1A).
Ten overlapping antibody panels were designed (nine cell
type-specific panels and one general lineage-connecting back-
bonepanel,Figure1B;TableS1)toensurebroadcoverageofim-
mune cell subpopulations across different lineages. Each cell
type-specific panel consisted of well-characterized cell-surface
marker combinations for the following major immune cell popu-
lations: natural killer (NK) cells, dendritic cells, monocytes, CD4 +
T cells, CD8 + T cells, non-conventional T cells, and B cells (Fig-
ure 1B). Multicolor flow cytometry was performed on isolated
white blood cells (WBCs) from the peripheral blood, and these
antibody panels were utilized to quantitate all CD45 + cells in
the samples (Figures 1A and 1B; Table S2). We manually com-
bined and aligned the flow cytometry data using our antibody
panels for exhaustive subpopulation cell typing within the major
cell populations (Figures S1A–S1I; Table S2). Together, 650 cell
types and activation states were identified based on theirmarker
expression profiles (Figure 1B; Table S2).
The manualcell-typing analysisthusdefined anextensive cell-
type hierarchy that was used to establish an automated cytom-
etry analysis platform. Specifically, it was used to train ML
gradientboostingevent-typemodelstoautomaticallyandrepro-
duciblyidentify immunecellsubsetsfromeachpanel(Figures1A
and S2A; Table S3). These cell-typing models accurately de-
tected various immune cell populations and activation states
from peripheral blood by corroborating the manual supervised
gatinganalysisinvalidationtests(F1-scores:0.74–0.95,P4-met-
rics: 0.84–0.97, for the 10 panels, Table S3; Figure S2B). This
platform was then used to analyze blood samples from healthy
donors and cancer patients to determine if differences in im-
mune cell composition between these two groups could reveal
additional findings of diagnostic or prognostic significance.
Preliminary comparisons were performed between healthy
donors and cancer patients with the blood samples from our
training set. These comparisons revealed striking differences in
the relative frequencies of monocytes as well as naive, central
memory, and terminally differentiated CD4 + and CD8 + T cells
(Figure 1C). Consistent with published reports, 24–27 this prelimi-
nary analysis supported further exploration of differences in im-
mune profiles from healthy donors and patients with advanced
cancer.Thus,weassembledalargecohorttoexamineifimmune
cell heterogeneity in patients with cancer differed significantly
from healthy donors.

### Stratifying healthy donors and cancer patients using differences in immune cell composition between these two groups

Peripheral blood from 408 healthy donors and 442 cancer pa-
tients, aged 16 to 98 years (total n = 850, internal cohort), were
collected. This cohort comprised 84 different solid tumor diag-
noses within seven major therapy groups (Figure 2A; Table S4).
Complete blood count (CBC) revealed significant differences in
the absolute numbers of RBCs, platelets, neutrophils, and lym-
phocytes between healthy donors and cancer patients, while
the absolute number of monocytes were similar, in agreement
with published reports 24,28 (Figure S3A).
This immunoprofiling platform was then used to analyze the
peripheral immune cell distribution from each individual within
thiscohort.Thefrequenciesofupto650celltypesandactivation
states were measured for each sample, and Uniform Manifold
Approximation and Projection (UMAP) was used to plot these
features in two dimensions. This approach allowed us to eval-
uatetheinfluence ofdifferentvariableson immunecell heteroge-
neity in this cohort, such as the presence or absence of disease,
patient age, solid tumor type, and administered therapies (Fig-
ure 2B). Patients with similar diagnoses did not form distinguish-
able clusters, neither did patients with similar therapy lines.
Conversely, healthy donors and cancer patients formed sepa-
rate clusters. Patients in different age groups tended to cluster
as well, consistent with healthy donors being generally younger
than patients with solid tumors (Figure 2B). Our findings suggest
that differences in immune profiles between individuals in this
cohortcouldbeexplainedbythepresenceorabsenceofcancer,
regardless of tumor or treatment types.
To explore the features contributing to the variance in this
cohort, we used the Max-Relevance and Min-Redundancy
(MRMR) algorithm with stepwise leave-one-out cross-validation
to identify cell populations that were the most significantly
differentbetweenhealthydonorsandcancerpatients(Figure2C;
Table S5). Interestingly, CX 3 CR1 neg CD8 + TEMRA and mono-
cytes were significantly overrepresented in patients with cancer,
whereas populations of naive CD4 + and CD8 + T cells as well as
naive and memory B cells were overrepresented in healthy do-
nors (Figures 2C and 2D; Table S5). These observations suggest
that different cell types are enriched in patients with cancer,
while othersare enrichedin healthyindividuals. While some pop-
ulations differed between old and young healthy donors, these
differences were much starker between healthy donors and can-
cer patients (Figure 2C), suggesting disease stateis a more
prominent driver of variation in this cohort than patient age. We
then selected 20 cell types and used their frequencies to train
a TabPFN-based 29 classifier model on a set of 503 samples
from our internal cohort (Figure S3B). UMAPs were generated
from these selected features to show the label assignments pre-
dicted by our classifier model to correspond to the true labels
(Figure 2E).
Thisclassifier was assessed usingleave-one-out crossvalida-
tion on the training dataset and shown to perform well in classi-
fying healthy donors and cancer patients (area under the curve
for receiver operating characteristics [ROC-AUC] = 0.91). Note-
worthily, our binary classifier model trained on the features of the
20 previously selected cell populations outperformed a more
basic model trained on populations that could be identified
from a commonly used clinical cytometry panel (BD Multitest
6-color TBNK kit) combined with major populations from stan-
dard CBC: basophils, eosinophils, neutrophils, monocytes, NK
cells, natural killer T (NKT) cells, B cells, CD4 + T cells, and
CD8 + T cells (ROC-AUC = 0.81, Figure 2F, left). Similarly, this
classifier performed better in selecting healthy donors and can-
cer patients on a validation subset of 347 patient samples from
the internal cohort, compared to the TBNK/CBC panel (ROC-
AUC = 0.84 and 0.77, respectively, Figure 2F, right). Overall,
these results demonstrate that immune profiles can be used to
stratify patients with distinct clinical characteristics with high
specificity.
### Classification of immune cell composition in peripheral blood into five distinct immunotypes

Having established differences between healthy donors and
cancer patients, we aimed to understand if this analysis could
be expanded to identify immune profiles with putative functional
significance. Specifically, unsupervised spectral clustering
was applied to the normalized frequencies of 34 cell types on
samplesfromourinternalcohortobtainedbyflowcytometry(Ta-
ble S6). Initially, 30 cell types congruent with populations that
could be identified by cellular deconvolution of bulk RNA-seq
with Kassandra were selected. 9 To that, four cell populations
consistently identified as immunotherapy response biomarkers
were incorporated: TIGIT + PD-1 + CD8 + T cells, 30 Vd2 + gd-T
cells, 31 CD39 + regulatory T cells (Tregs), 32 and HLA-DR low
monocytes. 15,33–38
Five immunotypes (G1–G5) were identified using this
approach, with the separation into five clusters being associated
with the highest median number of significantly different cell
populations between clusters (Table S6, STAR methods). G1 ex-
hibited high frequencies of naive CD4 + T cells, naive CD8 +
T cells, and naive B cells. G2 showed greater percentages of
differentiated CD4 + central and transitional memory T cells, as
well as CD39 + Tregs. G3 showed increased frequencies of
mature NK cells as well as CD8 + transitional memory and PD-
1 + TIGIT + CD8 + T cells. G4 was enriched with NKT cells as well
as terminally differentiated effector memory CD45RA + (TEMRA)
and CD45RA ? (TEM) of both CD4 + and CD8 + T cells. Finally,
G5 was enriched with classical monocytes, HLA-DR low mono-
cytes, and neutrophils, and contained smaller frequencies of
lymphocytes (Figure 3A). Consistent with our UMAP analysis of
ourinternalcohort(Figure2B),thepresenceorabsenceofacan-
cer diagnosis (healthy or cancer) and patient age were unevenly
distributed among the immunotypes (Figures 3A and 3B). Impor-
tantly, immunotypes G4 and G5, enriched with terminally differ-
entiated CD8 + T cells and classical monocytes, respectively,
contained very few healthy donors. Conversely, immunotype
G1 with the highest percentage of naive T and B lymphocytes
contained the largest proportion of healthy donors (Figure 3A).
Themostfrequentlyrepresenteddiagnosesinourinternalcohort
contained similar ranges of immunotypes, suggesting that can-
cer type was not a major driver of immunotype distribution
(Figure 3C).
Bulk mRNA-seq libraries from 797 samples analyzed by flow
cytometry from our internal cohort were prepared and
sequenced (Table S4). Cellular deconvolution of bulk RNA-seq
by Kassandra 9 was then used to match cell populations with
those identified by flow cytometry. Cell population frequencies
derived from RNA-seq and flow cytometry were concordant
(Figures3D andS4), thusconfirmingour flow cytometry findings.
These RNA-seq data were then used to perform differential
gene expression analysis on the immunotypes of our internal
cohort.Here,alargenumberofgenesuniquelyup-ordownregu-
lated for each immunotype compared to the sum of all other im-
munotypes were identified (Figure S5A). Building upon this anal-
ysis, we selected the 200 most differentially expressed genes
from each cluster and performed a gene set enrichment analysis
(GSEA) using curated functional gene signatures for immunolog-
ically relevant pathways from MsigDB. 39 G1 and G2 were shown
to be enriched in signatures for transcriptional regulation
involving TCF, LEF, and CTNNB1 as well as TCR- and WNT/
beta catenin-mediated signaling. G4 was found to be enriched
in genes associated with cytotoxic effector T cell responses,
and G5 to be enriched in genes involved in signaling pathways
associated with innate immune sensing and myeloid cells
(Figures 3E and S5B; Table S6).
Of note, individual transcripts of cytokine and chemokine
signaling-related genes displayed distinct expression patterns
among our defined immunotypes. For instance, FLT3LG and
CCR7, which are expressed by naive and central memory
CD4 + and CD8 + T cells, were the most highly expressed in G1.
Their expression decreased progressively through to G4 and
were poor in G5. G4, enriched with terminally differentiated
CD4 + and CD8 + T cells, showed the highest levels of CCL4
and TGFBR3. CXCL16 and IL1R1 transcript levels were greatest
in G5, consistent with their expression by monocytes and neu-
trophils (Figure 3F). Collectively, these results demonstrate the
presence of immunotype-specific gene expression patterns
even at the level of individual transcripts.
### Analysis of T cell receptor repertoires and transcriptional signatures of T cell memory to show immunotype association with the characteristics of immunotherapy responsiveness

Adaptive immunity generally and therefore patient responses to
ICB are largely dependent on the clonal expansion and differen-
tiation of tumor antigen-specific T cells. 40 To better understand
the adaptive response potential of our different immunotypes,
we evaluated T cell repertoire composition using bulk RNA-seq
data from our internal cohort, 41 as T cell receptor (TCR) reper-
toire clonality and diversity have been characterized as bio-
markers for ICB response. 42 Our analysis showed the coverage
of CDR3 sequences from TCRb-chains to be consistent across
the cohort and to reflect the overall frequency of T cells in each
sample (Figure 4A, top). Dominant clones occupying more than
10% of total CDR3 in each patient, while infrequent in the cohort
overall, were enriched in the G4-chronic immunotype (Figure 4A,
bottom; Figures S6A and S6B).
The under- or over-representation of certain human leukocyte
antigens (HLAs) between immunotypes could potentially explain
differences in TCR repertoire composition. Therefore, the allele
distributions of HLA-A, -B, and -C in our internal cohort were
analyzed (Figure 4B, HLA-B). HLA distribution among the
different immunotypes was heterogeneous (Figure 4B). Interest-
ingly, of all the HLA types measured in this cohort, only the fre-
quency of patients with the HLA-B07:02 allele were significantly
lower in the G4-chronic immunotype compared to all other
groups (Figure 4B). This analysis demonstrates that HLA skew-
ing is not likely to have caused the differences in TCR repertoire
distribution among different immunotypes.
TCRb clonality index of individuals in the G4-chronic immuno-
type was approximately three times that of individuals in the
other immunotypes (Figure 4C, left). Additionally, there was no
association between TCRb clonality and the number of patients
with any specific HLA-B allele (Figure S6A). Conversely, immu-
notypes G1-naive, G2-primed, and G3-progressive had signifi-
cantly higher TCRb diversity (as indicated by Chao1) than immu-
notypes G4-chronic and G5-suppressive, decreasing from G1 to
G3 (Figure 4C, right). This is consistent with the observed frequencies of naive, central, and transitional memory T cells in
theseimmunotypes.Similardifferenceswere presentamongim-
munotypes in TCRa clonality and diversity (Figures S6C and
S6D). Additional analysis of B cell receptor (BCR) repertoire di-
versity between immunotypes revealed trends similar to those
forTCR,withtheG1-naive immunotypehavingthehighest diver-
sity index for BCR heavy and light chains that were significantly
greater than that for immunotypes G3-progressive, G4-chronic,
andG5-suppressive(FigureS6E).Theseimmunotype-based dif-
ferences in TCR repertoires suggest a putative connection to
transcriptional programs that control T cell differentiation and
clonal expansion.
To further test this, we expanded our GSEA analysis to eval-
uate the immunotypes using annotated gene signatures
centered on gene expression patterns connected with T cell dif-
ferentiation state, repertoire diversity, and PD-1 expression by
Tcells. 43,44 First, anenrichment pattern for a general Tcell differ-
entiation signature (GSE14699, Figure 4D, right) was observed,
containing genes differentially expressed between naive and
activated CD8 + T cells that resembled the immunotype distribu-
tion pattern seen for TCRb repertoire diversity (Figure 4C, right).
Inaddition,individualgeneexpressionlevelsoftranscriptionfac-
tors TCF-7, LEF1, and ID3 that are prominently expressed by
naive and self-renewing central memory T cells and control the
development of T cell memory were the highest in immunotypes
G1-naive and G2-primed (Figure 4E, top), consistent with the
T cell differentiation signature scores (Figure 4D, right). The
G4-chronic immunotype had the highest enrichment score for
the PD-1 high CD8 + T cell signature (GSE26495, Figure 4D, left),
which was concordant with our analysis on TCRb clonality (Fig-
ure 4C, left) and the frequency of terminally differentiated T cells
in this immunotype. Similarly, TBX21, EOMES, and TOX, encod-
ing transcription factors that are critical regulators of effector
Tcell differentiation and exhaustion, showed the highest expres-
sion in the G4-chronic immunotype (Figure 4E, bottom). To
examine the potential association between immunotype and
immunotherapy response, we then analyzed 70 cancer patients
with different diagnoses from our internal cohort who were on-
treatment with a PD-1 pathway inhibitor. While no differences
in the expression of PDCD1 (PD-1) or CD274 (PD-L1) were
seen between immunotypes (Figure 4F), G1-naive, G2-primed,
and G4-chronic showed an enrichment in gene signatures asso-
ciated with PD-1 signaling and response to PD-1 inhibition (Fig-
ure 4G). Taken together, these results further support the asso-
ciation of immunotypes G1–G5 with immunotherapy treatment
responses.
### Analysis of open-source peripheral blood RNA-seq data to reveal disease associations with immunotype distribution


Having shown that these immunotype classifications are consis-
tent with known states of immunological responsiveness, we
examined if this approach could be expanded to other datasets.
Initially, we attempted to assemble a cohort of healthy donors
and cancer patients similar to our internal cohort. Here, periph-
eral blood transcriptomes from 17,800 individuals from open-
source GEO and ArrayExpress databases 45 were collected
(Table S7). However, these datasets contained very few cancer
patients (n = 160), with diagnoses and therapies that did not
overlap with our internal cohort. As an alternative, samples
from healthy donors and patients with 90 different diagnoses
of immunological significance, including infectious, inflamma-
tory, and autoimmune diseases, were used to evaluate the asso-
ciation between our immunotype framework and responses to
well-characterized immunological challenges. First, the fre-
quencies of immune cell populations were derived from these
bulk transcriptomes using Kassandra. De novo unsupervised
spectral clustering was then applied to understand the distribu-
tion of these immune subsets in this larger, more diverse dataset
(Table S7). Encouragingly, we found these 17,800 transcrip-
tomes to form five clusters with cell type distributions strikingly
similar to those in our internal cohort (Figure 5A), thus allowing
us to independently verify the existence of these immunotype
clusters in open-source bulk RNA-seq datasets. Additionally,
3D principal component analysis (PCA) projection of these sam-
ples revealed a similar continuum of immunotypes to our internal
cohort, and a direct comparison of healthy donors from both da-
tasetsshowednosignificant differences inimmunotype distribu-
tion (Figures 5B, S7A, and S7B).
Next, each dataset was subgrouped based on disease patho-
genesis (Figure 5C; Table S7). For instance, samples from pa-
tients with persistent Mycobacterium tuberculosis or Leishmania
spp. infections were assigned to the ‘‘phagosomal pathogens’’
group, and samples from patients with influenza or coronavirus
to the ‘‘respiratory viruses’’ group. Consistent with the analysis
of our internal cohort (Figure 3A), healthy donors were most frequently assigned to the G1-naive and G2-primed immuno-
types (Figure 5C). Compared to healthy donors, only patients
from the ‘‘autoimmune diseases’’ group that contained a large
number of pediatric cases were significantly clustered in G1-
naive. While the G2-primed group contained the largest number
of samples across the cohort overall, this immunotype was only
significantly enriched among patients with phagosomal patho-
gens compared to healthy donors. The G3-progressive imm-
unotype was significantly enriched among patients with viral
infections (respiratory, enteric, and HIV) and phagosomal patho-
gens. Patients with chronic viral and extracellular bacterial infec-
tions were also assigned more frequently to the G4-chronic im-
munotype compared with healthy donors; G4-chronic was also
the most common immunotype classification for patients with
HIV. Interestingly, all disease groups contained significantly
more patients with the G5-suppressive immunotype, particularly
conditions associated with high levels of systemic inflammation
such as bacterial sepsis where nearly 80% of the patients in this
group were assigned to this immunotype (Figure 5C). Our anal-
ysis showed that beyond the observations from our internal
cohortwithhealthydonorsandcancerpatients,thesefiveimmu-
notypes could be identified in a diverse external dataset and
independently confirmed with cellular deconvolution of bulk
RNA-seq only, further supporting the validity and broad applica-
bility of our framework.
### Development of immunotype signature scoring for the identification of cancer therapy response correlatives

Consideringthatfrequenciesofdifferentimmunecellpopulations
in the peripheral blood of patients are normally distributed, clus-
tering of patients using these data resulted in significant overlap
between clusters. Consequently, classifying patients with inter-
mediate or transitional immunotype characteristics was chal-
lenging, as visualized in a UMAP projection of our internal cohort
(Figure5D),suggestingthattheseimmunotypesrepresentacon-
tinuum rather than discontinuous groups with clean separation
between them. This is more precisely visualized with a pseudo-
time projection based on flow cytometry data from our internal
cohort 46–48 (Figure5E,left).PatientswithimmunotypesG1-naive
and G2-primed clustered most frequently at the origin of the plot
andbifurcatedintotwobranchesterminatinginnodeswhereG4-
chronic and G5-suppressive were the most abundant. G3-pro-
gressive was located predominantly between clusters G1-naive
and G5-suppressive, and to a lesser extent between clusters
G2-primed and G4-chronic (Figure 5E), indicating potential tran-
sitional relationships between them.To more accurately quantify
the dynamic nature of these immunotypes for therapy response
evaluation, we used five different immunotype-specific linear
regression models to transform each immunotype into a contin-
uous score (Table S8). Importantly, this can be derived from
individual patient samples independently from their putative im-
munotype assignment. These immunotype signature scores
(ISSs) reflect the degree of similarity of each patient sample to
the samplewiththe mostideal,orhighest individual immunotype
score within the cohort, between 0 and 10.
ISSs were then plotted onto five different pseudotime plots
to illustrate the distribution of these scores throughout the in-
ternal cohort (Figure 5E, right). Essentially, these ISSs serve as
a metric that quantifies the magnitude of a particular immuno-
type of an individual patient within a cohort; the higher the
score, the closer that sample is to the ideal characteristics
of that immunotype in that cohort. The maximum immunotype
signature score (MIS) compares all five ISS values from a pa-
tient’s blood sample, and subsequently uses the largest ISS
value to assign that patient to an immunotype. Immunotype
assignment using the patients’ MISs showed high concor-
dance with the initial spectral clustering-based immunotype
assignment of our internal cohort (Figure 5F; Table S8). There-
fore, the quantification of ISSs (Table S8) and determination of
patients’ MISs are suitable analytical tools for evaluating dy-
namic, systemic immune responses to treatment and can be
applied either individually or in a complimentary fashion even
across small cohorts with adequate statistical power for
correlative assessment.
###  Immunotype signature scores correlated with patient responses to cancer treatment

Understanding the potential utility of our immunotype framework
as a tool to assess patient outcomes requires cohorts with ho-
mogeneous diagnoses and treatments, detailed clinical data,
and peripheral blood analysis where the frequencies of different
immune cells could be quantified. Our internal cohort contained
very few patients (n = 10) with available clinical response data
and was heterogeneous with respect to diagnosis and treat-
ment.Therefore, public datasetswithspecific treatments and di-
agnoses were used to first explore the utility of our immunotype
signature framework as a prognostic tool to stratify cancer pa-
tients by response.
Chemotherapy has profound effects on the composition of the
immune system. 3 As a proof of concept, we examined if these
changes could be reflected in alterations in immunotype signa-
tures identified in a cohort of breast carcinoma patients treated
with neoadjuvant chemotherapy (NAC) prior to surgical resec-
tion 49 (GSE201085, Figure 6A). Cellular deconvolution with Kas-
sandra of bulk RNA-seq of patients’ peripheral blood mononu-
clear cells (PBMCs) collected 30 days after treatment initiation
was used to calculate ISSs (Table S8), and patients were strati-
fied into immunotypes using MIS. Interestingly, patients with a
pathological complete response (pCR) to NAC were more
frequently assigned to immunotype G5 than those with residual
disease (RD) (Figure 6B). Patients with pCR had a significantly
higher G5-suppressive signature score (p = 0.01) and a signifi-
cantly lower score for the G1-naive signature (p = 0.03) than pa-
tients with RD (Figure 6C). Binary response stratification ROC-
AUCs for G5-suppressive and G1-naive were 0.79 and 0.25,
respectively, suggesting that our immunotype signatures are
sensitive to systemic changes associated with response. G3-
progressive and G4-chronic trended in the same direction as
G5-suppressive whileG2-primedtrendedtowardG1-naive,indi-
cating a broader shift in immune composition prognostic of
effective responses to chemotherapy (Figure 6D).
Next,acohortofpatientswithPDACfromarandomizedphase
II clinical trial (PRINCE 50 ) was evaluated. These patients were
treated with a combination of chemotherapy and anti-PD-1 (ni-
volumab; A1) or anti-CD40L (sotigalimab; B2) immunotherapy,
or all three (C2). PBMCs collected 30 days after treatment
(C2D1) were analyzed with high-parameter CyTOF (Figure 6E)
to further demonstrate the utility of ISSs in stratifying cancer pa-
tients with different diagnoses and treatment lines. Cell popula-
tions derived from CyTOF data were used to calculate ISS. Each
patient was assigned to an immunotype group using MIS, and
then the combined cohort was evaluated for progression-free
and overall survival (PFS and OS). While no significant associa-
tion between immunotype and PFS was observed (Figure 6F,
left), patients assigned to the G3-progressive immunotype had
significantlylongerOS(p=0.004)thanpatientsassignedtoother
immunotypes (Figure 6F, right). Patients were then segregated
by the median survival time for this trial into short (<347 days)
andlongOS(>347days).AmongpatientswithlongOS,agreater
proportionofthemhadaG3-progressiveMIScomparedwiththe
MIS for the remaining immunotypes (p = 0.04, Figure 6G). These
patients also had significantly higher G3-progressive ISSs over-
all (p = 0.0009, Figure 6H, left). A binary classifier using G3-pro-
gressive ISS was able to differentiate between patients with long
OS and short OS in this cohort with high specificity (ROC-AUC =
0.74, Figure 6I, left).
Todetermineifthissignaturecouldbetiedtoaparticulartreat-
ment arm, we analyzed the different therapy groups by OS. The
Chemo/Nivo A1 group had significantly higher G3-progressive
scores between patients with short and long OS (p = 0.0006)
and an ROC-AUC of 0.94. Patients with long OS also had signif-
icantly lower G2-primed ISSs with an ROC-AUC of 0.19
(Figures 6H and 6I right), indicative of a broader systemic shift
associated with response. This effect was not observed in either
the Chemo/Sotiga B2 or Chemo/Nivo/Sotiga C2 groups (Figures
6H and 6I middle). Our findings are consistent with those of Pa-
dron et al., 50 where only patients from the Chemo/Nivo A1 group
met the primary survival endpoints of the PRINCE trial.
Collectively, this analysis supports our previous observations
in NAC-treated breast cancer that ISSs have prognostic value
inpost-treatmentresponsemonitoringinanindependentcohort.
### Application of immunotype signatures forthe evaluation of PBMC samples from HNSCC patients treated with frontline immunotherapy

Having shown our immunotype signature framework to differen-
tiate responses between cancer patients with different diagno-
ses treated with chemotherapy and combination chemo/immu-
notherapy, we evaluated the utility of this platform in stratifying
cancer patients treated with frontline immunotherapy by objec-
tive responses from PBMCs collected and analyzed at pre-
and on-treatment time points. Two cohorts of patients with
advanced head and neck squamous cell carcinoma (HNSCC)
treated with checkpoint inhibitors targeting the PD-1 pathway
were selected. Both trials included a second arm where an addi-
tional drug was combined with the checkpoint inhibitor. In the
first trial, all 32 HNSCC patients (HNSCC-Durva cohort) were
treated with PD-L1 inhibitor durvalumab; among these, 25
were also treated with anti-hyperglycemic agent metformin
(25/32) (Table S9). Based on an overall objective pathological
assessment of primary tumors and involved lymph nodes,
56.25% (18/32) of patients had responded to treatment. There
was no statistical difference in response rates between patients
treated with durvalumab plus metformin and durvalumab alone
(Figure 7A), suggesting that therapy response in this trial was
driven primarily by durvalumab. Pre- and post-treatment
PBMCs from this trial were processed by bulk RNA-seq and
cell percentages were identified using Kassandra. Signatures
for immunotypes G1–G5 were calculated and patients were
then classified into different immunotype groups. While there
was no significant skewing of immunotype distribution based
on response, more responders tended to be assigned the G4-
chronic immunotype than non-responders (Figure 7B). A com-
parison of ISSs across the entire cohort showed significantly
higher G3-progressive scores for responders at the on-treat-
ment time point (p = 0.04), with a trend for increased G4-chronic
ISSs and response classification ROC-AUCs of 0.74 and 0.68,
respectively (Figure 7C).
Next, we explored if patient responses could be stratified
based on the immunotype signature analysis of baseline sam-
ples collected before treatment. While immunotype classifica-
tion with MIS was not statistically significantly different between
responders and non-responders (Figure 7D), G4-chronic ISSs
were significantly greater in responders (p = 0.03). Although
not statistically significant, G3-progressive ISSs were also
greater in responders, with ROC-AUCs of 0.73 and 0.66, respec-
tively (Figure 7E). This corresponded with multiple CD8 + T cell
populations that could be measured by Kassandra deconvolu-
tion being differentially represented among responders (Fig-
ure 7F). We then benchmarked the positive predictive value of
our G4-chronic signature to the measurement of PD-L1 expres-
sioninthetumorbyRNA-seq 51 frompatientsinthiscohortwhere
next-generation sequencing (NGS) data were available. Our
analysis showed the G4-chronic signature from this cohort to
considerably outperform tissue PD-L1 expression in stratifying
response at baseline (Figure 7G).

Our comprehensive immunoprofiling platform was then tested
with a clinical cohort of 35 HNSCC patients (HNSCC-Nivo
cohort) treated with first-line nivolumab alone or nivolumab in
combination with indoleamine 2,3-dioxygenase-1 inhibitor
BMS-986205 (IDOi) (Figure 7H, Tables S8, and S9). Similar to
the HNSCC-Durva cohort, patients in different arms had similar
response rates (Figure 7H). Cell population frequencies were ob-
tained from flow cytometry and RNA-seq analysis of cryopre-
served PBMCs collected at both on- and pre-treatment time
points, and patients were classified into immunotype groups
with corresponding MIS. Interestingly, responders were as-
signed most frequently to the G2-primed immunotype (p =
0.004) (Figure 7I). G2-primed scores were significantly higher in
responders and could prognostically discriminate responders
from non-responders with an accuracy of 76% (Figure 7J). Anal-
ysis of pre-treatment samples revealed a similar pattern of G2-
primed assignment, with all patients assigned to G2-primed re-
sponding to nivolumab (Figure 7K). Pre-treatment G2-primed
scores were significantly higher in responders (p = 0.02) with
an ROC-AUC of 0.74 (Figure 7L). In this context, the G2-primed
signaturedemonstratedpotential utility asboth a prognostic and
predictive biomarker for the treatment of advanced HNSCC with
nivolumab. This was further supported by differential population
analysis of baseline PBMCs showing ten significantly increased
cell populations in the peripheral blood of responders, nine of
which belong to the CD4 + T cell lineage (Figure 7M). Additionally,
the accuracy of G2-primed scoresin response stratification from
thiscohortwasgreaterthanthatofmultipleestablishedandpub-
lished biomarkers for HNSCC patients treated with anti-PD-1
ICB, including TMB, tumor PD-L1 expression by RNA-seq, and
CD4 + T cells and PD-1 + CD8 + T cells from the peripheral
blood 52,53 (Figure7N).Interestingly,approximatelyhalfofthepa-
tientsinboth HNSCCcohortshadthe sameMISatboth pre-and
on-treatment time points, while the rest of patients transitioned
between adjacent immunotypes during ICB therapy (Figures
S8A and S8B). Of note, 6/8 responder patients with G2-primed
MIS in the HNSCC-Nivo remained in G2-primed throughout
treatment, while the remaining 2 patients transitioned to the
adjacent G3-progressive MIS. Of the 11 patients that transi-
tioned to G4-chronic or G5-suppressive MIS, 9 did not respond
to PD-1 (Figure S8A). Conversely, in the HNSCC-Durva cohort,
7/8 patients that transitioned to G4-chronic or G5-suppressive
MIS responded to anti-PD-L1 (Figure S8B). These observations
are consistent with the association of different favorable sys-
temic immune responses to specific immunotherapy drugs.
### Immunotype signatures improved response stratification in HNSCC based on therapy type and human papilloma virus infection status

Human papillomavirus (HPV) is a major etiologic agent of
HNSCC, and patient responses to PD-1 and PD-L1 blockade
are associated with HPV status. 54 Having shown the potential
of ISSs to stratify HNSCC patients prior to treatment initiation
with durvalumab or nivolumab, we then explored the utility of im-
munotype stratification in HPV+ and HPV? HNSCC patients
from the two cohorts described in Figure 7. Segregation of pa-
tientsfromtheHNSCC-Nivo cohortinto HPV+andHPV?groups
revealed no significant differences among the G2-primed signa-
ture scores in HPV+ responders to nivolumab (Figure 8A). Inter-
estingly, for anti-PD-1-treated HPV? patients in this cohort, the
G2-primed scores were significantly higher (p = 0.01) in re-
sponders, with the G2-primed signature ROC-AUC at 0.86 in
HPV? patients, versus 0.58 in HPV+ patients and 0.74 in the
overall cohort (Figure 7L, 8B). HPV+ and HPV? patients from
the HNSCC-Durva group were then analyzed separately. While
not statistically significant, HPV+ responding patients had higher G4-chronic signature scores than non-responders with an ROC-
AUC of 0.75 (Figure 8C). This trend was also seen in HPV? pa-
tients with an ROC-AUC of 0.75 (Figure 8D), similar to our anal-
ysis of the G4-chronic immunotype in the overall cohort which
was statistically significant with an ROC-AUC of 0.73 (p = 0.04)
(Figure 7E). On the other hand, the G3-progressive signature
scores for HPV? patients in this cohort were significantly higher
in responders (p = 0.03) with an ROC-AUC of 0.89 versus 0.58 in
HPV+ patients (Figures 8C and 8D). Taken together, our findings
indicate that immunotype signatures G2-primed and G3-pro-
gressive have potential predictive utility for HPV? HNSCC pa-
tients treated with nivolumab and durvalumab, respectively,
while the immunotype signature G4-chronic can potentially
stratify responders to anti-PD-L1 therapy independent of HPV
status.

图例部分

Figure 1. Development of the immunoprofiling pipeline
(A) Workflow of immunoprofiling pipeline development: white blood cells (WBCs) were isolated from peripheral blood samples collected from healthy donors and
cancer patients. A hematology analyzer was used to measure complete blood count. WBCs were stained with custom antibody panels in 96-well plates. WBCs
wereprocessedbymultiparameterflowcytometry.Manuallylabeledflowcytometrydatawereusedtotrainmachinelearningmodelstoautomatically identifycell
populations. Finally, the healthy/cancer and immunotype classifications were implemented.
(B) Schematic heatmap of cytometry panels showing a portion of the markers used (x axis) and examples of identified populations (y axis). The
heatmap shows normalized signal intensities of cell-surface markers that define specific cell types, generated by combining readouts from the different
antibody panels (e.g., general, NK cells, and dendritic cells). Representative tSNEs of immune cell families identified with this strategy are shown on
the right.
(C) Differences in immune status, based on cell populations, between a representative healthy donor and a cancer patient, visualized with polar plots. Each dot
represents 0.5% of all fractions of peripheral blood mononuclear cells (PBMCs) for a total of 200 fractions shown. See also Figures S1, S2, and Tables S1, S2,
and S3.

Figure 2. Training and performance of our healthy/cancer classifier
(A) Cohort description with disease breakdown and clinical annotation. The cohort was first categorized into different clinical groups, and then split into training
and validation subsets for the construction and evaluation of the healthy/cancer classifier, respectively.
(B)VisualizationofUMAPanalysisofrawcytometrydata(allcellpopulations,beforeselection).Cohortdistributionisbasedonabsenceorpresenceofcancerand
age, diagnosis, or treatment groups, respectively.
(C) Volcano plot showing the 20 differentially represented cell populations between healthy donors and cancer patients that were selected with the MRMR al-
gorithm for constructing the binary healthy/cancer classifier (Mann-Whitney U test with Bonferroni correction, Table S5). Two series of bubble plots show log fold
changes (effect size) and statistical significance of the differences for those cell populations between different age groups (cutoff = 45 years for ‘‘old’’ and
‘‘young’’), and between healthy donors and cancer patients, respectively.
(D) Distribution of naive CD4 + T cell, unswitched memory B cell, CX 3 CR1 neg CD8 + TEMRA, and monocyte populations between healthy donors and cancer
patients. Mann-Whitney U test adjusted with Bonferroni correction method: ****p < 0.0001. Boxplots indicate the median and the 25th and 75th percentiles, and
whiskers extend to the lowest and highest value within 1.53 interquartile range.
(E) UMAP analysis on selected cell populations to compare true and predicted labels, showing a probability gradient between patients and healthy individuals.
(F)Our healthy/cancerclassifierwasestablished usingthe20selected cellpopulations’normalized percentagesas features,and comparedtothebasic modelof
the TBNK panel and major cell populations from CBC analysis. The performance on both training (n = 503) and validation sets (n = 347 from the internal cohort) is
shown with the ROC-AUC metric. See also Figure S3, Tables S4, and S5.

Figure 3. Flow cytometry-based clusterization of immunotypes and analytical validation with matched RNA-seq
(A) Unsupervisedspectral clusteringanalysiswasapplied tonormalized flowcytometry percentages torevealfive distinct immunotypesbasedon thedistribution
of selected cell populations. Samples were also categorized based on patient diagnosis (healthy donors or cancer patients).
(B) Histograms showing the age distribution among the immunotypes.
(C) Bar plots showing distribution of the five immunotypes within the seven most prevalent disease groups of solid cancer diagnoses of our internal cohort.
Dashed lines show boundaries between median distributions.
(D) Bubble plots of median cell percentages based on data from flow cytometry and cell deconvolution by Kassandra. Color gradient represents the percentages
of a cell type in the total WBC or PBMC population, based on flow cytometry (top) and RNA-seq deconvolution analysis (bottom). The circle sizes represent the
normalized cell fraction percentages between the cohort.
(E) Heatmap with GSEA scores for RNA-seq data grouped by immunotypes.
(F) Immunotype comparison of individual gene expression levels of cytokine and chemokine signaling-related genes. p values from Dwass-Steel-Critchlow-
Fligner all-pairs comparison test: **p < 0.01, ***p < 0.001. See also Figures S4, S5, Tables S4, and S6.


Figure 4. HLA alleles and TCR repertoire analysis of the internal cohort
(A) TCRb landscape. The TCRb CDR3 coverage is shown, with explicit TCRb fractions.
(B)Distribution of HLA-B alleles for class I HLA genes. Onlyalleleswithfive countsor more are labeled. Each allele is represented withadifferent color. Gray color
represents alleles with lower than 5 counts. Significant difference is noted on the pie chart for the frequency of HLA-B07:02 in chronic-G4 compared to all others:
*p = 0.0452, Fisher’s exact test for count data.
(C) Distribution of TCRb clonality and TCRb Chao1 diversity indices within immunotypes are shown in swarm plots, with each data point representing a sample
from the internal cohort. p values from Games-Howell post-hoc test: **p < 0.01, ***p < 0.001, ****p < 0.0001.
(D) GSE scores on gene signatures (left: GSE26495, right: GSE14699) compared across immunotypes (Dwass-Steel-Critchlow-Fligner all-pairs comparison
test: ***p < 0.001).
(E)Geneexpression levels(inlog 2 TPM)oftranscriptionfactors associated withnaiveandself-renewingmemoryTcells(toprow)andeffectorTcelldifferentiation
and exhaustion (bottom row) (Dwass-Steel-Critchlow-Fligner all-pairs comparison test: ***p < 0.001).
(F) Gene expression levels of PDCD1 and CD274 involved in PD-1 signaling. n = 70 patients on-treatment with ICB alone or in combination, from our internal
cohort. n.s: non-significant (Dwass-Steel-Critchlow-Fligner all-pairs comparison test).
(G) Heatmap showing expression of genes associated with PD-1 blockade and PD-1 signaling signatures among the different immunotypes. Boxplots in C and F
indicatethemedianandthe25thand75thpercentiles,andwhiskersextendtothelowestandhighestvaluewithin1.53interquartilerange.SeealsoFigureS6and
Table S6.

Figure 5. Immunoprofiling of transcriptomes from healthy donors, cancer patients, and patients with other immune conditions in the open-
source cohort
(A) Unsupervised spectral clustering analysis was applied to normalized cell percentages obtained from an open-source collection of 17,800 RNA-seq whole
blood samples processed by Kassandra deconvolution. Only 1,000 randomly selected samples are shown to reduce figure complexity.
(B) A three-dimensional PCA representation of the open-source blood RNA-seq datasets processed by Kassandra deconvolution and then classified in im-
munotypes. Only 5,000 randomly selected samples are shown to reduce figure complexity.
(C) Bar plots showing distribution of the five immunotypes within each disease group (left). The statistical significance of the distribution for each disease group
comparedwithhealthysamplesisshownonthebubbleplot(right).Colorgradientcorrespondstologpvalues(Fisher’sexacttestwithBonferronicorrection).The
circle size is proportional to the fraction value within the disease group.
(D) Immunotype distribution after UMAP analysis of the internal cohort’s cytometry data on selected cell populations used in clusterization (left). Pseudotime
analysis of flow cytometry data from our internal cohort based on the putative developmental trajectories of the different cell populations enriched in each
immunotype (right).
(E) Distribution of signature scores for each immunotype mapped on the pseudotime trajectory in (D).
(F) Sankey-plot depicting the concordance between immunotype assignment by clusterization and by maximum immunotype signature scores (MIS) for the
internal cohort. See also Figure S7, Tables S7, and S8.

Figure 6. Immunoprofiling of clinical cohorts and analysis of treatment response
(A) Graphical description of the breast cancer cohort (n = 33 patients) with neoadjuvant chemotherapy (NAC), blood draw, and surgical resection time points.
(B) Bar graphs for distribution of pathological complete responders (pCR) versus non-responders with residual disease (RD) within immunotype clusters (Fisher’s
exact test on a 532 table for count data, testing the relationship between immunotypes and treatment response) for on-treatment samples (left). Bar graphs for
distribution of immunotype clusters between pCR and RD for on-treatment samples (right).
(C) Boxplots showing G1 and G5 signature score distribution between RD and pCR for on-treatment samples (Mann-Whitney U test).
(D) ROC-AUC for each of the five signature scores for pCR versus RD in the breast cancer cohort.
(E) Graphical description of the PDAC cohort (n = 71 patients) with combination treatments and the blood draw time point at 4 weeks after the start of the trial,
noted as the C2D1 time point or day 30 (D30). The treatment types consisted of sotigalimab (sotiga) and/or nivolimab (nivo) combined with chemotherapy (CT),
indicated as A1, B2, and C2.
(F)Kaplan-Meierplot(multiple logrank test)showing progression freesurvival(PFS,left)and overall survival(OS, right) distribution forPDAC patientsassigned by
immunotypes.
(G) Bar graphs for distribution of short overall survival (sOS) versus long overall survival (LOS) within immunotypes (Fisher’s exact test on a 532 table for count
data, testing the relationship between immunotypes and treatment response) for blood samples at C2D1 time point (left). Bar graphs for distribution of im-
munotype clusters between sOS versus LOS for blood samples at C2D1 time point (right).
(H) Boxplots comparing the distribution of G3 signature scores between patients with sOS or LOS, for all that had received either A1, B2, or C2 treatment
combinations,forpatients witheither B2orC2treatments,andpatientswithA1,asindicated, basedonbloodsamplesdrawnattimepointC2D1.Thedistribution
of G2 signature score between patients with sOS and LOS was also compared (the median OS cutoff = 347 days, Mann-Whitney U test).
(I) ROC-AUC based on each signature score for all PDAC patients, patients with A1, and patients with B2 or C2, to show the performance of each signature score
in classifying SOS and LOS patients. Boxplots in C and H indicate the median and the 25th and 75th percentiles, and whiskers extend to the lowest and highest
value within 1.53 interquartile range. See also Table S8.

Figure 7. Establishing ICB response predictors for HNSCC cohorts based on immunotype signature scores (ISSs)
(A) Depiction of the HNSCC-Durva cohort (n = 32 patients) with treatment and blood draw timepoints. Bar plot shows the percentage of responders (R) and non-
responders (NR) from the total cohort of patients treated with durvalumab alone or durvalumab plus metformin.
(B) Bar graphs for immunotype clusters (left) (Fisher’s exact test on a 532 table for count data, testing the relationship between immunotypes and treatment
response) and responders (R) versus non-responders (NR) (right) for on-treatment blood samples.
(C) Boxplots showing the distribution of G3 (top left) and G4 (bottom left) ISSs between NR and R patients (Mann-Whitney U test). ROC-AUC evaluates the
performance of each of the five ISSs in distinguishing between on-treatment blood samples of Rs versus NRs (right).
(D) Bar graphs for immunotype clusters (left) (Fisher’s exact test on a 532 table for count data, testing the relationship between immunotypes and treatment
response) and R versus NR (right) for pre-treatment blood samples.
(E) Boxplots showing the distribution of G3 and G4 signature scores between NR and R (left) (Mann-Whitney U test). ROC-AUC of each signature score in
classifying R versus NR for pre-treatment blood samples (right).
(F) Waterfall plot showing differentially distributedcell populations with pvalue < 0.02 (Mann-Whitney U test) as the logfold difference for pre-treatment (baseline)
samples.
(G) Bar graph reflecting potential prognostic ROC-AUC of G4 ISS and a comparison with HNSCC tumor PD-L1 expression (RNA-seq based) as a benchmark
representative.
(H) Graphical description of the HNSCC-Nivo cohort (n = 35 patients) with treatment and blood draw timepoints. Bar plot shows the percentage of responders
(R) and non-responders (NR) from the total cohort of patients treated with nivolumab (nivo) alone or nivolumab plus indoleamine 2,3-dioxygenase (IDO) inhibi-
tor (IDOi).
(I) Bar graphs for immunotype clusters (left) (Fisher’s exact test on a 532 table for count data, testing the relationship between immunotypes and treatment
response) and R versus NR (right) for on-treatment blood samples.
(J) Boxplot for G2 signature score distribution between NRs (left) (Mann-Whitney U test). ROC-AUC for each signature score in classifying R versus NR for on-
treatment blood samples (right).
(K) Bar graphs for immunotype clusters (left) (Fisher’s exact test on a 532 table for count data, testing the relationship between immunotypes and treatment
response) and R versus NR (right) for pre-treatment blood samples.
(L) G2 signature score distribution between NR and R shown in boxplots (left) (Mann-Whitney U test). ROC-AUC for each signature score for pre-treatment blood
samples of R versus NR (right).
(M) Waterfall plot showing differentially distributed cell populations with p value < 0.05 (Mann-Whitney U test) and more than 20% difference for pre-treatment
(baseline) samples.
(N)Bargraphreflectingpotentialprognostic ROC-AUCvaluesofG2ISSandcomparison withtumorPD-L1expression,CD4 + Tcellpercentage, PD-1 positive CD8 +
T cell percentage and tumor mutational burden (TMB) as benchmark representatives. Boxplots in (C), (E), (J), and (L) indicate the median and the 25th and 75th
percentiles, and whiskers extend to the lowest and highest value within 1.53 interquartile range. See also Figure S8, Tables S8, and S9.

Figure 8. Analysis of HNSCC cohorts by HPV status
(A) Boxplot comparing G2 ISS distribution between responders (R) and non-responders (NR) based on pre-treatment PBMC samples of HPV+ patients from the
HNSCC-Nivo cohort (left) (Mann-Whitney U test). ROC-AUC for each signature score in classifying R versus NR from the pre-treatment samples of HPV+ pa-
tients (right).
(B) The distribution of G2 ISSs and ROC-AUCs for HPV? patients of the HNSCC-Nivo cohort.
(C) Thedistribution ofG3 and G4 ISSs between Rand NRHPV+patientsoftheHNSCC-Durvacohort basedon thepre-treatment PBMCsamples(Mann-Whitney
U test). ROC-AUC for each signature score in classifying R versus NR.
(D) The G3 and G4 ISS distributions for HPV? patients of the HNSCC-Durva cohort (Mann-Whitney U test), and associated ROC-AUCs. Boxplots indicate the
median and the 25th and 75th percentiles, and whiskers extend to the lowest and highest value within 1.53 interquartile range.


Figure S1: Gating strategy for selecting 34 cell subsets, related to Figure 1.
(A) CD4 + T cells (Panels CP8 and CP25). T cells were selected using tSNE and FlowSOM from all data
in the .fcs file except for that for Beads. The selected T cells were verified to be CD3 + and singlets. A
2D plot was used to select CD4 + Dump- T cells. An IL7RA vs CD25 plot was used to select CD4 + Tregs
(as CD25+ IL7RA-) from all CD4 + T cells. The remaining T-helper subtypes were selected using markers
CD45RA, CD27, and CD62L. CD4 + total memory: all CD4 + T cells except CD4 + Tregs and CD4 + Naive
T cells. CD4 + Naive Tregs were calculated as the intersection between CD4 + Naive T cells and CD4 +
Tregs. CD4 + CD39 + Tregs were calculated as the intersection between CD4 + Treg cells and CD4 +
CD39 + cells.
(B) CD8 + T cells (Panel CP7). T cells were selected using tSNE and FlowSOM from all data in the .fcs
file except for that for Beads. The selected T cells were verified to be CD3 + and singlets. A 2D plot was
used to select CD8 + Dump- T cells. The subtypes were selected using markers CD45RA, CD27, and
CD62L. CD8 + total memory: all CD8 + T cells except CD8 + Naive T cells. CD8 + T cells TIGIT + PD-1 +
were calculated as the intersection between CD8 + T cells TIGIT + and CD8 + T cells PD-1 + .
(C) NK cells (Panel CP26). NK cells were selected using tSNE and FlowSOM from all data in the .fcs
file except for that for Beads. A 2D plot was used to select CD56 + Dump- NK cells. Selected NK cells
were verified to be singlets. A CD56 vs. CD16 plot was used to identify immature NK cells (CD16 - ) and
mature NK cells (CD16 + ).
(D) NKT cells (Panel CP10). CD3 + CD56 + cells were selected using tSNE and FlowSOM from singlet
PBMCs in the .fcs file. A CD56 vs CD3 plot was used to identify NKT cells.
(E) γδ-T cells (Panel CP28). T cells were selected using tSNE and FlowSOM from all data from the .fcs
file except for that for Beads. The selected T cells were verified to be singlets. A 2D plot was used to
select CD3 + Dump- T cells. A TCRγδ vs Vδ2 + plot was used to identify Vδ2 + γδ-T cells.
(F) Dendritic cells (DC) (Panel CP16). A 2D plot was used to select HLA-DR + Dump- cells. From these
cells, CD14 - CD16 - cells were selected using a 2D plot. For these cells, tSNE and clustering were used
to identify pDC (CD123 + ), cDC1 (CD141 + and CLEC9A + ), and cDC2 (CD1c + and CD11c + ). The sum of
these cell populations was identified as DCs.
(G) Monocytes (Panel CP23). A 2D plot is used to select CD15 - Dump- cells. From these cells, CD16 -
CD33 - cells were excluded using a 2D plot. From the rest of the cells, a 2D plot was used to exclude
CD16 - CD14 - . The rest of the cells were identified as monocytes. Selected monocytes were verified to
be Viability- and singlets. Subsequently, the monocytes were separated into classical monocytes
(CD14 + CD16 - ) and non-classical monocytes (CD14 -/low CD16 + ) using CD16 vs. CD14. Further steps
were performed to separate HLA-DR low monocytes from classical monocytes. A 2D Plot was
constructed for all cells from the .fcs file except for that for Beads and Debris.
(H) Granulocytes (Panel CP10). Granulocyte selection was performed using all data in the .fcs file
except for that for Beads, Debris, and Aggregates. A CD66b vs CD193 (CCR3) plot was used to identify
Neutrophils (CD193 (CCR3) - CD66b + ), Eosinophils (CD193 (CCR3) + CD66b + ), and Basophils (CD193
(CCR3) + CD66b - ). After the selection, basophils were verified to be CD123 + and Viability-, eosinophils
were verified to be Viability dim, and neutrophils were verified to be Viability-. All selected Granulocytes
were verified to be CD3 - , CD19 - , and CD56 - .
(I) B cells (Panel CP22). B cells were selected using tSNE and FlowSOM from all data in the .fcs file
except for that for Beads. A 2D plot was used to select CD19 + Dump- cells. For these cells, tSNE,
clustering, and a 2D plot were used to identify naive B cells (IgD + and CD27 - ), non-switched memory
IgM B cells (IgD + and CD27 + ), and memory B cells (IgD - ). Next, cells with CD27 + CD138 + and CD27 +
CD38 + phenotypes were excluded from memory B cells to be designated as switched memory B cells.

Figure S2: Construction of cell-typing models and comparison with manual analysis of flow
cytometry data, related to Figure 1.
(A) A workflow for training the machine learning cell-typing models for our flow cytometry data analysis
platform.
(B) Correlation between the labels predicted by our cell-typing model and cell type labels from the
manual supervised gating analysis of flow cytometry samples (Spearman’s correlation coefficient  ρ ).


Figure S3: Investigating the immune cell composition in the peripheral blood of healthy donors
and cancer patients, related to Figure 2.
(A) Hematology analysis of whole blood for complete blood count (CBC). The absolute numbers of
blood cell populations in whole blood samples from healthy donors (n = 408) and cancer patients (n =
442) of the internal cohort, as measured by the hematology analyzer (Mann-Whitney U Test). Box plots
indicate median, 25th and 75th percentiles, and whiskers extend to the lowest and highest value within
1.5x interquartile range.
(B) The workflow for training the healthy/cancer classifier.

Figure S4: Comparison of RNA-seq deconvolution of cell types with flow cytometry analysis,
related to Figure 3.
(A) Heatmap generated with deconvolution by Kassandra. Immunotype labels based on
flow cytometry clusterization are shown.
(B) Comparison of cell distribution obtained from flow cytometry analysis with that from RNA-seq-based
cell deconvolution for samples from our internal cohort.


Figure S5: Analysis of differential gene expression and gene signatures related to
immunological pathways among immunotypes, related to Figure 3.
(A) Volcano plot of differentially expressed genes for each of the five immunotypes versus the sum of
all other immunotypes (Generalized linear model likelihood ratio test).
(B) Heatmap showing gene set enrichment analysis scores (GSEA, see Table S6 for full list) for
RNA-seq samples aligned on clusters in open-source genesets from mSigDB.


Figure S6: T cell receptor/B cell receptor (TCR/BCR) analysis, related to Figure 4.
(A) Bubble plots showing the distribution of the HLA-B allele between clusters with the average TCRβ
clonality.
(B) Percentage distribution of the largest TCRβ clone for immunotypes G1–G5. Games-Howell post-
hoc test: * p < 0.05, **** p < 0.0001.
(C) The TCRα landscape.
(D) Distribution of the largest TCRα clone, TCRα clonality, and diversity indices. Games-Howell post-
hoc test: ** p < 0.01, **** p < 0.0001.
(E) Diversity indices of BCR immunoglobulin heavy chain and the λ and κ light chains. Games-Howell
post-hoc test: * p < 0.05, ** p < 0.01, *** p < 0.001, **** p < 0.0001.
Boxplot in B, D and E indicate median, 25th and 75th percentiles, and whiskers extend to the lowest
and highest value within 1.5x interquartile range.


Figure S7: Comparison of the immunotype distribution in the internal cohort and open-source
collection for healthy donors and solid cancer patients, related to Figure 5. (A) Heatmap
showing fold changes for max to min for each assigned cluster in internal cohort (left) and open-
source data (right) (Mann-Whitney U test to test significance of differences). (B) Bar plots showing the
distribution of the five immunotypes for cancer patients and healthy donors from the internal and
open-source cohorts.


Figure S8: Dynamic analysis of the immunotypes assigned to patients before and during
treatment, related to Figure 7. Sankey plots showing the immunotype classification for pre-treatment
and on-treatment blood samples of responder (R) and non-responder (NR) patients in the HNSCC-Nivo
cohort (A) and HNSCC-Durva cohort (B).


'''
任务描述： 请根据描述详细讲解Fig.1a的结果和图例描述（不要用比喻的方式）,并根据结果和图例描述讲解完成这个图例的目的,输出格式如下：

    结果描述：
    图例描述：
    关键结论:
    分析目的：




