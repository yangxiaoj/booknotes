你是一个生物信息学术专家，请详细阅读三引号中的文本，然后完成以下任务。 '''

# 标题：Genome-wide association analysis of left ventricular imaging-derived phenotypes identifies 72 risk loci and yields genetic insights into hypertrophic cardiomyopathy


## Summary:

Left ventricular regional wall thickness (LVRWT) is an independent predictor
of morbidity and mortality in cardiovascular diseases (CVDs). To identify
specific genetic influences on individual LVRWT, we established a novel deep
learning algorithm to calculate 12 LVRWTs accurately in 42,194 individuals
from the UK Biobank with cardiac magnetic resonance (CMR) imaging.
Genome-wide association studies of CMR-derived 12 LVRWTs identified 72
significant genetic loci associated with at least one LVRWT phenotype
(P<5×10 −8 ), which were revealed to actively participate in heart development
and contraction pathways. Significant causal relationships were observed
between the LVRWT traits and hypertrophic cardiomyopathy (HCM) using
genetic correlation and Mendelian randomization analyses (P<0.01). The
polygenic risk score of inferoseptal LVRWT at end systole exhibited a notable
association with incident HCM, facilitating the identification of high-risk
individuals.ThefindingsyieldinsightsintothegeneticdeterminantsofLVRWT
phenotypes and shed light on the biological basis for HCM etiology.


##  Introduction:

The critical role of left ventricular (LV) structure and function in
adversely affecting the prognosis of individuals is increasingly
acknowledged. Changes in LV structure and function have been
associated with acute myocardial infarction 1 , heart failure 2 and
mortality 3 . Likewise, the LV wall thickness is an independent pre-
dictor of morbidity and mortality of hypertrophic cardiomyopathy
(HCM) 4 , diastolic dysfunction 5 , and ventricular arrhythmias 6 . Various
LVregionalwall thicknesses(LVRWT) occurred withdifferent clinical
implications 7,8 ,anditsquantitativeanalysisisofgreatsignificancefor
the diagnosis of cardiovascular disease (CVD) 9 . Hence, LVRWT
serving as intermediate phenotypes for CVD is needed for timely
detection.
Cardiovascular magnetic resonance (CMR) is one of the most
popular medical imaging modalities to quantify the LV phenotypes
due to its noninvasive and versatile nature 10 . However, the highly
variable cardiacstructures acrossdifferent subjects andquantification
tasks of small targets pose the biggest challenge to accurate estima-
tions of cardiac wall thicknesses in large investigations 11 . As a result,
such a large-scale genome-wide association (GWAS) study of the
LVRWT imaging phenotype has not been performed to date. Previous research on the genetic architecture of CMR-derived traits con-
centrated primarily on LV volumetric and functional metrics such as
stroke volume and ejection fraction 2,12 . To solve this issue, we estab-
lished a novel deep-learning framework named Myocardial Segmen-
tation and Measurement Method (MSMM) to precisely estimate
LVRWT. The UK Biobank (UKB), one of the largest population imaging
studies, has acquired both high-quality standardized CMR examina-
tions and genotype data 13 , offering a tremendous opportunity to
investigate the unknown genetic determinants of LVRWT traits.
In this study, we aimed to investigate the genetic basis of 12
LVRWTs: anterior, anteroseptal, inferoseptal, inferior, inferolateral, and
anterolateral LVRWT at end diastole and end systole. Using a deep
learning-based method to segment LV structure and design an auto-
maticmeasurementalgorithmtoquantifymyocardialwallthickness,we
performed GWASs on 12 LVRWT traits (all derived from the mid-cavity
slice with half obtained during end-systole (ES) phase and half during
end-diastole (ED) phase) in 42,194 UKB participants. We then evaluated
the putative causal relationships between the LVRWT traits and CVDs
using genetic correlation and Mendelian randomization (MR) analyses.
Finally, we established the polygenic risk score (PRS) of each LVRWT
trait,andvalidatedwhethertheLVRWT-PRSshavetheabilitytoidentify
HCM in 439,981 individuals without CMR imaging. Overall, this study
substantially enhances our knowledge of the genetic basis of LVRWT
and may provide valuable risk stratification guidance to identify high-
risk sub-populations in individualized HCM prevention.


## Results:

### Segmentation of left ventricle with deep learning
TheMSMMprocedureweestablishedtomeasurethethicknesseswere
presented in Fig. 1. To achieve state-of-the-art performance in seg-
mentation tasks, we trained the deep learning model using the Auto-
mated Cardiac Diagnosis Challenge (ACDC) dataset 14,15 annotated by
one clinical expert, which has a total of 1902 annotated images. We
randomly selected 1420 short axis images for training, 100 short axis
images for validation and 382 short axis images for testing. Within the
382 testing images, 80 images belong to the two mid-cavity slices.
Since only the mid-cavity slice quantification results were used for the
subsequent analysis, we evaluated the methods on two mid-cavity
slices of each case to ensure a consistent comparison. Moreover, we
included500mid-cavityimagesfromtheUKBdatasetforindependent
evaluationbecausethatGWASsareperformedontheUKBdataset.The
Deep Layer Aggregation based deep learning model 16,17 as the network
architecture (DLANet) was trained from 1420 ACDC images. The Deep
Layer Aggregation (DLA)-based deep learning model as the network
architecture was trained from these data. The trained deep learning
model was then used to output LV segmentation results in the UKB
imagingsubstudyofover45,000people 18 .Detailedinformationabout
model training, as well as quantitative and qualitative results, can be
found in the “Methods“ section and Supplementary Methods.
### Measurement of high-quality left ventricular regional wall thicknesses
We applied a measurement-based quantification method to post-
processthe deep learning output to measurethe LVRWT traits.A total
of45,353participantswithCMRimagingwereidentifiedforanalysesin
the UKB. For these individuals, 6 LVRWT phenotypes at end systole
[end-systolic anterior (ES-A), end-systolic anteroseptal (ES-AS), end-
systolic inferoseptal (ES-IS), end-systolic inferior (ES-I), end-systolic
inferolateral (ES-IL), end-systolic anterolateral (ES-AL) LVRWT] and 6
LVRWT phenotypesatenddiastole [end-diastolicanterior (ED-A),end-
diastolic anteroseptal (ED-AS), end-diastolic inferoseptal (ED-IS),
end-diastolic inferior (ED-I), end-diastolic inferolateral (ED-IL), end-
diastolic anterolateral (ED-AL) LVRWT] were available. Following the
exclusion of poor image quality and sample quality-control procedures,42,194 individualsfreefromadiagnosisofmyocardialinfarction
or heart failure remained (Supplementary Fig. 1). The average age of
the cohort at the time of imaging visit was 64.1 years, and 47.3% were
men at end systole and 47.2% at end diastole (Supplementary Table 1).
The mean and standard deviation of 12 LVRWT phenotypes are
reported in Supplementary Table 2. We next sought to estimate the phenotypic correlations of LVRWT traits. The strong positive pheno-
typic correlations were observed between regions of the same cardiac
cycle phases (r 2 =0.82 between ES-IL and ES-AL), and the end-diastolic
LVRWT phenotypes and end-systolic LVRWT phenotypes were mod-
estly positively correlated with one another (Supplementary Fig. 2a),
which is not unexpected, given their firm physiological associations.
Furthermore, to gain insight into the dimensionality of the data, we
conducted a principal component analysis (PCA) and identified that
utilizing five principal components explained over 90% of the varia-
bility in the LVRWT measurements (Supplementary Fig. 2b).
### Genome-wide association studies of left ventricular regional
wall thicknesses
To understand the common genetic basis for variation in myocardial
wall thickness, we performed a series of GWAS on 12 LVRWT traits
within each cohort. Firstly, due to the nonnormal distribution, we performed the rank-based inverse normal transformation of the residuals of LVRWTphenotypes(SupplementaryFig.3).There was noevidence of
confounding from populations tratification or cryptic relatedness inour GWAS analyses, as demonstrated by low genomic inflation factor
(λ=1.050–1.099, Supplementary Fig. 4). Furthermore, we identified a total of 72 genome-wide significant variants associated with the 12
LVRWT traits (P<5×10 −8 ), including 16 variants for IS, 2 variants for I, 7
variantsforIL,10variantsforAL,3variantsforAand7variantsforASat
end systole stage; 5 variants for IS, 3 variants for I, 3 variants for IL, 4
variants for AL, 3 variants for A and 9 variants for AS at end diastole
stage, respectively (Fig. 2 and Supplementary Data 1). Interestingly,
there have 10 genetic variants associated with multiple LVRWT traits,
resulting in 62 unique variants associated with the 12 LVRWT traits; for
example,rs7928419inSPI1at11p11.2reachedgenome-widesignificance
in ES-IS, ED-IS and ED-AS (P ES-IS =1.0×10 −12 , P ED-IS =1.3×10 −9 ,
P ED-AS =1.2×10 −8 ,SupplementaryFig.5).Furthermore,followingthefive
PCscorrectionformultipletests,weobservedthat47variantsremained
significant (P<1.0×10 −8 , Supplementary Data 1).
### Functional characterization for risk variants of 12 LVRWT traits
The LVRWT GWAS loci harbored a total of 6345 candidate variants in
linkage disequilibrium (LD, r 2 >0.6) with 62 lead variants. To char-
acterize the features for risk variants of 12 LVRWT traits, we first gen-
erated the control variants set and functionally defined the genomic
position distribution of variants via SnpEff 19 . Compared with control
variants, wefound riskvariants were significant enriched within intron
region,geneupstreamanddownstreamregions,andintergenicregion
(Fig. 3a, b). We next investigated whether risk variants are enriched
among genetic regulatory elements. We observed significant enrich-
ments for risk variants of 12 LVRWT traits within the histone marks of
promoters [H3K4 trimethylation markers (H3K4me3)], enhancers
[H3K4 monomethylation marks (H3K4me1), H3K27 acetylation marks
(H3K27ac) and H3K36 trimethylation markers (H3K36me3)], and
transcriptionalfactor binding sites (TFBSs), while significant depletion
among repressive transcription [H3K9 trimethylation markers
(H3K9me3)] (Fig. 3c). Furthermore, to examine the characteristics for
risk variants of 12 LVRWT traits in the context of their potential contribution to CVDs susceptibility, we conducted enrichment analyses
usingthedataofGWASsummarystatisticsfrom11selectedCVDstraits
(Supplementary Data 2). As a result, risk variants of 12 LVRWTs were
observed significantly enriched among CVDs GWASs loci (Fig. 3d). To sum up, these results indicated that risk variants may regulate the expression of genes by activating chromatin state, and might result in an increased CVDs incidence.
### Identification and functional annotation of susceptible genes
associated with left ventricular regional wall thicknesses
We further sought to identify candidate genes influencing LVRWT
phenotypic variation using an integrative approach supported by
multiple lines of evidence (Supplementary Fig. 6). Based on the
downstream analysis of the discovery GWAS summary statistics, for
end diastole and end systole, respectively, 31 genes and 21 genes were
identified by position (±1Mb of the lead variant) (Supplementary
Data 1); 58 genes and 50 genes were discovered by expression quan-
titative trait locus (eQTL) mapping (Supplementary Data 3); and 45
genes and 25 genes were identified by transcriptome-wide analysis
(TWAS) (Supplementary Data 4–9). Besides, Multi-marker Analysis of
GenoMic Annotation(MAGMA) gene-basedanalyses yielded55and44
significant genes for end diastole and end systole, respectively, (mean
χ 2 statistics, P<2.64×10 −6 ) (Supplementary Data 10). We combined all
ofgenesannotatedusingthefourmethods.Asseverallociwereshared
by multiple traits; counting each locus only once, we totally identified
127 candidate genes at end systole and 95 candidate genes at end
diastole, respectively (Supplementary Data 11). Notably, ALPK3 was
annotated by the four methods, and rs3803405 in proximity to ALPK3
was the most significant variants in this study. MYBPC3, which was
identified by the MAGMA analysis for inferoseptal LVRWT at end sys-
tole, is one of the two most well-known HCM causal genes 20 . ALPK3 21 ,
NMB 22 , and WNT3 23 loci, which are significant candidate genes that
have been linked to inherited CVDs, were shared across most LVRWT
traits (Supplementary Fig. 7).
To further dissert the potential function of the candidate genes,
wecharacterizedthebiologicalpathwaysassociatedwiththe127genes
at end systole and 95 genes at end diastole. The GO analyses demon-
strated that the candidate genes are remarkably enriched in the bio-
logical pathways correlated with the heart development, heart
contraction, and cardiac muscle cell development, which are essential
for cardiac remodeling (Fig. 4a, b and Supplementary Data 12). The
tissue expression analyses were performed separately for 54 specific
tissue types,and tissues from the heart atrial appendage and heart left
ventricle showed the most significant P value (P=2.64×10 −6 ) in most
LVRWT traits (Fig. 4c, d and Supplementary Data 13). In summary,
these findings significantly advance our understanding of the genetic
basis of LVRWT phenotypes and suggest that candidate genes encode
essential proteins involved in the construction and maintenance of
sarcomeric infrastructure.
### Heritability and genetic correlation of left ventricular regional wall thicknesses
We next estimated the proportion of LVRWT phenotypic variation
attributable to the genotypes by the variance component analyses.
The highest genome-wide variant heritability estimates were
observed for inferoseptal LVRWT at end systole (ED-IS, at 28%), followed by inferoseptal LVRWT at end diastole (ED-IS, at 25%), while
heritabilities were lower for anterior and anterolateral LVRWT at end
diastole, which had a heritability of 17% (Fig. 5a). We observed sig-
nificantly genetic correlations between LVRWT traits ranging from
high(r g =0.97betweenES-ILandES-A)tolow(r g =0.42between ES-A
and ED-AS; Fig. 5a). Strong positive genetic correlations were generally found between regions of the same cardiac cycle phases and moderate correlations between regions of the different cardiac cycle phases, which may reflect genetic effects acting on the development of the cardiac wall.
DuetotheinterdependentnatureofLVRWTandLVchambersand
the importance of wall thickness remodeling, we first sought to
quantify the strength of their genetic correlations by linkage dis-
equilibrium score regression (LDSC) analyses using our LVRWT sum-
mary statistics and the summary data from a recently published LV
GWAS 12 .TheLVRWTtraitshadhighlypositivegeneticcorrelationswith
LV volumetric and functional traits such as LV ejection fraction (LVEF)
and stroke volume (SV) (r g range: 0.16–0.60), and negative genetic
correlations with LVRWT traits were observed between LV end-
diastolic volume (LVEDV), LV end-systolic volume (LVESV) and the
body-surface-area indexed versions of these traits, including LVEDVi and LVESVi (r g range: −0.58 to −0.13), which emphasized their strong
physiological connections (Fig. 5b and Supplementary Data 14).
Additionally,wealsoinvestigatedthegeneticcorrelationsbetweenthe
12 LVRWT traits and cardiac measurements that could mediate the
CVDs progression. The LVRWT traits were highly positively connected
with traits such as heart rate, diastolic and systolic blood pressure (r g
range: 0.11–0.45, Fig. 5b and Supplementary Data 14). Collectively,
thesefindingssupportthejustificationforinvestigatingthegeneticsof
LVRWT traits as a complementary gateway to understanding the drivers of cardiac remodeling.
### Genetic correlation analyses between left ventricular regional wall thicknesses with cardiovascular diseases
ToexaminesharedgeneticeffectsbetweenLVRWTtraitsandCVDs,we
performed genetic correlation analyses with GWAS summary statistics
from 11 selected CVDs traits. As expected, we observed statistically
positive genetic correlations of 12 LVRWT traits with CVDs such as
HCM, hypertension, pulmonary hypertension, chronic ischemic heart
disease, and ischemic stroke. Anterior LVRWT at end diastole had the
highest genetic correlation estimate with HCM than other LVRWT
traits (ED-A: r g =0.65, P=7.0×10 −4 ). For inferoseptal LVRWT, we
observed positive genetic correlations with HCM at both end systole
and end diastole (ES-IS: r g =0.52, P=1.4×10 −3 ; ED-IS: r g =0.42,
P=6.8×10 −3 ). Furthermore, HCM as the disease had the highest
genetic correlation estimates with LVRWT than other CVDs (r g range:
0.37–0.65) (Fig. 5c and Supplementary Data 15). In full, these findings
of the genetic correlations between LVRWT traits with CVDs provide
quantitative support for genetic overlap.
### Mendelian randomization of left ventricular regional wall thicknesses exposures and cardiovascular diseases
Thegeneticcorrelationsbetween12LVRWTtraitsandCVDsriskledus
to the hypothesis that the increased LVRWT traits are causally asso-
ciated with CVDs. We then tested such potential causality between 12
LVRWT exposures and CVDs outcomes using two-sample Mendelian
randomization (MR). Although heterogeneity and the number of var-
iants in the exposure-outcome effects are limitations, the findings of
the inverse-variance-weighted method and sensitivity analyses sup-
portcausalrelationsbetween10of12LVRWTtraitsandincreasedHCM
risk (beta range: 0.45 to 3.10, P<0.01) (Fig. 6 and Supplementary
Data 16). We also found robust support for the causal effects of
inferolateral, anteroseptal, and anterior LVRWT on cardiomyopathy at
end systole and end diastole (P<0.01). However, there is no statisti-
cally significant effect on hypertension, angina pectoris, myocardial
infarction, chronic ischemic heart disease, and ischemic stroke
(P>0.05). Taken together, these findings suggest that the genetic
relationships between LVRWT traits and HCM may partly reflect
underlying causal processes.

### Polygenetic risk scores influence the risk for incident hypertrophic cardiomyopathy
Foreachofthe12LVRWTtraits,wederivedPRSsweightingthegenetic
dosage by the effect size of independent genetic variants located at
autosome (P<1×10 −5 ) from each LVRWT traits GWAS (Supplementary
Data 17). We investigated whether PRSs could discriminate the 12
LVRWT traits. As expected, participants with a higher PRS tended to
have thicker LVRWT for all 12 LVRWT traits, especially for inferoseptal
LVRWT at end systole and end diastole (Fig. 7a, b and Supplementary
Figs. 8a, b–12a, b), suggesting that the PRSs yielded favorable dis-
crimination for the LVRWTs.
Having establishedthe causaleffects of LVRWTtraits on HCM, we
then sought to evaluate whether a genetic predisposition to LVRWT
traits is associated with incident HCM in the remaining 439,981 indi-
viduals without CMR imaging data. We found that the PRS tertiles of
inferoseptal LVRWT at end systole were associated with higher risk of HCM (hazard ratio (HR) ES-IS =1.69, 95% CI=1.33–2.15, P=2.31×10 −5 for
high tertile vs. low tertile, Supplementary Data 18). As expected, the
PRS of inferoseptal LVRWT at end systole exhibited effective risk
stratification within the HCM population (Fig.7c).Moreover,wefound
that the PRS of inferoseptal LVRWT at end systole enabled a clear
distinction between incident HCM cases and healthycontrols(Fig. 7e).
In addition, we found the similar results in inferolateral, anterolateral,
anterior and anteroseptal LVRWT at end systole, and inferior, infer-
olateralandanteriorLVRWTatenddiastole(SupplementaryFigs.8d,f,
9c–f, 10c, e, 11c–f and 12c, e). Regrettably, the other 4 LVRWT traits
(inferior LVRWT at end systole, and inferoseptal, anterolateral, and
anteroseptal LVRWT at end diastole) did not exhibit strong perfor-
mance in identifying individuals at elevated risk (Fig. 7d, f and Sup-
plementary Figs. 8c, e, 10d, f and 12d, f). We also assessed the correlation between the constructed PRS for LVRWT traits and 10
other CVDs (Supplementary Data 18). We calculated the C-statistic for
our HCM PRSs and noticed that it is not sufficiently satisfactory.
However, a slight improvement is noted after further integrating the
relevant PRS with clinical risk factors, as depicted in Supplementary
Fig. 13. Despite the modest C-statistic values, this enhancement
underscores the efficacy of our PRS in identifying individuals at an
elevated risk for HCM. In total, higher genetically determined LVRWT
was associated with higher HCM risk, which may provide valuable risk
stratification guidance to identify high-risk individuals.

## Methods
### Study population
The UKB is a large prospective cohort study of over 500,000 partici-
pants recruited at 22 assessment centers across the UK between 2006
and 2010. It has gathered a wealth of information on participants,
including health and lifestyle data, physical measurements, biological
samples, imputed genome-wide genotypes and imaging data. All par-
ticipantsprovidedinformedconsent.Theethicalcommitteesfromthe
North West Multi-Center Research Ethics approved the study.
Sample selection
Disease information based on the UKB Field ID and date of first in-
patient diagnosis is provided in Supplementary Data 19. In total, we
analyzed 45,353 participants with CMR who had not withdrawn con-
sent as of December 2020. After excluding participants with poor
imaging, missing information on genetic data, previous myocardial
infarction, diagnosis of heart failure as well as body mass index
(BMI)<16 or > 40kg/m 2 , 42,194 individuals were included in the ana-
lysis following the quality-control procedures outlined in Supple-
mentary Fig. 1. Among the initial 456,937 individuals without CMR
data, we excluded individuals without genotype data, resulting in a
final sample size of 442,889 individuals. After accounting for missing
informationonsmokingandalcoholconsumption,thesamplesizewas
further reduced to 440,085 individuals. Additionally, in subsequent
analyses focusingonspecific diseases,we further excludedindividuals
who had the corresponding disease prior to their enrollment in the
UKB. For instance, in the case of HCM, we excluded 104 individuals
who had HCM before their enrollment, resulting in a final sample size
of 439,981 individuals.
### Definitions of covariates and phenotypes
All covariates recorded at the imaging visit were used in the analysis
where possible. The UKB Data-Fields of covariates were listed in Sup-
plementaryData20.BMIwascalculatedas:weight(kg)/height(m) 2 .The
definitions were used for GWAS participant exclusion and PRS
assessment.
### Semantic segmentation and deep learning model training
CMR protocol had previously been described in detail 13 . In brief, CMR
was performed with 1.5 Tesla scanners (MAGNETOM Aera, Syngo
Platform VD13A, Siemens Healthcare, Erlangen, Germany) using elec-
trocardiographic gating for cardiac synchronization. Long-axis cines
and a complete short-axis stack of balanced steady-state free preces-
sion cines were acquired at one slice per breath hold.
Semantic segmentation aims to assign a label to each pixel in an
image. In the proposed MSMM framework, the deep learning model
for segmentation learns to extract MR image features and output one
of three different classes for each pixel, including background, LV
cavity, and LV myocardium. Labels of LV structures in the ACDC
(https://www.creatis.insa-lyon.fr/Challenge/acdc/index.html) dataset
are annotated by one clinical expert. There are 1420 images for train-
ing process, 100 images for validation and 382 images for testing
process. Additionally, we resorted to a doctor who has 7 years of
clinical experience to label the LV cavity and LV myocardium on the
UKB dataset for a comprehensive evaluation. During the testing stage,
80 mid-cavity slices from the ACDC dataset and 500 mid-cavity slices
from the UKB dataset were employed for evaluating the performance
of the segmentation model.
We utilized the DLANet 16,17 architecture as a segmentation model,
whichuses two types of structures:the Hierarchical Deep Aggregation
(HDA) and the Iterative Deep Aggregation (IDA). With the HDA and
IDA, the DLA architecture canbetter merge information from multiple
layers and scales, and achieve state-of-the-art performance in the
segmentation task. DLANet with 166 hidden layers and 20,576,932
parameters was implemented in Pytorch. Training and inference pro-
cesses were performed on NVIDIA GeForce GTX 1080 Ti GPUs. During
the training process, the DLANet was trained from scratch for 1000
epochs. We employed the Adam 45 optimizer for minimizing the Dice
Loss 46 . The initial learning rate was set to 1×10 −3 and decayed by 0.99 everyepoch. The weight decay was 1×10 −5 . At the inference stage, one
frame of a patient with all slices in the size of (8–12)*256*256 will take
about 0.5s on one GPU. Additionally, we compared the performance
of the DLANet with state-of-the-artmethods by re-implementing them
and reporting the results in Supplementary Data 21 and 22. The com-
parative analysis across different datasets provides valuable insights
into the efficacy of our proposed deep learning model.
Beforethetrainingprocess,wefirstperformeddatapreprocessing
operations. The in-plane resolution of the original cardiac MR images
was resampled to 1.25mm×1.25mm, and then the resampled images
were cropped or padded to a size of 256×256. During training, data
augmentations were employed including random shifting, rotation,
scaling and so on. For images at the base or apex of the LV, we over-
sampled them more than one times in an epoch to increase their fre-
quencyduringthe training data andimprove theperformanceon these
imagesfortheirdifficulty.Weranvalidationevery20epochsoftraining,
and when the training process was complete, we selected the DLANet
that performs best on the validation set for testing. Finally, the trained
model output LV segmentation results on the UKB dataset and the
results were used for subsequent quantification of the myocardium.
For quantification, we designed a measurement-based method to
calculate wall thicknesses. Before the measurement, we normalize the
MR images 47 by rotation to the fixed arrangement in order to perform
subsequent measurements. The thicknesses rely on the calculation of
the distance between the center and the contour of the mask, either
epicardium or endocardium, for some direction. To this end, we first
converted the Cartesian coordinate system into a polar coordinate
system and then generated the distance based on the direction angle.
Finally, we averaged ten measurements for wall thicknesses. We then
used MSMM to calculate the myocardial thicknesses in the UKB. We
obtained accurate estimations of 12 LVRWT traits which included 6
LVRWT phenotypes at end systole (ES-IS, ES-I, ES-IL, ES-AL, ES-A, and
ES-AS)and6LVRWTphenotypesatenddiastole(ED-IS,ED-I,ED-IL,ED-
AL, ED-A, and ED-AS). Additionally, we assessed the DLANet’s perfor-
mance across various training dataset sizes, as detailed in Supple-
mentary Data 23 and 24, demonstrating the model’s robustness even
with limited training data. The techniques used to postprocess the
deep learning output to measure wall thickness is described in
the Supplementary Methods.
### Genotyping and imputation
Detailed information on genotyping and imputation in the UKB has
been described previously 48 . Briefly, participants were genotyped
based on UK BiLEVE Axiom™ Arrayby Affymetrix (807,411 markers for
49,950 participants) and UKB Axiom Array by Affymetrix (825,927
markers for 438,427 participants). Genotype imputation was based on
merged UK10K sequencing and 1000 Genomes phase3 reference
panels with SHAPEIT3 and IMPUTE3 49 . Variant positions were keyed to
the GRCh37 human genome reference.
### GWAS and heritability
We calculated the residuals by regressing LVRWT phenotypes on the
covariatesage,sex,BMI,andimaging center.WeperformedtheGWAS
of each normalized LVRWT trait using a linear mixed-model method
using ~8.5 million well-imputed variants with minor allele frequency
(MAF)≥1% and imputation quality (INFO) score >0.3 by BOLT-LMM.
Wenextestimatedtheheritabilityexplainedbythegenotypedvariants
(h 2 g variant) using BOLT-RELM. Both GWAS and heritability analysis
models were adjusted for age, sex, BMI, and principal compo-
nent (PC) 1–10.
### Genetic correlation
Using summary statistics, we applied LDSC software 50 to estimate the
genetic correlations (1) between 12 LVRWT traits; (2) between 12
LVRWT traits and 10 cardiac structure and function traits 12 : heart rate,
diastolic blood pressure, systolic blood pressure, LV end-diastolic
volume (LVEDV), LV end-systolic volume (LVESV), stroke volume (SV),
the body-surface-area (BSA) indexed versions of these traits (LVEDVi,
LVESVi, and SVi), and LV ejection fraction (LVEF); and (3) between 12
LVRWT traits and 11 CVDs: hypertension, pulmonary hypertension,
dilated cardiomyopathy, HCM, cardiomyopathy, HEART FAILURE,
atrial fibrillation, myocardial infarction, angina pectoris, chronic
ischemic heart disease, ischemic stroke. Data sources of summary
statistics for genetic correlation analyses were listed in Supplemen-
tary Data 2.
Given the unavailability of GWAS summary data for hypertrophic
cardiomyopathy, pulmonary arterial hypertension, and dilated cardi-
omyopathies, we performed GWAS analyses utilizing ~8.5 million well-
imputed variants, each with a MAF≥1%, and an INFO score exceeding
0.3, using data from the UKB. Each GWAS analysis was adjusted for
covariates including age, sex, BMI, smoking status, alcohol intake
frequency,andthefirsttenprincipalcomponents(PC1-10).Thesample
sizes for each disease were as follows: hypertrophic cardiomyopathy
(552 cases and 2208 controls), pulmonary arterial hypertension (2047
cases and 8301 controls), and dilated cardiomyopathies (1303 cases
and 5281 controls).
### Functional follow-up with FUMA
The web tool Functional Mapping and Annotation of Genome-Wide
Association Studies (FUMA) has previously been described in detail
(https://fuma.ctglab.nl/) 51 . Genome-wide significant variants were
defined by trait associations P<5×10 −8 and r 2 <0.1 with correlated
variants in 250kb region using FUMA.
Weutilizedtwomainapproachestomapgenome-widesignificant
loci to genes via FUMA default settings and specialized datasets, as
describedfollows:(1)positionalmappingofvariants,wherebyvariants
within a 10kB window from known protein-coding genes in the human
reference assembly (GRCh37/hg19) are mapped; (2) eQTL mapping
whereby allelic variations at a variant is significantly linked to expres-
sion of a gene, where we considered eQTLs within heart atrial appen-
dage and heart left ventricle from GTEx v8.
We also performed a generalized gene-set analysis using MAGMA
within FUMA. variants within exonic, intronic, and untranslated
regions were chosen for each gene. The 18,888 protein-coding genes
were usedinMAGMA. The meanofthe summary statistic(χ 2 ) ofGWAS
for the variants in a gene was used to determine the gene-based P
value 52 . The Bonferroni method was used to calculate the P value sig-
nificance threshold, which is 2.64×10 −6 when 0.05 is divided by the
total number of genes (18,888).
### Transcriptome-wide association study
For each of the 12 LVRWT phenotypes, we performed a TWAS to
identify the most strongly associated gene at each locus based on
imputed cis-regulated gene expression. We used FUSION with eQTL
data from GTEx v8. Precomputed transcript expression reference
weights for the LV (5886 genes), the atrial appendage (6740 genes),
and the artery coronary (3989 genes) were obtained from the FUSION
authors’ website (http://gusevlab.org/projects/fusion/). A P<8.49×
10 −6 was considered significant in LV tissue, a P<7.42×10 −6 was con-
sidered significant in atrial appendage tissue, a P<1.28×10 −5 was
considered significant in artery coronary tissue. FUSION was then run
with its default settings.
### Enrichment and tissue expression analyses
Functional enrichment and pathway characterization of the 127 can-
didate genes at end systole and 95 candidate genes at end diastole
weredoneinthewebsite(http://kobas.cbi.pku.edu.cn/)toobtainGene
Ontology (GO) terms. Tissue expression analyses were obtained from
GTEx which were also integrated in FUMA. Average gene expression
pertissuetypewasutilizedasagenecovariatetotestforapositivelink between gene expression in a given tissue type and genetic
correlations.
### Mendelian randomization
We used MR to estimate causal effects between the 12 LVRWT expo-
sures and 11 CVDs. For two sample MR analyses, we used MR-Egger
regression, weighted median and mode-based estimations as sensi-
tivity analyses, along with the inverse-variance weighted (IVW) tech-
nique as our major model. To determine whether any discernible
influence was mediated by outliers, the MR Pleiotropy RESidual Sum
and Outlier (MR-PRESSO) 53 approach was applied. In brief, we selected
variants that were genome-wide significant (P<5×10 −8 ) for each
LVRWT trait, and remove variants in LD using default settings
(r 2 <0.001, kb=10) to generate independent variations. A P<0.05/5
traits=0.01 was considered statistically significant. All analyses were
performed using the R package TwoSampleMR.
### Polygenic risk score
WeusedtheC+T(clumping+thresholding)method 54 toconstructthe
polygenic risk score (PRS) of each LVRWT trait based on the effect
sizesderivedfromtheLVRWTGWASs.ThePRSwascalculatedthrough
a weighted model, as shown below:
PRS j =
X
i=1
β i G i,j
where β values (the log of odds ratio) is the summary statistic for the
effectivealleleandGisthenumberoftheeffectivealleleobserved.We
used variants with genome-wide significant (P<1×10 −5 ) and clumping
window (r 2 <0.1, kb=250) to derive PRS. We repeated this procedure
for each of the 12 traits, producing 12 PRSs. We categorized
participants into three genetic risk levels: low (lowest tertile),
intermediate (second tertile) and high (highest tertile).
Additional and detailed analyses are available in the Supplemen-
tary Methods.
### Reporting summary
Further information on research design is available in the Nature
Portfolio Reporting Summary linked to this article.


## 图例部分

Fig. 1 | Left ventricular wall thicknesses measurement with deep learning. A
complete and novel framework named Myocardial Segmentation and Measure-
ment Method (MSMM) for the quantification of myocardial wall thicknesses. a The
originalCMR imagesforendsystoleandenddiastole.bThesegmentationnetwork
architecture is based on the Deep Layer Aggregation (DLA). c Deep learning model
that has been trained segments the initial CMR images, producing pixel-by-pixel
output.Blue:leftventricularcavity,green:leftventricularmyocardium.dThepolar
representation of the segmentation contour is used to approximation an under-
lyingfunctionofdirectionanglemappedtodistancewiththekeypointsfortheleft
ventricular structure. e The function is applied to a set of uniformly spaced direc-
tion angles in the neighborhood of the target direction and take the average for a
robust quantification. IS inferoseptal, I inferior, IL inferolateral, AL anterolateral, A
anternor, AS anteroseptal.


Fig. 2 | Manhattan plots of genome-wide association studies results for 12
LVRWT phenotypes. Manhattan plots show the chromosomal position on the x-
axis and the −log10(P) on the y-axis for each LVRWT phenotype. The black dashed
line indicates the genome-wide significance threshold at P<5×10 −8 , while the red
dashed line represents the significance level after multiple corrections
(P<1.0×10 −8 ). Loci that contain variants with P<1×10 −8 were labeled with the
name of the nearest gene. P values are two sided based on the chi-squared test
statisticsinBOLT-LMMsoftware.LVRWTLVregionalwallthickness,ISinferoseptal,
I inferior, IL inferolateral, AL anterolateral, A anternor, AS anteroseptal.


Fig. 3 | Functional characterization for risk variants of 12 LVRWT traits. a Pie
chartrepresentstheproportionsforriskvariantsof12LVRWTtraitsannotatedwith
each functional category (intron region, gene upstream and downstream regions,
intergenic region, 3′-untranslated region (UTR), 5′-UTR and exon region).
b Enrichment analyses for risk variants of 12 LVRWT traits in each different func-
tionaltypeofvariants.Pvalueswerecalculatedbytwo-tailedFisher’sexacttestand
bars indicate 95% confidence intervals (CIs).c Enrichment analyses forrisk variants
of 12 LVRWT traits among epigenomic marks, such as H3K4 monomethylation
marks (H3K4me1), H3K4 trimethylation marks (H3K4me3), H3K27 acetylation
marks (H3K27ac), H3K36 trimethylation marks (H3K36 me3), H3K9 trimethylation
markers (H3K9me3) and transcriptional factor binding sites. P values were calcu-
lated by two-tailed Fisher’s exact test and bars indicate 95% CIs. d Enrichment
analyses for risk variants of 12 LVRWT traits among 11 CVDs risk loci. P value was
calculated by two-tailed fisher’s exact test. OR is depicted on the y axis and bars
indicate 95% CIs.


Fig. 4 | Pathway enrichment and tissue enrichment for susceptible genes
associated with LVRWT. a, b Pathway enrichment analyses of Gene Ontology
terms were performed at http://kobas.cbi.pku.edu.cn. Significantly enriched GO
terms (P<0.05, two-sided) were identified from the analyses of significant genes
forendsystole(a)andenddiastole(b).c,dTissueexpressionresultsfor54specific
tissuetypeswereobtainedfromGTExv8usingFUMA.ThePvalueswerecalculated
as two-sided. those bar that survived multiple correction (P<0.05/54)are denoted
with red. Tissue enrichment analysis was performed for inferoseptal (IS) at end
systole(ES)in(c)andenddiastole(ED)in(d).ISinferoseptal,ESendsystole,EDend
diastole.

Fig. 5 | SNP heritability and genetic correlations.a Genetic correlations between
12 LVRWT traits. Degree of correlation is indicated by color legend and circle area,
ranging from −1 to +1. SNP heritability is shown in the diagonal. We estimated the
single nucleotide polymorphism heritability (h 2 g ) and the genetic correlations
using BOLT-RELM and LDSC, respectively. Two-sided P values shown unadjusted
are estimated using LDSC for genetic correlation. Only significant correlations
(P<0.05) are shown. b Genetic correlations between 12 LVRWT traits and 10 car-
diacstructureandfunctiontraits.Degreeofcorrelationisindicatedbycolorlegend
and circle area, ranging from −1 to +1. Two-sided P values shown unadjusted are
estimated using LDSC for genetic correlation. Only significant correlations
(P<0.05) are shown. c Genetic correlation between the 12 LVRWT traits and 11
CVDs. Degree of correlation is indicated by color legend and circle area, ranging
from −1 to +1. Two-sided P values shown unadjusted are estimated using LDSC for
genetic correlation. Only significant correlations (P<0.05) are shown. LVRWT LV
regional wall thickness, CVDs cardiovascular diseases, IS inferoseptal, I inferior, IL
inferolateral, AL anterolateral, A anternor, AS anteroseptal, ES end systole, ED end
diastole, EH essential hypertension, PAH pulmonary arterial hypertension, DCM
dilated cardiomyopathies, HCM hypertrophic cardiomyopathy, CM cardiomyo-
pathy, HF heart failure, AF atrial fibrillation, AP angina pectoris, MI myocardial
infarction, CHID chronic ischemic heart disease, IS* ischemic stroke, HR heart rate,
SBP systolic blood pressure, DBP diastolic blood pressure, Lvesv left ventricular
end-systolic volume, SVi stroke volume (BSA-indexed), SV stroke volume, LVESVi
left ventricular end-systolic volume (BSA-indexed), LVEF left ventricular ejection
fraction, LVEDVi left ventricular end-diastolic volume (BSA-indexed), LVEDV left
ventricular end-diastolic volume.

Fig. 6 | Causal effects between LVRWT phenotypes and CVDs using Mendelian
randomization. The GWAS data sources used for Mendelian randomization are
detailed in Supplementary Data 2. Effect sizes are presented as ORs per standard
deviation increment in LVRWT in relation to the risk of CVDs. The horizontal bars
represent 95% confidence intervals (95% CIs), with color-coding indicating sig-
nificance levels: red denotes multiple correction for significance (P<0.05/55),
green signifies nominal significance (P<0.05), and faded gray indicates non-
significantcorrelations.FortwosampleMRanalyses,weusedMR-Eggerregression,
weighted median and mode-based estimations as sensitivity analyses, along with
the inverse-variance weighted technique as our major model. LVRWT LV regional
wall thickness, CVDs cardiovascular diseases, IS inferoseptal, I inferior, IL infer-
olateral, AL anterolateral, A anternor, AS anteroseptal, OR odds ratio, SD standard
deviation. The dot refers to each variant’s mean value of association estimate with
exposure and outcome, while the cross symbol represents SE.

Fig. 7 | Distribution of PRS and cumulative incidence of HCM stratified by PRS.
a,bDistributionofPRSforparticipantswiththin,mediumandthickLVRWT.PRSof
inferoseptal LVRWT end systole (a) and end diastole (b) yielded discrimination for
the LVRWTs. c,d Atotalof439,981individualsunrelatedtotheCMR cohort.Those
in the first tertiles of genetically predicted inferoseptal LVRWT are depicted in
green, the second tertiles are depicted in blue and the last tertiles are depicted in
red. The darker shades represent the central estimate of the cumulative incidence
(defined as 1-the Kaplan–Meier survival estimate).The lighter shades represent the
respective 95% CIs. The x axis depicts years since enrollment in the UKB; the y axis
depicts cumulative incidence of HCM. Strata based on genetic prediction of
inferoseptal LVRWT atend systole(c) and end diastole (d).Distribution of ES-IS (e)
andED-IS(f)PRSpercentilesforHCMcases(n=420)andcontrols(n=439,561).For
all box plots: central line of each box, median; top and bottom edges of each box,
first and third quartiles; whiskers extend 1.5× the interquartile range beyond box
edges. P values were calculated by a two-sided Student’s t test. Asterisk denotes
statistically significant differences *p<0.05; **p<0.01; ***p<0.001. PRS polygenic
risk score, HCM hypertrophic cardiomyopathy, LVRWT LV regional wall thickness,
ES end systole, ED end diastole, IS inferoseptal.

'''
任务描述： 请根据描述详细讲解Fig.1a的结果和图例描述（不要用比喻的方式）,并根据结果和图例描述讲解完成这个图例的目的,输出格式如下：

    结果描述：
    图例描述：
    关键结论:
    分析目的：


