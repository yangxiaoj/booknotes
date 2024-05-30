你是一个生物信息学术专家，请详细阅读三引号中的文本，然后完成以下任务。 '''

# 标题：Coordinated Cellular Neighborhoods Orchestrate Antitumoral Immunity at the Colorectal Cancer Invasive Front

## Summary:

Antitumoral immunity requires organized, spatially nuanced interactions between components of the im-
mune tumor microenvironment (iTME). Understanding this coordinated behavior in effective versus ineffec-
tive tumor control will advance immunotherapies. We re-engineered co-detection by indexing (CODEX) for
paraffin-embedded tissue microarrays, enabling simultaneous profiling of 140 tissue regions from 35
advanced-stage colorectal cancer (CRC) patients with 56 protein markers. We identified nine conserved,
distinct cellular neighborhoods (CNs)—a collection of components characteristic of the CRC iTME. Enrich-
ment of PD-1 + CD4 + T cells only within a granulocyte CN positively correlated with survival in a high-risk pa-
tient subset. Coupling of tumor and immune CNs, fragmentation of T cell and macrophage CNs, and disrup-
tion of inter-CN communication was associated with inferior outcomes. This study provides a framework for
interrogating how complex biological processes, such as antitumoralimmunity, occur through concertedac-
tions of cells and spatial domains.


## Introduction:

The immune tumor microenvironment (iTME) is a complex as-
sembly of tumor, immune, stromal, and extracellular compo-
nents. Organization of these components at the cellular and tis-
sue levels plays a crucial role in the effectiveness of antitumor
immunity (Binnewies et al., 2018). Technological and computa-
tional advances have allowed new spatial relationships to be
identified, but determining which of these are informative of tis-
sue behavior and, therefore, have the highest clinical utility re-
mains challenging.
Multiplexed imaging technologies allow capturing many pa-
rameters of single cells while preserving their spatial location
(Agasti et al., 2017; Angelo et al., 2014; Gerdes et al., 2013; Gie-
sen et al., 2014; Gut et al., 2018; Huang et al., 2013; Lin et al.,
2018; Moffitt et al., 2018; Saka et al., 2019; Schubert et al.,
2006; Wang et al., 2017b, 2018; Wei et al., 2017). We previously
introduced co-detection by indexing (CODEX), a technology
that uses DNA-conjugated antibodies and iterative polymerase
extensionwithfluorescentnucleotidesandchemicalfluorophore
cleavage to achieve high-parameter immunofluorescence imag-
ing of fresh-frozen tissue. Among other applications, we demon-
strated that the identity of cells could often be predicted simply
bytheirneighbors,implyingmutualinformationrelationshipsthat
link cell marker expression and tissue localization. In addition,
these neighbor relationships were predictive of disease progres-
sion in a murine model of autoimmunity (Goltsev et al., 2018).
To better study the iTME in cancer patients with long-term clin-
ical follow-up, including survival data, we re-engineered the
CODEX method to be compatible with formalin-fixed, paraffin-
embedded (FFPE) tissue and tissue microarrays (TMAs).
Focusing on the iTME, other investigators applying multi-
plexed imaging have explored cellular functional states, spatial
and functional interactions between multiple cell types, as well
as how these interactions are modulated by tissue context (Ali
et al., 2020; Arnol et al., 2019; Jackson et al., 2020; Keren
et al., 2018; Schapiro et al., 2017; Stoltzfus et al., 2019; Zhu
et al., 2018). We reasoned that viewing the tissue only with
respect to interacting cell types (CTs) limits the ability to capture
the tissue-level processes that emerge from such spatial relationships. Tissue biology is organized into at least two levels,
distinct tissue regions and the CTs of which they are composed;
therefore, in our representation of the tissue, we sought to reflect
coordination at both levels. By analogy, the iTME is like a city
composed of neighborhoods (e.g., industrial, residential, or agri-
cultural), which are regions where specific functions of the city
occur.Theseneighborhoods aredistinguishedbytheircomposi-
tion of buildings, activities, and people, but they exhibit behavior
of their own, such as industrial output or energy consumption. At
a more granular level, people (e.g., teachers, doctors, and con-
struction workers) play integral roles in the city’s function. The
same concept applies when studying tissue. Identifying these
different levels and integrating information between them allows
us to pose novel questions about the tissue’s behavior. How do
certain CTs perform specialized roles to accomplish specific tis-
sue processes? How do specific tissue regions interact with
each other? How do different types of tissues compare? We
developed experimental and computational methodologies to
address these questions. We then applied them to the iTME of
human colorectal cancer (CRC) because it has long been recog-
nized in CRC that distinct, histologically observed forms of its
spatial architecture are linked to prognosis. Because CRC is a
leading cause of cancer deaths in the Western world (Siegel
et al., 2018), it offered a compelling clinical question and an op-
portunity to determine whether higher-level abstractions of tis-
sue architecture in the iTME could allow inference of underlying
mechanisms driving outcomes.
Is there evidence that neighborhoods as described above are
functionally relevant in the CRC tissue context? One spatial
structure that could be interpreted as a neighborhood is the ter-
tiary lymphoid structure (TLS). The biological and clinical rele-
vance of TLSs has been demonstrated not only in CRC but
also in multiple other cancers (Binnewies et al., 2018; Cabrita
et al., 2020; Di Caro et al., 2014; Dieu-Nosjean et al., 2016; Gra-
ham and Appelman, 1990; Helmink et al., 2020; Petitprez et al.,
2020; Saute`s-Fridman et al., 2016). To study TLSs and addi-
tional, currently unknown neighborhoods that could affect the
behavior of the iTME in CRC, we selected two patient groups
from opposite ends of a spectrum of iTME architectures. One
group exhibited de novo formation of numerous TLSs at the tu-
mor invasive front—the ‘‘Crohn’s-like reaction’’ (CLR). The other
group was defined by the absence of TLSs and the presence of
diffuse inflammatory infiltration (DII). Overall survival of patients
with CLR is much longer than that of patients with DII, as re-
ported previously (Di Caro et al., 2014; Graham and Appelman,
1990). The presence of TLSs in CLR patients and their absence
in DII patients indicates that the differences in survival between
these patient groups are likely influenced by differences in their
antitumoral immune responses as opposed to only tumor-
intrinsic factors. We reasoned that comparing the iTME of CLR
and DII patients using highly multiplexed tissue imaging would
allow us to identify new neighborhoods beyond the TLS whose
behavior could be associated with effective or ineffective antitu-
moral immunity.
To maximize our ability to identify novel tissue behaviors in
these opposing phenotypes, we constructed TMAs that specif-
icallyrepresentedtheiTMEattheCRCinvasivefront.Weimaged
theseTMAswith56markersthatwouldrecapitulatecellularphe-
notypes established to be associated with antitumoral immunity
in solid cancers, such as different T cell and macrophage sub-
sets (Joyce and Fearon, 2015). We identified CTs in each patient
sample and identified cellular neighborhoods (CNs) as regions
with a characteristic local stoichiometry of CTs (Figure 1A.1).
Thus, a patient sample can be viewed simultaneously as a
collection of CTs and as a collection of CNs.
Inourmodel,aCNcanretainitsidentityevenwhentheindivid-
ual cells within it change (like a cell retains its identity even when
the molecules within it change). We would expect changes in
spatial regions corresponding to CTs and CNs to be correlated
(Figure 1A.2, left). Understanding the dynamic processes in the
iTME therefore requires understanding them from the view of
CTs, from the view of CNs, as well as how these two views are
coupled. In gene expression data, principal-component analysis
(PCA) decomposes variation in samples to reveal the organiza-
tion of genes into modules. We use tensor techniques to decom-
pose variation in samples to reveal organization from the view of
CTs, organization from the view of CNs, as well as how the orga-
nization from these two views is coupled (Figure 1A.2, right).
The functional states of cells can be identified by key markers
and are associated with patient outcomes (Hashimoto et al.,
2018). Therefore, the frequency of a given marker-positive cell
subset within a CN could be an indicator of its functional state.
Moreover, the functional state of a CN could be associated
with survival even when the frequency across the tissue of the
CT defining that functional state is not (Figure 1A.3).
If the functional state of one CT were correlated, across pa-
tients, with the functional state of another, one could infer that
something is mediating this correlation; i.e., these CTs ‘‘commu-
nicate.’’ThesameholdstrueforCNsandenablesinferenceofan
inter-CN communication network (Figure 1A.4). Alterations be-
tweenpatient groupsininter-CN communication couldreveal in-
sights into how the tumor modulates the iTME and possibilities
for therapeutic intervention.
Using this analytical framework, we identified 28 CTs and 9
CNs that recapitulated known tissue components, such as the
TLS and the tumor, as well as novel ones. Tensor decomposition
identified differences in the coupling of CTs and CNs between
patient groups and suggested that a granulocyte-enriched CN
could play a significant role in DII patients. Indeed, the frequency
of PD-1 + CD4 + T cells within this CN was correlated with survival
in DII patients whereas the overall frequency of these cells was
not. Furthermore, the tensor decomposition indicated that a
T cell-enriched CN is coupled to a macrophage-enriched CN in
DII patients but not in CLR patients. Investigating these CNs further, we found that the Ki-67 + CD8 + T cell density in the T cell-
enrichedCNwasanti-correlated withthefrequencyofregulatory
T (Treg) cells in the macrophage-enriched CN in DII but not CLR
patients. These findings suggest that CNs and their correlations
could play a functional role in the iTME. We further identified a
communication network of CNs based on the correlations in
the frequencies of functional T cell subsets within them.
Our experimental and analytical techniques provide a general-
izable framework for interrogating the spatial behavior of a given
cancer’s iTME. Applied to large patient cohorts, it could reveal
how tumors modulate the organization, functional states, and
intercommunication of CNs to evade antitumoral immunity.

## Results:

### Selection of Patient Samples by Classically Determined iTME Structures in CRC
The native immune infiltrates and associated histologic features
at the CRC invasive front exhibit a spectrum of iTMEs from CLR
withmanyTLSstoDIIwithnoTLSs.Fromadatabaseof715CRC
patients, we selected cohorts of 17 CLR and 18 DII patients and
constructed TMAs of the iTME at the tumor invasive front (Fig-
ures 1B and 1C). The two groups were matched with regards
to gender, age, cancer type, location, and stage (Figure 1D; Ta-
ble S1A). In line with previous reports, the overall survival of CLR
patients was significantly better than that of DII patients
(Figure 1E).
### FFPE-Optimized CODEX Enables Highly Multiplexed Fluorescence Microscopy of Archival Human Cancer Samples
We re-engineered and fully automated the CODEX platform to
use iterative annealing, imaging, and stripping of fluorescently
labeled DNA probes complementary to DNA barcodes on tis-
sue-bound antibodies. We further optimized CODEX for use in
FFPE tissue to study archival human samples (Figure 2A). We
performed extensive testing of the iterative imaging approach
and individual antibodies and validated our combined CODEX
antibodypanelbystainingandanalyzingamulti-tumorTMA(Fig-
ures 2B, S1 and S2; Tables S1B–S1E, Data S1 and S2A, and
STAR Methods). Expected antigen distribution patterns were
observed in all tissues analyzed, exemplified by normal spleen,
follicular lymphoma, hepatocellular carcinoma, gastric carci-
noma,breastinvasivelobularcarcinoma, andpleuraldiffuse ma-
lignant mesothelioma (Figure 2C). For example, spleen tissue
showed a normal distribution of red and white pulp (CD3,
CD20, CD68), presence of granulocytes (CD15), localization of
indoleamine 2,3-dioxygenase 1 (IDO-1) in red pulp macro-
phages, and prominent PD-L1 expression in splenic sinusoids
(CD31). Notably, we detected a strong and ubiquitous expres-
sion of the T cell checkpoint marker V domain Ig suppressor of
T cell activation (VISTA) in mesothelioma, which is confirmed
as a feature of mesothelioma in a recent integrative genomic
characterization study (Hmeljak et al., 2018). Collectively, these
data demonstrate that FFPE-optimized CODEX is suitable for
highly multiplexed single-cell marker visualization, quantification
and biomarker discovery in clinically relevant tissues.
### FFPE-CODEX Enables In Situ Identification and Quantification of Major Immune CT in the iTME of the CRC Invasive Front
At the CRC invasive front, the iTME is usually seen as leukocyte-
dense regions alternating with regions of sparse immune infiltra-
tion. InDIIpatients, TLSs(follicles)are absent inthe immuneinfil-
trate but abundant in tumors from CLR patients. We performed
56-marker CODEX on two specifically created high-precision
TMAs incorporating four representative leukocyte-dense iTME
regions from the tumor invasive front for each patient, resulting
in a total of 140 regions (Figures 3A, 3B, and S3; Data S2B
and S2C).
By unsupervised clustering using X-shift (Samusik et al., 2016)
followed by supervised cluster merging based on marker
expression profiles, tissue localization, and morphology, we
identified and validated 28 unique CT clusters. These included
18 immune cell clusters, 6 stromal and vasculature clusters, 2
mixed clusters, 1 tumor cell cluster, and 1 undefined cluster
(Data S3 and S4; STAR Methods). Supervised manual gating
and unsupervised X-shift clustering led to comparable results
for absolute numbers and frequencies of defined major immune
CTs (Data S5; Table S1F). For downstream analyses, we chose
the CTs identified using unsupervised clustering.
We visualized the CTs using Voronoi diagrams, merging clus-
ters to simplify visualization (Figure 3C; Data S6A). We quantified
each immune CT as a fraction of total immune cells on an overall
per-group and per-patient basis. The frequency of immune sub-
sets across all patients revealed CTs with high (i.e., macro-
phages, 34%), medium (i.e., CD4 + T cells, 15%; CD8 + T cells,
13%; B cells, 10%), and low frequencies (i.e., Treg cells, 2%;
natural killer [NK] cells, <1%; CD11c + dendritic cells [DCs],
<1%) (Figure 3D; Data S6B–S6F).
Differences in the composition of these immune cell clusters
were observed between CLR and DII patients. Most notably,
CLR patients had higher frequencies of B cells, whereas DII pa-
tients had higher frequencies of macrophages. Interestingly, the
frequencies of CD8 + T cell and Treg cell clusters were not signif-
icantly different between CLR and DII patients (Figure 3D; Data
S6E and S6F). No differences in the frequencies of tumor cell,
smoothmuscle,stroma,andvasculatureclusterswereobserved
(Data S6B–S6D).
We performed PCA to identify combinations of CTs driving
variation and assessed their prevalence across patient groups.
The first two principal components were more prevalent
in CLR patients than in DII patients (t test, p < 0.01 and p <
0.025, respectively; Figure 3E). The first principal component had a positive weight for cell populations that are found in a clas-
sically defined follicle (B cells, plasma cells, and CD4 + T cells)
(Figure S4A). Interestingly, in the second principal component,
non-immune and non-tumoral cell clusters that make up struc-
tural components, such as vessels and connective tissue, had
a positive weight (Figure 3F).
A CODEX image can be analyzed for the spatial coordinates of
each cell within the tissue. We computed pairwise cell-cell con-
tact frequencies and frequency-normalized contact likelihood
ratios (log-odds ratios) (Goltsev et al., 2018) for cell clusters in
both groups of patients. The most dominant pairwise cell-cell
contacts were homotypic (e.g., B cells with B cells; DCs with
DCs), and we did not observe significant differences in these
contacts between CLR and DII patients (Figure S4B). This sug-
gested that higher-order features of tissue architecture might
be required to distinguish patient groups.
### Characteristic CNs of the CRC iTME Are Conserved across Patient Groups
We reasoned that viewing patient samples in terms of spatial
structures formed by cells and not just as collections of single
cells would provide insights into the processes organizing the
iTME. The simplest possible extension to treating an entire pa-
tient sample as a homogeneous collection of single cells (i.e.,
viewing it in terms of its CT composition) was to view the tissue
in terms of CNs. We identified CNs as regions of the tissue with a
specific local density of various CTs. Many other, more compli-
cated local features could be used to identify CNs, but this might
be less biologically interpretable. For every cell in the tissue, its
10 nearest spatial neighbors, which we labeled its ‘‘window,’’
were identified (Figure 4A.1). The CT composition, with respect
to the 28 CTs, was determined per window (Figure 4A.2), and
windows were clustered (Figure 4A.3). The tissue was colored
with respect to CNs (Figure 4A.4).
CNs were identified by clustering data from both patient
groups together to maximize recognition of common CNs.
We found 10 distinct CNs in the CRC iTME that recapitulated
core tissue components, as validated on the original H&E-
stained sections and fluorescence images for both patient
groups (Figures 4B–4E; Data S2D–S2G). One of the 10 CNs
was comprised mainly of imaging artifacts and, therefore,
was removed from further analyses (data not shown). Except
for a CN corresponding to the TLS (follicle), the remaining
eight CNs were broadly present in CLR and DII patients.
When we applied this algorithm to each patient group sepa-
rately, the identified CNs were still comparable across patient
groups (Figure S4C), and the common CNs were therefore not
an artifact of the data-merging process. This led to the prelim-
inary conclusion that the two extremes of the CRC iTME spec-
trum, although visually distinct as a result of the presence of
TLS, shared underlying architectural components that could
be defined as CNs.
The nine CNs recapitulated structures that directly related
to components of the CRC iTME architecture as observed
in H&E-stained tissue sections. For example, CN-5 was en-
riched for B cells, CD4 + T cells, CD4 + CD45RO + T cells,
CD11c + DCs, and CD163 + macrophages and depleted of
all other CTs. When compared with H&E-stained images,
CN-5 nearly perfectly aligned with the TLS (follicle) (Figures
4B and 4C). Additionally, the analysis revealed previously
unappreciated substructure in the remaining non-follicular
leukocyte-dense tissue regions. Examples included T cell-en-
riched CN-1, macrophage-enriched CN-4, and granulocyte-
enriched CN-9.
The tumor itself was divided into two distinct CNs: CN-2,
mainly comprised of tumor cells (‘‘bulk tumor’’), and CN-6,
which contained tumor cells as well as CD11c + DCs, CD68 +
macrophages, T cell subsets, and other immune and non-im-
mune CTs (‘‘tumor boundary’’) (Figures 4B and 4D). In the
stroma, we discriminated three CNs: CN-3 was enriched in
immune cells, CN-7 was vascularized smooth muscle, and
CN-8 mainly consisted of smooth muscle cells (Figures 4B
and 4E). Voronoi maps of CNs aligned well with fluorescent
CODEX images and H&E images (Figures 4D and 4E; Data
S2D–S2G).
We assessed whether the frequencies of CNs differed be-
tween CRC patient groups. Except for CN-5 (follicle), which
was highly enriched in CLR patients, none of the other CN fre-
quencies differed significantly (Figures 4F and S4D). This indi-
cates that the CNs we identified were common across patient
groups and likely represent conserved tissue compartments of
the CRC iTME. This raises the question whether there are other
structures and relationships between these CNs that might
explain the differences between CLR and DII.
### Coupling of Tumor and Immune Components in DII PatientsAssociatedwithCouplingandFragmentationof T Cell and Macrophage CNs
The CNs we identified provided a different view of patient
samples than the CTs. We reasoned that the underlying pro-
grams shaping the iTME could be better understood from
the CT view and the CN view simultaneously. We therefore
considered, for every patient, the joint composition matrix of
CNs and CTs, removing data from CN-5 (the follicle) because
it was present only in CLR patients (Figures 5A.1 and 5A.2).
This matrix not only describes cellular localization at the tissue level (i.e., the probability that a randomly sampled cell of a
given type is in a given CN) but also takes into account the
abundance of CNs. The variation across patients’ joint CN-
CT compositions should therefore provide insight into how
the processes in the iTME differ between patient groups
from the CN and CT views simultaneously. Tensor techniques
achieve this by retaining the information that the joint CN-CT
composition for each patient is a 2D matrix and not a 1D vec-
tor; the collection of 2D matrices is a 3D ‘‘tensor.’’ Variants of
tensor decomposition have been applied previously to gene
expression data collected across different tissue types to
identify multi-tissue gene networks (Hore et al., 2016). We
therefore applied non-negative Tucker tensor decomposition
(Kim and Choi, 2007) to the tensor of patients’ joint CN-CT
compositions in each patient group separately (Figures 5A.3
and 5A.4). This technique identified a collection of ‘‘CN mod-
ules’’ and ‘‘CT modules’’ (from the view of CNs and CTs,
respectively) that could be coupled in different ways to form
‘‘tissue modules’’ (from the view of CTs and CNs
simultaneously).
CN modules and CT modules are not only combinations of
CNs and CTs, respectively, that we could infer to be co-regu-
lated (analogous to gene modules in gene expression data).
Instead, combinations of paired CN and CT modules can be
interpreted as tissue modules corresponding to programs
operating simultaneously at the CN level and CT level. The dif-
ferences in the decomposition between patient groups (i.e.,
with respect to which CNs formed CN modules, which CTs
formed CT modules, as well as how combinations of paired
CN and CT modules formed tissue modules) should therefore
reveal differences in the organization of the iTME to further
investigate in subsequent analyses. For a detailed explanation
and biological interpretation of the tensor decomposition
output, see Data S7.
We first describe, at a high level, how the decomposition re-
sults from our CRC data are represented. In each patient group,
6 CN modules, 6 CT modules, and 2 tissue modules were iden-
tified.Tissuemodules(Figures5Band5C,solidouterrectangles)
combined different pairs of CN and CT modules (Figures 5B and
5C,dashedinnerrectangles)interactingtodifferentextents,indi-
cated by the weight of the line (edge) connecting them. CN and
CT modules whose edges were below an empirically defined
threshold were not deemed to contribute to a given tissue mod-
ule and were greyed out.
The patient groups differed in the collection of CN modules,
collection of CT modules, as well as how these were combined
to form tissue modules. In CLR patients, the two tissue modules
corresponded to an immune compartment (Figure 5B, top) and a
separate tumor compartment (Figure 5B, bottom). In contrast, in
DII patients, there was a single compartment containing tumor
andimmunemodules(Figure5C,top)and,additionally,adistinct
granulocyte compartment (Figure 5C, bottom). This suggests
that, in DII patients, there is greater coupling between formation
of the tumor and the immune tissue compartments than in CLR
patients. Although the differences in patient groups are likely
due to the actions of both the immune system and the tumor,
the results suggested that, in DII patients, the tumor might inter-
fere with or regulate immune processes to a larger extent than in
CLR patients. Uniquely, this was not the case for those involving
the granulocyte compartment.
We noted other interesting differences between the two pa-
tient groups in CN modules and CT modules. In DII patients,
one CN module had a high weight for CN-1 (T cell enriched)
and CN-4 (macrophage enriched), with its corresponding CT
module having a high weight for T cells and macrophages (Fig-
ure 5C, row iii). In contrast, in CLR patients, no CN module had
a high weight for CN-1 and CN-4, and there was no CT module
with a high weight for T cells and macrophages (Figure 5B).
This suggested that there might be a common program driving
the spatial organization of macrophages and adaptive immune
cells into CN-1 (T cell enriched) and CN-4 (macrophage en-
riched) in DII patients, whereas in CLR patients, there could be
distinct programs driving formation of these CNs.
That these two CNs were part of the same CN module in DII
patients also suggested that these two modules might be more
interdigitated in DII patients than in CLR patients. We therefore
computed the number of cells in CN-1 that had a cell in CN-4 as
a nearest neighbor and vice versa. We divided this number by
the total number of cells in the appropriate CN, estimating the
level of their contact or spatial proximity. We found that DII pa-
tients had a significantly higher contact between CN-1 (T cell
enriched) and CN-4 (macrophage enriched) than CLR patients
(p = 0.046, Student’s t test; Figure S4E). Despite this increased
surface area of contact, CN-1 and CN-4 did not ‘‘merge’’ but
were still distinct CNs and were represented within both patient
groups (Figure S4C).
In DII patients, two CN modules had a high weight of CN-2
(bulk tumor): one alongside CN-6 (tumor boundary) and CN-1
(Tcellenriched) andonealongsideCN-6andCN-4(macrophage
enriched) (Figure 5C, top, rows v and vi). In contrast, in CLR pa-
tients, no CN modules contained a high weight for tumor CNs
and other CNs (Figure 5B). This suggests that the molecular pro-
grams driving recruitment of cells to the DII tumor neighbor-
hoods (CN-2 and CN-6) could also drive recruitment of cells to CN-1 (T cell enriched) and CN-4 (macrophage enriched). There-
fore, the interference by the tumor in the immune processes of
the DII iTME may restrict the spatial compartmentalization of
T cells and macrophages.
Taken together, the tensor decomposition suggested that
there are differences in the underlying programs that result in a
distinct spatial organization of the iTME in CLR and DII patients.
Moreover, it suggested that, in DII patients, there was increased
coupling between the tumor and immune processes specifically
associated with increased coupling and spatial contact between
T cell and macrophage CNs.
### Neighborhood-Specific Expression of Functional Markers on T Cell Subsets Suggests Altered T Cell Processes in the Bulk Tumor
Understanding the iTME requires appreciating cells not only in
terms of simple phenotypic descriptors but also in terms of their
functional states, and we would expect the same to be true for CNs. T cells exhibit diverse functional states in the iTME, often
indicated by their expression of functional markers. Because
the balance of these functional states is essential for a success-
ful antitumoral immune response (Wherry, 2011), we would
expectthattherelativeproportionsofTcellsexpressingdifferent
functionalmarkersareindicatorsofthefunctionalstateofagiven
CN that could be relevant for patient outcomes.
The CD4 + :CD8 + T cell ratio is often used as a simple measure
to determine the overall balance of T cell function in cancer,
providing prognostic information when measured in the tumor
and tumor-immune interface (Shah et al., 2011; Wang et al.,
2017a).The‘‘tumor’’andthe‘‘tumor-immuneinterface’’arelikely
composed of finer sub-structures that were not addressed in
previous studies. We therefore computed and visualized the fre-
quencies of CD4 + and CD8 + T cells in each CN for each patient
(Figure 6A).
We next assessed whether these frequencies or their ratios
within the tumor CNs (CN-2 and CN-6) were associated with
overall survival. We performed these tests only for DII patients
because there was insufficient mortality (only four deaths) in
the CLR patient group. The CD4 + T cell frequency and the
CD4 + :CD8 + T cell ratio in CN-6 were significant prognostic fac-
tors (Figure 6B). This suggested that T cell activity specifically
in CN-6 (tumor boundary) could be important in the antitumoral
immune response.
In addition to quantifying frequencies and ratios of T cell sub-
sets, CODEX visualization allowed simultaneous investigation of
cellularfunctionalstatesbasedonmeasuredlevelsofkeyactiva-
tion, co-stimulatory, and checkpoint molecules. We manually
gatedthe functionalmarkers PD-1, Ki-67(aproliferation marker),
and inducible costimulator (ICOS) on the T cell subsets (Figures
6C and S5). We then quantified the relative proportions of
marker-positive (PD-1 + , Ki-67 + , ICOS + ) T cell subsets across
the nine CNs, pooling cells from all patients (Figure 6D). These
functional markers were not included during identification of
CTs or CNs.
InCN-2(bulktumor),theproportionofTcellsexpressingatleast
one of these three markers was approximately twice as high as in
anyotherCN(Figure6D).Theextentofthisenrichmentintratumor-
ally,evenincomparisonwiththetumorboundary(CN-6),wasstrik-
ing. In addition to there being changes in the frequency of ‘‘func-
tional’’ CD4 + and CD8 + T cells and Treg cells (as indicated by
marker positivity) between CN-2 and other CNs, we would also
expect there to be differences in the specific markers expressed
by these marker-positive cells. For each of these subsets, and
within each patient, we computed the relative proportion of
ICOS + , Ki-67 + , and PD-1 + cells among marker-positive cells in
CN-1, CN-2, CN-4, and CN-6. We observed that the proportion
of marker-positive cells that were ICOS + was significantly higher
inCN-1,CN-4, andCN-6comparedwithCN-2(Figure6E).Thisin-
dicates that T cell subsets expressing the activation marker ICOS
are less frequent in the bulk tumor as a proportion of marker-pos-
itive cells. In contrast, we found that the frequency of Ki-67 + CD4 +
T cells was highest in the bulk tumor (Figure 6E, center panel). No
significant differences were observed for the PD-1 + subsets (Fig-
ure 6E, bottom row). These data point toward a change in the in-
flammatory milieu within the bulk tumor compared with the tumor
boundaryandotheriTMECNsandraisethequestionofwhichsig-
nals maintain this discrepant relationship.
### CN Functional States with Respect to T Cells Are Distinct between CLR and DII Patients and Are Correlated with Survival
If the biological processes related to antitumoral immunity co-
occurring in each CN are altered between patient groups, we
would expect to observe concurrent changes in the frequencies
of the relevant functional CTs therein. We first built two statistical
models to test whether we can classify patients as CLR versus
DII using frequencies of T cells and macrophages expressing
the functional markers PD-1, Ki-67, and ICOS. In the first model,
we used only the overall frequency of each CT across the non-
follicular CNs. In the second model, we used the frequencies of CTs in each of the non-follicular CNs (we refer to these in the
following as ‘‘CN-specific CT frequencies’’). Evaluating these
models across repeated holdouts, we observed that including
spatial information improved classification accuracy (Figure 6F).
Thus, the frequencies of CTs within certain compartments could
contain additional information distinguishing patient groups
beyond what is contained in their overall frequencies.
ThisbeggedthequestionofwhetherCN-specificCTfrequencies
are more different between patient groups than expected by the
differences in the overall frequencies of the corresponding CTs
(i.e.,whenwasaCT‘‘differentiallyenriched’’inagivenCNbetween
thepatientgroups?).Thiswouldbeexpectedwhenthereweredif-
ferences inthe functionalstate of a given CN and not justchanges
inoverallcellularcompositionoftheiTME.Therefore,foreachCN-
specificCTfrequency,weestimatedalinearmodelincludingasco-
variates patient group and overall frequency of the corresponding
CT and visualized the estimated effects of the patient group as a
heatmap. According to this model, a significant coefficient indi-
catesthatthegivenCTismoreenrichedinagivenCNinonegroup;
i.e.,theCN-specificCTfrequencyishigherinonegroupthanwhat
can be explained by changes in the overall frequency of that CT
(Figure 6G; STAR Methods).
AllCNsexceptCN-8 (smooth muscle)exhibited significant dif-
ferential enrichment of at least one functional cell subset be-
tween patient groups. In CLR patients, there was increased
enrichment of Ki-67 + CD8 + T cells in CN-1, Ki-67 + macrophages
in CN-2, and Ki-67 + Treg cells and Ki-67 + CD4 + T cells in CN-3
(Figure 6G, first 3 columns). In DII patients, there was increased
enrichment of Ki-67 + Treg cells in CN-4; ICOS + Treg cells, ICOS +
and Ki-67 + CD8 + T cells, and Ki-67 + macrophages in CN-6;
ICOS + Treg cells in CN-7; and PD-1 + and ICOS + CD4 + T cells
in CN-9 (Figure 6G, columns 4–8).
That there was differential enrichment of four CTs in CN-6
compared with only one in CN-2 suggested that changes in im-
mune activity in the tumor boundary CN could be implicated in
the impaired survival of DII patients (Figure 6G). In the tensor
decomposition, we observed increased coupling between CN-
1 (T cell enriched) and CN-4 (macrophage enriched) in DII pa-
tients. In addition, Ki-67 + CD8 + T cells were less enriched in
CN-1 and Ki-67 + Treg cells were more enriched in CN-4 in DII
compared with CLR patients (Figure 6H), and activated ICOS +
Treg cells were enriched in CN-6 in DII patients (Figure 6G).
These data suggest that, in DII patients, immunosuppressive ac-
tivity is increased in CN-4 and CN-6 and that, in CN-6, this could
oppose the cytotoxic activity from Ki-67 + and ICOS + CD8 +
T cells. In contrast, in CLR patients, there could be increased,
unopposed cytotoxic activity in CN-1.
Different CTs could have different roles in iTME function in
each patient group. We therefore computed a ‘‘CN functional
state alteration score’’ for each marker-positive CTs. We
comparedthe improvement in classification accuracy fora linear
model trainedto classifypatients bygroup whentheCN-specific
frequencies for that CT in the non-follicular CNs were included in
addition to its overall frequency across repeated holdouts (STAR
Methods). We found that Ki-67 + Treg cells were the most CN
functional state altering CT, followed by Ki-67 + macrophages
(Figure 6I). Within CD4 + T cells, the PD-1 + subset had the stron-
gest score for functional state alteration, suggesting a possible
role of this T cell subset in driving the differences in antitumoral
immune response between patient groups.
The granulocyte-enriched CN-9 stood out in the tensor
decomposition analysis as being uniquely present in a tissue
module distinct from the tumor in both patient groups. We also
observed that PD-1 + and ICOS + CD4 + T cells were more en-
riched in CN-9 in DII than in CLR patients (Figure 6G). In addition,
CD11c + DCs were present in CN-9 and were differentially en-
riched between patient groups (Figures 4B and S6A). These re-
sults suggest that certain processes occurring in CN-9, such
as antigen presentation, could play key roles in the antitumoral
immune response. Could the functional state of CN-9 contribute
to the antitumoral response?
Survival differences between CLR and DII patients are associ-
atedwiththepresenceofTLS(Figure1).However,prognosticators
ofsurvivalhavenotbeenestablishedpreviouslyinDIIpatients.We
assessed whether the frequencies of PD-1 + and ICOS + CD4 +
T cells in CN-9 were prognosticators of survival in DII patients.
Notably,thePD-1 + CD4 + TcellfrequencyinCN-9wasasignificant
prognostic factor for overall survival (p = 0.006, Cox proportional
hazards likelihood ratio test, 18 patients, 13 deaths) (Figures 6J
and 6K). Neither the overall frequency of PD-1 + CD4 + T cells in
the patient tissue nor the overall relative presence of CN-9 alone
was a significant prognosticator of outcome (data not shown).
The positive association of the frequency of PD-1 + CD4 + T cells
in CN-9 with overall survival is visible in Figure 6J, and this count
canbeusedtostratifypatients,asshowninFigure6K.Thesefind-
ings could imply that specific events occurring in CN-9, related to
production,maintenance, orfunctionof PD-1 + CD4 + T cells, could
contribute to the antitumoral immune response in CRC. Further-
more, although we could only compute the association with sur-
vival in DII patients, CN-9 is present in both groups, indicating its
relevancetoallCRCpatients.Theonlyotherfeaturestestedforas-
sociation with survival (excluding those in Figure 6B) were the fre-
quenciesofKi-67 + TregcellsinCN-4,ICOS + TregcellsinCN-6and
CN-7, as well as Ki-67 + CD68 + CD163 + macrophages in CN-6
because these, in addition to PD-1 + CD4 + T cells in CN-9, were
the five most predictive features in the classification model in Fig-
ure 6F (Figure S6B).
Taken together, these data indicate that the functional states
of CNs are different between CLR and DII patients and that CN
functional states are potentially functionally relevant for the anti-
tumoral immune response. Specifically, the functional state of a
granulocyte-enriched CN, indicated by its frequency of PD-
1 + CD4 + T cells, was associated with overall survival in DII pa-
tients. These results imply that some aspect of the T cell subset
activity harbored within the granulocyte-enriched CN could
contribute to positive immune activity.
### Correlated CN Functional States Suggest Immunosuppressive Inter-CN Communication and an Altered Communication Network in DII Patients
The tensor decomposition suggested that different CNs can re-
cruit similar combinations of CTs, which could be interpreted as
a form of communication between these CNs. We therefore ex-
pected that other forms of communication between CNs could
give rise to functional state correlations. These correlations
could be mediated by biological processes such as immune cell infiltration, antigen presentation, cytokine production, or
processes still to be determined.
Ki-67 + Treg cells were more enriched in CN-4 in DII patients,
and Ki-67 + CD8 + T cells were more enriched in CN-1 in CLR pa-
tients (Figures 6G and 6H). Given that Treg cells are capable of
suppressing CD8 + T cell activity (Chen et al., 2005), we deter-
mined whether the frequency of Treg cells in CN-4 was corre-
lated with the frequency of proliferating (Ki-67 + ) CD8 + T cells in
CN-1 in each patient group separately. A significant negative
correlation was observed only in DII patients (Figure 7A), sug-
gesting that a suppressive program involving Treg cells and
CD8 + T cells across CN-1 and CN-4 was only active in this pa-
tient group. Moreover, this finding suggested that there were
changes in inter-CN communication between patient groups.
Should there not also be differences in communication with
respect to multiple cell subsets and across other pairs of CNs?
We explicitly mapped the communication between different
CNs involving T cells by performing canonical correlation anal-
ysis (CCA; STAR Methods; Hardoon et al., 2004). CCA has
beenusedtoidentifycommonsignalsacrossmultipledatatypes
(for example, in multi-omics analyses; Witten and Tibshirani,
2009), and so we used it to find common signals across multiple
CNs with respect to their CN-specific CT frequencies. Briefly, for
any given pair of CNs, the frequencies of the CTs of interest are
computed within those CNs (Figure 7B.1). CCA then identifies
the two combinations of CN-specific CT frequency variations,
one from each CN, so that their correlation is maximized (Fig-
ure 7B.2). This maximal correlation is the canonical correlation
betweentwoCNs,whichweusedasaproxyforfunctionallyrele-
vant communication (Figure 7B.3). We applied CCA to the fre-
quencies of PD-1 + , Ki-67 + and ICOS + CD8 + T cells as well as
Ki-67 + Treg cells in each pair of CNs. In both patient groups,
we identified pairs of CNs that likely communicate by comparing
the observed canonical correlations with a permuted null distri-
bution. These CN communication relationships were visualized
as a graph of nodes corresponding to CNs and edges indicating
possible communication for each patient group (Figure 7C).
There were interesting differences between patient groups in
the communication networks of CNs with respect to functional
T cell subsets. In CLR and DII patients, CN-6 (tumor boundary)
played a central role. In CLR patients, CN-6 was strongly con-
nectedtoCN-1(Tcellenriched)andCN-2(bulktumor)andweakly
connectedtoCN-4(macrophageenriched)(Figure7C, leftgraph).
CN-4 and CN-1 were not directly connected to CN-2, suggesting
that functional T cell subsets in CN-1 and CN-4 could be commu-
nicatingwiththebulktumorviathetumorboundary.Incontrast,in
DII patients, CN-6 was not connected to CN-1 but strongly con-
nected to CN-4 and weakly connected to CN-2 (Figure 7C, right
graph). This is compatible with the communication between CN-
1 and CN-6 having been rerouted via CN-4 in DII patients, which,
asweshowed,hadimmunosuppressivecommunicationwithCN-
1 and increased enrichment of Ki67 + Treg cells (Figure 6G). The
fact that the edge between CN-6 (tumor boundary) and CN-2
(bulktumor)wasweakerinDIIpatientssuggeststhatcommunica-
tionwithrespecttoTcellsbetweenthetumorandtumorboundary
couldbedisrupted.Inaddition,onlyinDIIpatientsweretherecon-
nections between CN-9 (granulocyte enriched) and the tumor
CNs. Because the frequency of PD-1 + CD4 + T cells in CN-9 was
associated with survival in DII patients (Figures 6J and 6K), these
data suggest a possible role of CN-9 in T cell-mediated antitu-
moral responses. Finally, in CLR patients, CN-5 (follicle) was con-
nected to CN-1, CN-4, and CN-7 (vascularized smooth muscle),
indicating that the processes occurring in the follicle influence
T cell activity in multiple CNs.
In summary, in DII patients, correlation analysis allowed us to
observe a possible immunosuppressive program at play be-
tween CN-1 (T cell enriched) and CN-4 (macrophage enriched).
Moreover, the network of communication between CNs with
respect to functional T cell subsets was altered between patient
groups in a manner that suggested that this immunosuppressive
program could be affecting the phenotypes of functional T cell
subsets in the tumor boundary and bulk tumor. Thus, the
increased spatial contact between CN-1 and CN-4 as well as
the changes in organization of CNs and CTs observed in the
tensordecompositioncouldplayaroleintheimpairedoutcomes
of these patients.


## Methods

Detailed methods are provided in the online version of this paper
and include the following:

KEY RESOURCES TABLE

RESOURCE AVAILABILITY
- Lead Contact
- Materials Availa-ility
- Data and Code Availa-ility

EXPERIMENTAL MODEL AND SU-JECT DETAILS

METHOD DETAILS
- Construction of tissue microarrays
- -uffers and solutions
- Generation of CODEX DNA-conjugated anti-odies
- CODEX FFPE tissue staining and fixation
- Immunohistochemistry
- CODEX anti-ody screening, validation and titration
- CODEX multi-cycle reaction and image acquisition
- Figure creation

QUANTIFICATION AND STATISTICAL ANALYSIS

- Computational image processing
- Cleanup gating, unsupervised clustering and cluster
validation
- Manual gating of cell types and checkpoint-positive
cell su-sets
- Generation of Voronoi diagrams and contact matrices
- Details of statistical tests
- Computation of pairwise cell-cell contacts
- Neigh-orhood identification
- Non-negative Tucker tensor decomposition
- Differential enrichment analyses
- Classification of groups
- CN functional state alteration score
- Survival analysis
- Canonical correlation analysis
SUPPLEMENTAL INFORMATION
Supplemental Information can -e found online at https://doi.org/10.1016/j.
cell.2020.07.005.
ACKNOWLEDGMENTS
We thank Angelica Trejo, Han Chen, Kenyi Donoso, Nilanjan Mukherjee, Vishal
Venkataraaman, and Gustavo Vazquez (Stanford University) for excellent tech-
nical assistance and Sandrine Ruppen, Carmen Cardozo, and Dr. Jose´ Galva´n
(University of -ern) for help with creating the TMAs. We are grateful to Dr.
Anna Seigal (University of Oxford, UK) for helpful discussions regarding tensor
decomposition, Dr. Julian Schardt (University Hospital Bern, Switzerland) for
helping obtain patient clinical information, and Prof. Paul Bollyky (Stanford University) for providing the biotinylated VG1 hyaluronan detection reagent. We
thank the patients for consent to use their tissues for research. We would like
to extend our gratitude to Dr. Sizun Jiang and Dr. Xavier Rovira-Clave´ (Stanford
University) for critical comments on the manuscript.This work was supported by
the NIH (2U19AI057229-16, 5P01HL10879707, 5R01GM10983604,
5R33CA18365403, 5U01AI101984-07, 5UH2AR06767604, 5R01CA19665703,
5U54CA20997103, 5F99CA212231-02, 1F32CA233203-01, 5U01AI140498-02,
1U54HG010426-01, 5U19AI100627-07, 1R01HL120724-01A1, R33CA183692,
R01HL128173-04, 5P01AI131374-02, 5UG3DK114937-02, 1U19AI135976-01,
IDIQ17X149, 1U2CCA233238-01, and 1U2CCA233195-01); the DOD
(W81XWH-14-1-0180 and W81XWH-12-1-0591); the FDA
(HHSF223201610018C and DSTL/AGR/00980/01); Cancer Research UK
(C27165/A29073); the Bill and Melinda Gates Foundation (OPP1113682); the
Cancer Research Institute; the Parker Institute for Cancer Immunotherapy; the
KennethRaininFoundation(2018-575);theSiliconValleyCommunityFoundation
(2017-175329 and 2017-177799-5022); the Beckman Center for Molecular and
Genetic Medicine; Juno Therapeutics (122401); Pfizer (123214); Celgene
(133826and 134073); Vaxart (137364); and the Rachford & Carlotta A. Harris En-
dowed Chair (to G.P.N.). C.M.S. was supported by an advanced postdoctoral
mobility fellowship from the Swiss National Science Foundation
(P300PB_171189 and P400PM_183915) and an international award for research
in leukemia from the Lady Tata Memorial Trust (London, UK). D.J.P. was sup-
ported by an NIH T32 fellowship through the Stanford Department of Epithelial
Biology (AR007422), anNIH F32fellowship (CA233203), a Stanford Dean’s post-
doctoral fellowship, and theStanford Dermatology Department.S.S.B. wassup-
ported byaStanfordBio-XinterdisciplinarygraduatefellowshipandtheStanford
Bioengineering Department. G.L.B was supported by an NIH T32 fellowship
through the Stanford Molecular and Cellular Immunobiology Program(5-
T32AI007290-34).

## METHOD DETAILS
### Construction of tissue microarrays
FFPE tissue blocks were retrieved from the tissue archive at the Institute of Pathology, University of Bern, Switzerland. For the multi-
tumor TMA, 70 unique different tissues were selected (54 different cancers and non-malignant tumors as well as 16 normal tissues;
for details see Table S1E and Data S2A). Tumor and normal tissue regions were annotated on corresponding hematoxylin and eosin
(H&E)-stained sections by a board-certified surgical pathologist (C.M.S.). A next-generation TMA (ngTMA?) with 0.6 mm diameter
cores was assembled using a TMA Grand Master automated tissue microarrayer (3DHistech).
For the CRC study, two independent 70-core ngTMAs were created, containing four 0.6-mm cores per patient. TMA cores were
digitally annotated byL.N.,under thesupervision ofC.M.S and I.Z.,asfollows: CLR group, tworegions containing a tertiarylymphoid
structureandtwodiffuseimmuneinfiltrateregionsperpatient;DIIgroup,fourdiffuseimmuneinfiltrateregionsperpatient.TMAswere
sectioned at 3 mm thickness, stained with H&E, and digitized using a Pannoramic P250 digital slide scanner (3DHistech).
Square glass coverslips (Electron Microscopy Sciences) were pre-treated with Vectabond TM (Vector Labs) according to the man-
ufacturer’s instructions. Briefly, coverslips were immersed in 100% acetone for 5 min and then incubated in a mixture of 2.5 mL Vec-
tabond TM and 125 mL 100% acetone in a glass beaker for 30 min. Coverslips were washed in 100% acetone for 30 s and air-dried,
baked at 70 ? C for 1 h, and stored at room temperature. The 4-mm thick sections of the TMAs were mounted on Vectabond TM -treated
coverslips and stored in a coverslip storage box (Qintay) at 4 ? C in a vacuum desiccator (Thermo Fisher) containing drierite desiccant
(Thermo Fisher) until analysis.
### Buffers and solutions
Buffers and solutions were prepared, filtered sterile using 500 mL 0.2-mm pore size filters and stored at room temperature unless
otherwise specified. Staining solution 1 (S1): 5 mM EDTA (Sigma), 0.5% w/v bovine serum albumin (BSA, Sigma) and 0.02% w/v
NaN 3 (Sigma) in PBS (Thermo Fisher Scientific); storage at 4 ? C. Staining solution 2 (S2): 61 mM NaH 2 PO 4 ∙ 7 H 2 O (Sigma),
39 mM NaH 2 PO 4 (Sigma) and 250 mM NaCl (Sigma) in a 1:0.7 v/v solution of S1 and doubly-distilled H 2 O (ddH 2 O); final pH 6.8-
7.0. Staining solution 4 (S4): 0.5 M NaCl in S1. TE buffer: 10 mM Tris pH 8.0 (Teknova), 1 mM EDTA and 0.02% w/v NaN 3 in
ddH 2 O. Tris stock solution (for conjugation buffer), 50 mM, pH 7.2 (at room temperature) was prepared in ddH 2 O using Trizma
HCl and Trizma Base according to Sigma’s Trizma mixing table. Buffer C (for conjugation): 150mM NaCl, 2 mM Tris stock solution,
pH7.2,1mMEDTAand0.02%w/vNaN 3 inddH 2 O.CODEX2.0buffer(H2):150mMNaCl,10mMTrispH7.5(Teknova),10mMMgCl 2
∙ 6 H 2 O (Sigma), 0.1% w/v Triton TM X-100 (Sigma) and 0.02% w/v NaN 3 in ddH 2 O. Blocking reagent 1 (B1): 1 mg/ml mouse IgG
(Sigma) in S2. Blocking reagent 2 (B2): 1 mg/ml rat IgG (Sigma) in S2. Blocking reagent 3 (B3): Sheared salmon sperm DNA,
10 mg/ml in H 2 O (Thermo Fisher). Blocking component 4 (BC4): Mixture of 57 non-modified CODEX oligonucleotides (see Table
S1C) at a final concentration of 0.5 mM each in TE buffer. BS3 fixative solution (BS3): 200 mg/ml BS3 (Thermo Fisher) in DMSO
from a freshly opened ampoule (Sigma); stored at ?20 ? C in 15 mL aliquots. TCEP solution: 0.5 M TCEP (Sigma) in ddH 2 O, pH 7.0.
Rendering buffer: 20% DMSO (v/v) in H2 buffer. Stripping buffer: 80% DMSO (v/v) in H2 buffer.
### Generation of CODEX DNA-conjugated antibodies
All pipetting was performed using LTS filter tips (Rainin). Maleimide-modified short DNA oligonucleotides (for sequences, see Table
S1C) were purchased from TriLink. Maleimide groups were deprotected by heating in toluene at 90 ? C for 4h (with exchange of toluene
after 2h). Deprotected oligonucleotides were repeatedly washed in 100% ethanol, resuspended in buffer C, and aliquoted at 50 mg in
0.2 mL 8-strip tubes (E&K Scientific). Oligonucleotides were flash-frozen in liquid N 2 , lyophilized overnight in 900 mL Labconco Fast-
Freeze Flasks (Thermo Fisher) using a FreeZone? 4.5 Plus lyophilizer (Labconco) and stored until conjugation at ?20 ? C in an airtight
box containing desiccant. Conjugations were performed at a 2:1 weight/weight ratio of oligonucleotide to antibody, with at least
100 mg of antibody per reaction. All centrifugation steps were at 12,000 g for 8 min, unless otherwise specified. Purified, carrier-free
antibodies (for details on clones and manufacturers, see Table S1B) were concentrated on 50 kDa filters and sulfhydryl groups were activatedusingamixtureof2.5mMTCEPand2.5mMEDTAinPBS,pH7.0,for30minatroomtemperature.Afterwashingtheantibody
with buffer C, activated oligonucleotide was resuspended in buffer C containing NaCl at a final concentration of 400 mM. Oligonucle-
otide was thenadded tothe antibodyand incubated for2 h atroomtemperature.The conjugatedantibodywas washedbyresuspend-
ing and spinning down three times in PBS containing 900 mM NaCl. It was then eluted by centrifugation at 3,000 g for 2 min in PBS-
based antibody stabilizer (Thermo Fisher) containing 0.5 M NaCl, 5 mM EDTA, and 0.02% w/v NaN 3 (Sigma), and stored at 4 ? C.
### CODEX FFPE tissue staining and fixation
Coverslips were handled using Dumont coverslip forceps (Fine Science Tools). For deparaffinization, coverslips were baked at 70 ? C
for at least 1 h, followed by immersion in fresh xylene for 30 min. Sections were rehydrated in descending concentrations of ethanol
(100% twice, 95% twice, 80%, 70%, ddH 2 O twice; each step for 3 min). Heat-induced epitope retrieval (HIER) was performed in a
Lab Vision TM PT module (Thermo Fisher) using Dako target retrieval solution, pH 9 (Agilent) at 97 ? C for 10 min. After cooling to room
temperature for 30 min, coverslips were washed for 10 min in 1x TBS IHC wash buffer with Tween? 20 (Cell Marque). Tissues were
encircled using polyacrylamide gel (Bondic), and nonspecific binding was blocked for 1hat roomtemperature using100 mLof block-
ing buffer [S2 buffer containing B1 (1:20), B2 (1:20), B3 (1:20), and BC4 (1:15)]. For each coverslip, DNA-conjugated antibodies were
added to 50 mL of blocking buffer on a 50-kDa filter unit, concentrated byspinning at 12,000 g for 8 min, and resuspended in blocking
buffer to a final volume of 100 ml. This antibody cocktail was then added to the coverslip and staining was performed in a sealed hu-
midity chamber overnight at 4 ? C on a shaker. After staining, coverslips were washed for 4 min in S2 and fixed in S4 containing 1.6%
paraformaldehyde for 10 min, followed by three washes in PBS. Then, coverslips were incubated in 100% methanol on ice for 5 min,
followed bythreewashes inPBS.FreshBS3fixative wasprepared immediately beforefinal fixationbythawingand dilutingone15 mL
aliquot of BS3 in 1 mL PBS. Final fixation was performed at room temperature for 20 min, followed by three washes in PBS. There-
after, coverslips were stored in S4 in a 6-well plate at 4 ? C for up to two weeks, or further processed for imaging.
### Immunohistochemistry
Sections were cut to 4 mm thickness and placed on frosted histology glass slides (Thermo Fisher). H&E stained sections were ob-
tained from each FFPE block. Deparaffinization, rehydration, and HIER were performed on an ST4020 small linear stainer (Leica)
as described above. Nonspecific binding was blocked for 1 h at room temperature using 100 mL of serum-free protein block (Agilent).
Antibodies were diluted in 100 mL antibody diluent (Agilent), and sections were stained overnight in a sealed humidity chamber at 4 ? C
on a shaker. After staining, slides were washed for 10 min in 1x TBS IHC wash buffer with Tween? 20 (Cell Marque), and specimens
were covered with dual endogenous enzyme-blocking reagent (Agilent) for 5-10 min at room temperature, followed by washing for
10 min. Bound antibodies were then visualized using the HRP/liquid DAB+ substrate chromogen system (Agilent) according to the
manufacturer’s instructions. Sections were counterstained with hematoxylin, followed by dehydration, mounting, and imaging in
brightfield mode on a BZ-X710 inverted fluorescence microscope (Keyence).
CODEX antibody screening, validation and titration
Antibodies were first screened and validated in CODEX single-stainings on tonsil tissue or a multi-tumor TMA, with cross-validation
by manual IHC (Figures 2 and S1; Data S1; Table S1B). Briefly, after antibody staining and fixation, 100 nM of fluorescent DNA probe
was added to the tissue in rendering buffer, containing 0.7 mg/ml sheared salmon sperm DNA, and was incubated at room temper-
ature for 5-10 min, followed by washing with rendering buffer and S4 buffer. Coverslips were mounted onto glass slides with nail pol-
ish (SallyHansen)orCytoseal XYL(ThermoFisher), driedinthe darkand imagedon aBZ-X710 invertedfluorescence microscope.All
validation was performed by or under the supervision of a board-certified surgical pathologist (C.M.S.) and confirmed with online
databases (The Human Protein Atlas, Pathology Outlines) and the published literature.
### CODEX multi-cycle reaction and image acquisition
Coverslips were removed from S4, and the tissue was covered with a small piece of cling film. The non-tissue containing parts of the
coverslips were rinsed in ddH 2 O to remove salt residues and thoroughly dried using vacuum. Then, coverslips were mounted onto
custom-made CODEX acrylic plates (Bayview Plastic Solutions; blueprints available upon request) using coverslip mounting gaskets
(Qintay), creating a well in the acrylic plate above the tissue section for liquid storage and exchange. The cling film was removed, and
the tissue was stained with Hoechst nuclear stain at a dilution of 1:1000 in H2 buffer for 1 min, followed by three washes with H2
buffer. The CODEX acrylic plate was mounted onto a custom-designed plate holder (blueprints available upon request) and secured
ontothestageofaBZ-X710invertedfluorescencemicroscope.Fluorescentoligonucleotides(concentration:400nM)werealiquoted
in Corning TM black 96-well plates in 250 mL H2 buffer containing Hoechst nuclear stain (1:600) and 0.5 mg/ml sheared salmon sperm
DNA, according to the multi-cycle reaction panels. For details on the order of fluorescent oligonucleotides and microscope light
exposure times, see Table S1D. Black plates were sealed with aluminum sealing film (VWR Scientific) and kept at room temperature
during the multi-cycle reaction. The final concentration of fluorescent oligonucleotides in the tissue-containing imaging well corre-
sponded to 80 nM (1:5 dilution in rendering buffer).
Automated image acquisition and fluidics exchange were performed using an Akoya CODEX instrument and CODEX driver soft-
ware (Akoya Biosciences). During imaging, the tissue was kept in H2 buffer. Hybridization of the fluorescent oligonucleotides was
performed in rendering buffer. After imaging, fluorescent oligonucleotides were removed using stripping buffer. Overviews of the TMA were acquired manually using a CFI Plan Apo l 2x/0.10 objective (Nikon), and automated imaging was performed using a CFI
Plan Apo l 20x/0.75 objective (Nikon). For multi-cycle imaging of the TMA spots, the multipoint function of the BZ-X viewer software
(Keyence) was manually programmed to the center of each TMA spot and set to 17 Z stacks. Hoechst nuclear stain (1:3000 final con-
centration) was imaged in each cycle at an exposure time of 1/175 s. Biotinylated VG1 hyaluronan-detection reagent was produced
as previously described (Clark et al., 2011), used at a dilution of 1:500, and visualized in the last imaging cycle using streptavidin-PE
(1:2500final concentration). DRAQ5 nuclear stain(1:500 finalconcentration) wasadded andvisualized inthe lastimaging cycle. After
each multi-cycle reaction, H&E-stainings were performed according to standard pathology procedures, and tissues were reimaged
in brightfield mode.
A multi-cycle experiment performed the using multi-tumor TMA with 55 different antibodies, two nuclear markers and H&E took
about 36h to runand resultedin 3,630 tissue proteinexpression readouts (approximately 2,000 cells per0.6-mmdiameter core; total
of 7.26 3 10 6 single-cell protein readouts).
### Figure creation
PartsofFigures1B,2A,and3AwerecreatedusingtemplatesfromBiorender(https://biorender.com).PartsofFigures1,4,6,S4,and
S5,andDataS5andS6werecreatedandcorrespondingstatisticalanalyseswereperformedusingGraphPadPrism?5.0(GraphPad
Software).
## QUANTIFICATION AND STATISTICAL ANALYSIS
### Computational image processing
Raw TIFF image files were processed using the CODEX Toolkit uploader (Goltsev et al., 2018). Briefly, this software computationally
concatenates and drift-compensates the images using Hoechst nuclear stain as a reference, removes out-of-focus light using the
Microvolution deconvolution algorithm (Microvolution), subtracts the background (using blank imaging cycles without fluorescent
oligonucleotides), and creates hyperstacks of all fluorescence channels and imaging cycles of the imaged TMA spots. The following
settings in the CODEX uploader were used for the TMA experiments: Microscope: Keyence BZ-X710. Deconvolution: Microvolution.
Objective type: Air. Magnification (x):20. Numerical aperture: 0.75.Lateral resolution (nm/pixel): 377.442. Zpitch (nm): 1500. Number
of Z-slices: 17. Color mode: grayscale. Drift compensation channel index: 1. Drift compensation reference cycle: 1. Best focus chan-
nel:1.Bestfocuscycle:1.Numberofcycles/Range:1-23(multi-tumorTMA),1-24(CRCTMA).Tilingmode:snake.RegionsizeXand
Y: both 1. Tile overlap X and Y: both 0. H&E staining: yes (no in the case of background subtraction). Focusing fragment: no. Back-
ground subtraction: yes (no if H&E staining was co-processed). Use blind deconvolution: yes. Use bleach-minimizing cropping: no.
Processing only, export as TIFF.
After uploading, all spots of each TMA were stitched together into a single 10x7 spots file using the grid/collection stitching plugin
(Preibischetal.,2009)inImageJsoftware(Fiji, version2.0.0). Antibodystainingswerevisuallyassessedforeachchannelandcyclein
each spot, and seven-color overlay figures for selected markers were generated.
Hyperstacks from the CRC TMA spots were segmented based on DRAQ5 nuclear stain, pixel intensities were quantified, and
spatial fluorescence compensation was performed using the CODEX toolkit segmenter, with the following settings: Radius: 7.
Max. cutoff: 1.0. Min. cutoff: 0.07. Relative cutoff: 0.2. Cell size cutoff factor: 0.4. Nuclear stain channel: 4. Nuclear stain cycle:
23. Membrane stain channel: 1. Membrane stain cycle: ?1 (i.e., not used). Use membrane: false. Inner ring size: 1.0. Delaunay graph:
false. Anisotropic region growth: false. Comma-separated value (CSV) and flow cytometry standard (FCS) files were generated from
each TMA spot and used for further downstream analysis.
### Cleanup gating, unsupervised clustering and cluster validation
All 140 background-subtracted FCS files from both CRC TMAs were imported into CellEngine (https://cellengine.com). Gates were
tailored for each file individually in a blinded manner by two experts in flow and mass cytometry (C.M.S and D.R.M.). Nucleated cells
were positively identified, and artifacts were removed by gating on Hoechst1/DRAQ5 double-positive cells, followed by gating on
focused cells in the Z plane (Data S5). After cleanup gating, FCS files were re-exported and subsequently imported into VorteX clus-
tering software, where they were subjected to unsupervised X-shift clustering using an angular distance algorithm (Samusik et al.,
2016). The following data import settings were applied: Numerical transformation: none. Noise threshold: no. Feature rescaling:
none. Normalization: none. Merge all files into one dataset: yes. Clustering was based on all antibody markers except CD57,
CD71, CD194 (CCR4), CDX2, Collagen IV, MMP9 and MMP12. The following settings were used for clustering: Distance measure:
Angular distance. Clustering algorithm: X-shift (gradient assignment). Density estimate: N nearest neighbors (fast). Number of neigh-
bors for density estimate (K): From 150 to 5, steps 30. Number of neighbors: determine automatically.
The optimal cluster number was determined using the elbow point validation tool and was at K = 40, resulting in 143 clusters. Clus-
ters and corresponding data were exported as a CSV file and were manually verified and assigned to cell types by overlaying the
single cells from each cluster onto the stitched TMA images in ImageJ, based on the unique cluster identifiers and cellular X/Y po-
sition, using custom-made ImageJ scripts (available upon request). Clusters with similar morphological appearance in the tissue and
similar marker expression profiles were merged, and artifacts were removed, resulting in 28 final clusters. Minimal spanning trees of
the clusters were generated in VorteX, based on angular distance, and were exported for each marker (Data S3).

### Manual gating of cell types and checkpoint-positive cell subsets
After cleanup gating, the frequencies of major immune cell types (Data S5) and their expression of Ki-67 and checkpoint molecules
(Figure S5) were manually gated in a blinded manner for each TMA spot in CellEngine, and statistics were exported for further anal-
ysis.Forcheckpoint-positivecellsubsets,quantified checkpointexpression wascomparedto therawimageforeachspotand gates
were adjusted to best represent the raw image.
Generation of Voronoi diagrams and contact matrices
FCS files were exported from VorteX and subjected to a custom-made Java algorithm to create Voronoi diagrams and cell-to-cell
contact matrices (code available upon request).
Details of statistical tests
Inadditiontothemethodslistedbelow,thespecific detailsofstatisticaltests(valuesofn,pvalues,typeofstatisticaltest,definitionof
center etc.) are reported in the figure legends.
### Computation of pairwise cell-cell contacts
Direct neighbors of each cell were determined by Delaunay triangulation as implemented in the deldir R package, using the default
settings. From the original 28 cell clusters, two clusters were removed (undefined and tumor/immune cells), and the remaining clus-
ters were merged into 14 clusters (Figure S4B). To represent associations of cells from various clusters, likelihood ratios or relative
frequencies were calculated between the various clusters for each group of patients, according to the following formulas:
Likelihood ratios:

$$
\frac{N i j * N t}{N i * N j}
$$

Relative frequencies:
$$
\frac{N i j}{N i}
$$

where
Nij is the number of edges between cells in cluster 1 and cluster 2
Nt is the total number of edges, 
$$
\sum_{i, j} N i j
$$

$$
N i \text { is }=\sum_j N i j
$$

$$
N j \text { is }=\sum_i N i j
$$


Log 2 ratios of these metrics for CLR and DII patients were generated from the resulting matrices. A heatmap of the resulting values
was plotted using the Heatmap function from the ComplexHeatmap R package after removing contacts between clusters where the
number of unique adjacent cells was < 100 in both patient groups.
### Neighborhood identification
For each of the 258,385 cells across these tissues across all spots and patient groups, a ‘window’ was captured consisting of the 10
nearest neighboring cells (including the center cell) as measured by Euclidean distance between X/Y coordinates. These windows
were then clustered by their composition with respect to the 29 cell types that had previously been identified by X-shift clustering
and supervised annotation and merging (Data S6). Of these, 28 cell clusters had been assigned to biological cell types and one to
imaging artifacts, such as tissue folds and autofluorescent precipitations. This latter was included to identify poor quality regions
of the image. Specifically, each window was converted to a vector of length 29 containing the frequency of each of the 29 cell types
among the 10 neighbors, and the windows were subsequently clustered using Python’s scikit-learn implementation of MiniBatchK-
Means with k = 10. Each cell was then allocated to the CN that its surrounding window was. To validate the CN assignment, these
allocations were overlaid on the original tissue H&E-stained and fluorescent images. During this process, the CN cluster that con-
tained the imaging artifacts (cellular cluster 29) was removed.
### Non-negative Tucker tensor decomposition
ThetensorofCN-celltypedistributionsforeachpatient,withdimensionspatientsxcelltypesxCNs,wasproducedbycomputingthe
frequency of each cell type in each CN in the non-follicular compartments (i.e., all CNs except CN-5). This tensor was split along
the patient direction by patient group (CLR and DII). Non-negative Tucker decomposition as implemented in the Tensorly Python package was applied to each tensor (Kossaifi et al., 2019). The ranks in each dimension (2,6,6) were selected by a visual elbow point
method assessing the decomposition loss (Figure S6C). Several random-starts were utilized to ensure stability.
The cell type modules correspond to the factors in cell-type space. The CN modules correspond to the factors in CN space. The
interactions comprising a tissue module correspond to each 6x6 slice of the 2x6x6 core tensor.
### Differential enrichment analyses
Linear models 
$$
Y_{n, c}=\beta_0+\beta_1 X+\beta_3 Y_c+\mathrm{e}
$$
were estimated, where Y c is the log overall frequency of cell type c, X is an indicator variable
forpatientgroup,Y n,c isthelogfrequencyofcelltypecinCNn,b i arecoefficients, andeismeanzeroGaussiannoise.Apseudocount
of 1 $`e^-3 `$ was added prior to taking logs. These were estimated using the statsmodels Python package (Seabold and Perktold, 2010).
The coefficient estimates and p values for b 1 were extracted and visualized.
Classification of groups
Classification modelswere L1regularized logistic regressionmodels, fitusingtheglmnetRpackage (Friedman etal.,2010). Features
were computed under the transformation 
$$
x->\log \left(1 e^{-3}+x\right)
$$ 
and z-normalized across the dataset prior to inclusion in any models.
Repeated hold-out (RHO) was utilized to estimate prediction error, which utilized 10 training samples from each patient group. The
L1regularizationparameterwaschosenforeachsampledtrain-testsplitbycross-validationonthesampledtrainingset,andamodel
using this regularization parameter was fit on the sampled training set. The model was evaluated on the sampled test set, and ROC
curves were estimated on the test set (of size 15). This was repeated 1000 times. The feature importance was computed as the z-
score of the absolute value of the coefficient across resampling, as reported in (Laurin et al., 2016).
### CN functional state alteration score
TheCNfunctionalstatealterationscorewascomputedforeachcelltypeindividually.Specifically,foreachcelltype,theclassification
performance (AUC) was estimated using 200 RHO samples for two models classifying patients as CLR vs. DII. The first model
included as features the overall frequency of that cell type. The second model included as features the overall frequency as well
as the CN-specific cell type frequencies of that cell type in all CNs except CN-5. Each cell type had a different accuracy of classifi-
cation with respect to these two models. The CN functional state alteration score was defined as the improvement in classification
between the two models. Specifically, the negative log (base 10) of the p value of a one-sided t test for a greater mean in the AUC
across RHO samples between the second and first model was used to quantitate them. Since this entire procedure contained
randomness, it was repeated 10 times to estimate the variability across the dataset of the CN functional state alteration score.
### Survival analysis
We tested the log (1e -3 + frequency in CN-9) for each of PD-1 + CD4 + and ICOS + CD4 + T cells individually, in Cox proportional hazards
regression models, estimated using the survival R package (Therneau, 2015). The p value displayed was from the Cox regression
model, and the Kaplan-Meier curve displayed was computed using the optimal split of the samples along the PD-1 + CD4 + T cell fre-
quency in CN-9 variable. The partial residual plot in Figure 6J was created using the visreg R package (Breheny and Burchett, 2013).
The proportional hazards assumption was supported by non-significant relationships between scaled Schoenfeld residuals and time
as computed using the cox.zph function of the survival R package.
### Canonical correlation analysis
For each CN, the log CN-specific cell type frequency of each of ICOS + , Ki-67 + , and PD-1 + and CD8 + T cells as well as Ki-67 + Tregs
was computed. For each pair of CNs, estimated canonical directions for the frequencies of these cells in each CN was estimated
using the scikit-learn Python package (Pedregosa et al., 2011). For each pair of CNs, patients with no cells assigned to either CN
were not included in the analysis. The correlation of the projections along these canonical directions was compared to a permutation
distribution, corresponding to 5000 random permutations of the data. The permutation p value, i.e., the percentage of permutations
whose estimated canonical correlation exceeded the observed one, was interpreted as the strength of communication.




## 图例部分

Figure 1. CRC Study Cohort
(A) Conceptual framework.
(B) Exclusion criteria: pre-operative therapy, pathological tumor, nodes, metastasis (pTNM) score 0–2 or unknown, absent immune infiltration (Klintrup-Ma¨kinen
[K-M] score 0), insufficient material for Graham-Appelman (G-A) scoring, a combination of low immune infiltration (K-M 1) and absent follicles (G-A 0) or few
follicles (G-A 1).
(C) Spectrum of iTME architectures in 134 advanced-stage CRC patients.
(D) Characteristics of patients in the CRC study cohort.
(E) Kaplan-Meier survival curve of the CRC study cohort (p determined with a log-rank test).
See also Table S1A and STAR Methods.

Figure 2. CODEX Workflow and Antibody Validation
(A) CODEX workflow.
(B) Seven-color overview of multi-tumor TMA, imaged using a 56-marker CODEX panel.
(C) Higher-magnification seven-color images of select tissue cores.
See also Figures S1 and S2, Data S1 and S2A, and Tables S1B–S1E.


Figure 3. Spatial Composition of Immune Infiltrates in CRC
(A) Schematic of CRC TMA assembly. Blue dots represent follicles/TLSs.
(B) Representative TMA cores for CLR and DII patients depicted as seven-color images.
(C) Voronoi diagrams of clustered CTs, merged to reduce complexity.
(D) The eight immune clusters (n = 132,437 cells) and their frequencies in all CRC patients (top) and separated into CLR (n = 57,894 cells) and DII patients (n =
74,543 cells) (bottom).
(E) PCA of CT abundances in CLR versus DII patients.
(F) CT loadings in principal component 2.
See also Figures S3, S4A, and S4B, Data S2B, S2C, and S3–S6, and Table S1F.

Figure 4. Characteristic CNs of the CRC iTME
(A) Schematic of CN identification.
(B)Identification of 9distinctCNs basedon the28 original CTs and their respective frequencies(enrichment score) within each CN(pooleddata from both patient
groups).
(C) Representative Voronoi diagrams of CNs for CLR and DII patients. Insets, H&E images.
(Dand E)Representative Voronoidiagramsof CNswereselectedtoshowthenine different CNs(leftpanels)andcorresponding seven-color images(right panels)
in patient 33 (D) and 19 (E). Insets, H&E images.
(F) Frequencies of CNs in CLR versus DII patients. Each point represents the mean CN frequency from four TMA cores per patient, and horizontal lines represent
the means across patients (***p < 0.001, Student’s t test).
See also Figures S4C and S4D and Data S2D–S2G.


Figure 5. Tensor Decomposition Suggests Differences in Organization of the iTME
(A) Schematic of the tensor decomposition analysis.
(B) Decomposition results for CLR patients. Tissue modules (interacting pairs of CN modules and CT modules) correspond to an ‘‘immune compartment’’ (top)
and a ‘‘tumor compartment’’ (bottom).
(C)DecompositionresultsforDIIpatients.Tissuemodules correspondtoan‘‘immuneandtumorcompartment’’(top)anda‘‘granulocyte compartment’’(bottom).
See also Figure S6C and Data S7.

Figure 6. CN Functional States Are Indicators of Antitumoral Immunity
(A) Example Voronoi diagrams of TMA spots, colored by CN, with CD4 + (left) and CD8 + T cells (right) overlaid in each CN as points of the corresponding CN color.
(B) Table of Cox proportional hazards regression results for T cell frequencies in the indicated CNs. Each CN-specific frequency was tested individually in a
distinct model (DII patients: n = 18, 13 deaths).
(C) Example staining for ICOS, Ki-67, and PD-1 on different T cell subsets.
(D) Relative proportions of CD4 + (FOXP3 ? ) T cells, CD8 + T cells, and Treg cells positive for at least one of the functional markers (ICOS, Ki-67, and PD-1) in each
CN. Pooled data from all patients are shown (cell numbers: CN-1, 17,822; CN-2, 735; CN-3, 4,031; CN-4, 11,753; CN-5, 4,695; CN-6, 2,681; CN-7, 4,504; CN-8,
1,368; CN-9, 2,884).
(E) Violin plots of CN-specific CT frequencies of marker-positive CD4 + T cells, CD8 + T cells, and Treg cells in CN-1, CN-2, CN-4, and CN-6. Asterisks indicate
significant differences in the CN-specific CT frequency below compared with the frequency in CN-2 (bulk tumor), tested across patients (*p < 0.05, **p < 0.01,
***p < 0.001, Student’s t test).
(F) Receiver operating characteristic curves comparing the performance of L1-regularized logistic regression classifiers(CN-specificCT frequency versusoverall
frequency of marker-positive cells) over repeated holdout samples to classify patients by group.
(G) Heatmap of estimated differential enrichment coefficients (*p < 0.05, not adjusted for multiple tests). A positive coefficient (red) indicates that the corre-
sponding CT is more enriched in DII patients in the given CN.
(H) Estimated enrichment of Ki-67 + CD8 + T cells in CN-1 and Ki-67 + Treg cells in CN-4 for each patient. Horizontal lines represent the means across patients.
(I) Estimated CN functional state alteration score for each CT. Variation corresponds to the distribution of the score across 10 resampling iterations.
(J) Partial residual plot of the log frequency of PD-1 + CD4 + T cells in CN-9 versus the estimated log hazard ratio with respect to overall survival in DII patients (p =
0.006; n = 18, 13 deaths; Cox proportional hazards regression). A pseudocount of 0.001 was added to the frequency for all patients when logarithms were
computed.
(K) Kaplan-Meier curves for overall survival in DII patients corresponding to the best splitting of DII patients into two groups along the CN-9-specific frequency of
PD-1 + CD4 + T cells.
See also Figures S5, S6A, and S6B, and STAR Methods.


Figure 7. Altered Inter-CN Communication Favors Immunosuppression in DII Patients
(A) Correlation of the frequency of Ki-67 + CD8 + T cells in CN-1 (T cell enriched) and the frequency of Tregs in CN-4 (macrophage enriched) in each patient group.
Spearman rank and Pearson correlation coefficients and p values are shown.
(B) Schematic of the canonical correlation analysis (CCA).
(C) The canonical correlation with respect to the frequencies of ICOS + , Ki-67 + , and PD-1 + CD8 + T cells as well as Ki-67 + Treg cells in each pair of CNs was
compared with a permuted null distribution within each patient group. Pairs of CNs whose observed canonical correlation with respect to these CTs was higher
than 90% of permutations were connected by edges and visualized as a graph.
(D) Conceptual framework for describing CRC iTME spatial behavior.
(E) Model of differences in the iTME between CLR and DII patients with respect to CN organization (Figure 5), cellular function (Figure 6), and inter-CN
communication (Figures 7A–7C).



Figure S1. Validation and Titration of the CODEX Antibody Panel, Related to Figure 2, Table S1, and STAR Methods
FFPE tonsil tissue was stained with a cocktail of 55 different DNA-conjugated antibodies, and a multi-cycle experiment was performed followed by H&E staining.
(A) Images of a single tissue region at the interface of a follicle (top left in each image) and epithelium (bottom right in each image) are depicted in false gray color
foreachantibody;H&Estainingisalsoshown.Scalebar,100mm.(B)Topleftpanel:Overviewofthetonsilsectioninafive-coloroverlayimagewithHoechst(blue;
nuclei), CD31 (yellow;vasculature), CD3 (red;T cells), CD20 (green; Bcells), and pan-cytokeratin (CK, white; epithelium). Inset: H&E staining.Scale bars, 200 mm.
Regions 1-4 are indicated by white rectangles. Region 1: Six-color overlay and single-marker images of a follicle with CD57 (red), ICOS (also known as CD278,
green), PD-1 (also known as CD279, blue), VISTA (cyan), LAG-3 (also known as CD223, white), and Ki-67 (magenta). Scale bars, 40 mm. Region 2: Six-color
overlayandsingle-markerimagesofaninflamedepithelial-lymphoidparenchymainterfacewithCD15(blue),CD68(red),CD163(cyan),CD56(white),PD-L1(also
known as CD274, green), and EGFR (magenta). Scale bars, 40 mm. Region 3: Six-color overlay and single-marker images of a follicle with CD4 (red), CD8 (green),
CD25 (yellow), CD45RA (blue), CD45RO (cyan), and FOXP3 (magenta). A CD4 + CD25 hi FOXP3 + CD45RO + regulatory T cell is indicated by the white arrow. Scale
bars, 40 mm and 20 mm, respectively. Region 4: Six-color and two-color overlay images of an epithelial region with Pdpn (green), CD34 (yellow), EMA (also known
as MUC-1, white), CD45 (blue), vimentin (cyan), and SMA (magenta). Scale bars, 40 mm. Brightness and contrast adjusted.


Figure S2. Signal and Tissue Integrity and Autofluorescence during the CODEX Multi-Cycle Experiment, Related to Figure 2, Table S1, and
STAR Methods
(A) FFPE tonsil tissue was stained with a cocktail of nine different DNA-conjugated antibodies. Antibodieswere repeatedly rendered visible using complementary
fluorescent oligonucleotides in 33 cycles with blank cycles to measure autofluorescence (no fluorescent oligonucleotides added) at the beginning (cycle 1), after
eachround of nine antibody rendering (cycles 11 and 21), and at the end (cycles 31, 32 and 33). The microscopelight exposuretimes were kept constant for each
antibody in each cycle. Hoechst nuclear stain was used as a reference marker. (B) Example images of nuclear marker Ki-67-Alexa488 and membrane markers
CD20-ATTO550 and CD3-Alexa647 in cycles 4, and 20 are shown. Images are representative of cycles and nuclear and membrane markers that are not shown.
Scale bar, 20 mm. Brightness and contrast adjusted. (C) Comparison of fluorescence intensity profiles from cycles 4 and 20, as measured by ImageJ software on
the yellow lines in panel B. (D-I) Cells were segmented using the CODEX toolkit and clustered using X-shift (VorteX). (D) Mean marker expression for CD45
(ATTO550), CD20 (ATTO550), and CD3 (Alexa647) on lymphocytes (combined CD20 + cells and CD3 + cells). (E) Mean marker expression for Na-K-ATPase
(Alexa488) and pan-cytokeratin (ATTO550) on epithelial cells (pan-cytokeratin + cells). (F) Mean marker expression for Ki-67 (Alexa488) and CD45 (ATTO550) on
proliferating cells (Ki-67 + cells). (G) Mean marker expression for HLA-DR (Alexa488) and CD45 (ATTO550) on antigen-presenting cells (HLA-DR + cells). For
lymphocytes, epithelial cells, and proliferating cells, 1500 cells were sampled; for antigen presenting cells, > 250 cells were sampled. (H) Mean autofluorescence
levels on all cells combined measured in each channel in blank cycles 1, 11, 21 and 31 (no fluorescent DNA probes added). (I) Mean expression of the nuclear
marker Hoechst per cell in cycle 20 versus cycle 1. (J) Representative image of H&E staining performed after the last blank cycle 33.


Figure S3. CRC CODEX Antibody Panel, Related to Figure 3, Table S1, and STAR Methods
Each marker of the CRC CODEX panel is depicted individually for one representative TMA spot (spot 36 of TMA 1; patient 18). CD30 and MMP12 were not
detectable in any of the spots in either TMA, and are therefore not depicted. H&E and Hoechst stainings are shown for morphological reference. Scale bar,
200 mm. Brightness and contrast adjusted.


Figure S4. Pairwise Cell-Cell Contacts and CNs in Both Patient Groups, Related to Figure 4
(A) PCA correlating combinations of cell-type abundances in CLR versus DII patients. Cell-type loading in principal component 1 is shown. (B) Heatmap of
likelihood ratios of direct cell-cell contacts for 14 selected clusters is shown for clusters with at least 100 unique interacting cells. Gray boxes indicate less than
100 unique interacting cells; these data were omitted. Pooled data from all TMA cores are shown. (C) Both CLR and DII patient groups were clustered separately.
CNs were annotated manually. CN-0 corresponds to the imaging artifacts cluster; this cluster was omitted from the analysis shown in Figure 4B. Neighborhoods
that did not have matching counterparts in the analysis of the combined groups are labeled ‘‘not defined.’’ (D) Frequencies of each CN from Figure 4B in each
patient are shown. Frequencies are z scored by column to highlight major differences between CLR patients (blue) and DII patients (orange). (E) The contacts
between CN 1 (T cell-enriched) and CN 4 (macrophage-enriched) were computed (see Methods) and are displayed as ‘‘CN mixing’’ by patient group. For each
patient, the mean mixing score of four TMA cores is shown (*p < 0.05, Student’s t test).


Figure S5. Gating Strategy for Analysis of Checkpoint Molecule Expression on T Cells and Macrophage Populations, Related to Figure 6
(A) Representative dot plots from CellEngine are shown for each marker and population. (B) Heatmap of marker-positive cell populations per patient. (C) Fre-
quencies of marker-positive cell populations per patient. Data are mean values from four biological replicates (TMA cores) per patient (*p < 0.05, **p < 0.01,
Student’s t test).


Figure S6. Heatmap of Estimated Differential Enrichment Coefficients, Feature Importance for the Classification Model, and Elbow Points
for Tucker Tensor Decomposition, Related to Figure 6 and STAR Methods
(A) Heatmap of estimated differential enrichment coefficients for cell types not shown in Figure 6G. Asterisks indicate CNs and cell types with a regression p
value < 0.05 (not adjusted for multiple tests). A positive coefficient (red) indicates that the corresponding cell type is more enriched in DII patients than in CLR
patients inthe given CN.(B)Featureimportance for classification model. Bar plotof absolutecoefficient z-scores for CN-specific cell type frequencies,estimated
from a model classifying patient groups using iterative resampling, as described in Figure 6F. The five CN-specific cell type frequencies with a coefficient
importance of 0.3 or higher (left to red dotted line) were considered for assessment with respect to survival in DII patients. (C) Elbow points for Tucker tensor
decomposition. Tensor decomposition loss for choices of rank in patient space, CN space, and cell-type space used for selection of decomposition rank in each
patient group. Blue lines, one tissue module; red lines, two tissue modules. The elbow point was found at 6 CN modules and cell type modules (red line).





'''
任务描述： 请根据描述详细讲解Fig.1a的结果和图例描述（不要用比喻的方式）,并根据结果和图例描述讲解完成这个图例的目的,输出格式如下：

    结果描述：
    图例描述：
    关键结论:
    分析目的：
