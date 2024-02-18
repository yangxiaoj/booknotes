# Organization of the human intestine at single-cell resolution

John W. Hickey, Winston R. Becker, Stephanie A. Nevins, Aaron Horning, Almudena Espin Perez, Chenchen Zhu, Bokai Zhu, Bei Wei, Roxanne Chiu, Derek C. Chen, Daniel L. Cotter, Edward D. Esplin, Annika K. Weimer, Chiara Caraccio, Vishal Venkataraaman, Christian M. Schürch, Sarah Black, Maria Brbić, Kaidi Cao, Shuxiao Chen, Weiruo Zhang, Emma Monte, Nancy R. Zhang, Zongming Ma, …Michael Snyder Show authors

Nature volume 619, pages572–584 (2023)Cite this article

64k Accesses

16 Citations

321 Altmetric

Metricsdetails

## Abstract
The intestine is a complex organ that promotes digestion, extracts nutrients, participates in immune surveillance, maintains critical symbiotic relationships with microbiota and affects overall health1. The intesting has a length of over nine metres, along which there are differences in structure and function2. The localization of individual cell types, cell type development trajectories and detailed cell transcriptional programs probably drive these differences in function. Here, to better understand these differences, we evaluated the organization of single cells using multiplexed imaging and single-nucleus RNA and open chromatin assays across eight different intestinal sites from nine donors. Through systematic analyses, we find cell compositions that differ substantially across regions of the intestine and demonstrate the complexity of epithelial subtypes, and find that the same cell types are organized into distinct neighbourhoods and communities, highlighting distinct immunological niches that are present in the intestine. We also map gene regulatory differences in these cells that are suggestive of a regulatory differentiation cascade, and associate intestinal disease heritability with specific cell types. These results describe the complexity of the cell composition, regulation and organization for this organ, and serve as an important reference map for understanding human biology and disease.

## Main
The human adult intestinal system is a complex organ that consists of approximately 7 m of small intestine and 2  m of large intestine. This system completes the digestive process that begins in the oral cavity and stomach, first absorbing water and small-molecule nutrients (such as sugars, monovalent ions and amino acids) in the small intestine, then accumulating larger molecules such as fibre in the large intestine, which serves as an anaerobic fermentation chamber enabling the breakdown and absorption of by-products and the synthesis, often through alimentary gut microbiota, and absorption of other nutrients such as vitamins1.

The small intestine is phenotypically heterogeneous, comprising three morphologically distinct regions—the duodenum, jejunum and ileum2. The large intestine can be partitioned into the ascending, transverse, descending and sigmoid regions. Each of these anatomical regions contains an immense diversity of phenotypically and morphologically distinct cell types. Epithelial, stromal and immune cells, each comprising multiple cell types, reside throughout the intestine. Immune cells are of particular interest, as they interact with the microbiome and foreign material present in the gut3. Although these broad cell types are common to all portions of the intestinal system, specific cell types are known to display locational preferences. For example, Paneth cells populate the small intestine, and enteroendocrine L cells are found primarily in the ileum and large intestine4,5. Moreover, these cell types are spatially organized into different ‘neighbourhoods’ across these intestinal regions, and both the composition of these neighbourhoods and the molecular phenotypes of the underlying cellular types vary in relatively unknown ways across these anatomical regions. These differences in both the composition of functional neighbourhoods and the molecular identity of the cell states that comprise these neighbourhoods define the composition and function of the human intestine.

Here, we map many portions of the intestine at the single-cell resolution using single-nucleus RNA, open chromatin and spatial proteomic imaging technologies. Previous studies have mapped cell types using single-cell RNA-sequencing (scRNA-seq) and have catalogued cell types across the intestine6. We extend this research by spatially mapping cells and proteins using co-detection by indexing (CODEX)7,8,9,10 as well as mapping gene regulatory information using single-cell assay of open chromatin using single-nucleus assay for transposase-accessible chromatin with sequencing (snATAC–seq)11. We define the relative abundance of distinct cell types across the intestine, including the enormous complexity of epithelial cells across different intestinal regions, and the organization of cells into different multicellular structural niches. We also map gene regulatory differences in these cells that are suggestive of a regulatory differentiation cascade. These results provide important insights into cell function, regulation and organization for this complex organ and serve as an important reference for understanding human biology and disease.

## Mapping the human intestine
We mapped the cell composition, regulatory information and spatial distribution of single cells across the intestines of multiple donors using single-nucleus RNA-seq (snRNA-seq), which measures nuclear RNA transcripts in individual nuclei; snATAC-seq, which measures open chromatin in single cells; and CODEX, which stains the same tissue section with up to 54 antibody probes against different targets (usually proteins). We analysed eight sections from nine individuals: seven individuals of European ancestry (five male and two female) and two African American individuals (one male and one female). Age ranges were from 24 to 78 years. The eight regions (in order of trajectory from the stomach) were as follows: the duodenum, proximal jejunum, mid-jejunum and ileum from the small intestine, and the ascending, transverse, descending and sigmoid regions of the large intestine.

## Multiplexed imaging of the intestine
To create a spatial map of the intestine across the eight regions, we used CODEX multiplexed imaging, which enables insights into cellular interactions, composition of multicellular tissue units and spatial relationships to the overall function of the intestine9,10. We first validated and optimized CODEX staining, imaging and image processing for 16-mm2 sections of fresh-frozen samples on one participant (B001) (Supplementary Figs. 1–3). 

![](images/2024-02-13-15-27-51.png)
Supplemental Figure 1: CODEX multiplexed imaging of first donor B001 for small intestine and colon samples. A) 44 marker antibody base panel used for imaging. B) CODEX imaging of one of the 8 different sites taken from the colon for B001, with 5/44 markers shown (scale bar = 500 µm). Four zoomed in regions (scale bar = 100 µm) with various 5 color combinations of markers from the larger image (denoted by colored outline) with also an H&E image shown for the tissue. C) Multicellular neighborhood map for the same region with both cell type and neighborhood maps zoomed in around immune follicle regions. Representative image taken here is one of 8 taken from donor B001. 
![](images/2024-02-13-15-30-43.png)
Supplemental Figure 2: Cell type maps for all 8 regions imaged. For donor 1 (B001) of the small intestine and colon (scale bar = 1 mm). 
![](images/2024-02-13-15-31-26.png)
Supplemental Figure 3: Determination of multicellular neighborhoods in CODEX multiplexed imaging for donor 1 across all 8 regions. A) Cell type enrichment score within each neighborhood as represented in the heatmap. B) Cell type mapped back to each individual sample imaged (scale bar = 1 mm). 

For the other eight donors, we expanded our CODEX antibody panel by adding and validating 17 intestine-specific markers (Supplementary Information 1 and Supplementary Fig. 4) for a total of 54 antibodies that enabled the spatial identification of 25 cell types12 (Extended Data Fig. 1c and Supplementary Figs. 5 and 6).
![](images/2024-02-13-15-42-05.png)
C) accompanying cell type map following cell segmentation and unsupervised clustering. 

![](images/2024-02-13-15-32-48.png)
Supplemental Figure 4: CODEX multiplexed imaging with expanded 54 antibody CODEX panel. A) One region of B004 (total of 8) shown with 6 markers shown (Vimentin, CD3, aSMA, CD45, Cytokeratin, and CD31) (scale bar = 500 µm) B) Zoomed in regions with 6 markers each shown for the region highlighted (yellow box) in A with additional markers added to the panel highlighted (scale bar = 100 µm). C)  Cell type by marker heatmap normalized both by column and row to show markers which define cell types from CODEX multiplexed imaging for samples B004,5,6.
![](images/2024-02-13-15-33-39.png)
Supplemental Figure 5: Cell type maps for all 8 regions imaged. For donors A) B004, B) B005, and C) B006 of the small intestine and colon (scale bar = 1 mm).
![](images/2024-02-13-15-34-20.png)
Supplemental Figure 6: Quantification of cell type percentages for all donors (n=8, error bars indicate standard deviation). A) Cell type percentage separated by donor. B) Cell type percentage grouped by location in the intestine. C) Cell type percent summation graph by location in the intestine with all cell types shown

We used the resultant dataset (a total of 2.7 million cells) to compare the cellular composition and organization across the different tissue regions, normalizing to overall cell grouping (Fig. 1a–c). 
![](images/2024-02-13-15-43-50.png)
a–c, Cell type percentages from CODEX data averaged across eight donors. Cell types are normalized to the stromal (a), immune (b) and epithelial (c) compartments. Statistical analysis was performed using two-sided t-tests comparing the difference in cell type percentage between the small bowel (SB) and the colon (CL); *P < 0.05. ICC, interstitial cells of Cajal; NK, natural killer cells; TA, transit-amplifying cells.

Within the stromal compartment, moving from the small intestine to the colon, we observed a decrease in endothelial cells and an increase in smooth muscle cells (Fig. 1a and Extended Data Fig. 1d). 
![](images/2024-02-13-15-44-56.png)
a–c, Cell type percentages from CODEX data averaged across eight donors. Cell types are normalized to the stromal (a), immune (b) and epithelial (c) compartments. Statistical analysis was performed using two-sided t-tests comparing the difference in cell type percentage between the small bowel (SB) and the colon (CL); *P < 0.05. ICC, interstitial cells of Cajal; NK, natural killer cells; TA, transit-amplifying cells. 

![](images/2024-02-13-15-46-54.png)

D-E) Stromal cell type percentages either as a percent of D) All stromal cells, or E) all cells restricted to the Muscularis Externa tissue unit.

To verify that this was not an artefact of capturing more muscularis externa within samples of the colon compared with the small intestine, we calculated the percentages of all cell types within the four different pathological compartments of the intestine: the mucosa, muscularis mucosa, submucosa and muscularis externa. Indeed, even when comparing all of the cell types found within the muscularis externa, there was still a significant decrease in endothelial cells and an increase in smooth muscle cells (Extended Data Fig. 1e).
![](images/2024-02-13-15-49-46.png)
 D-E) Stromal cell type percentages either as a percent of D) All stromal cells, or E) all cells restricted to the Muscularis Externa tissue unit.

 Thus, not only is there less vasculature more broadly in the colon, but there is less within the muscularis externa and a higher density of smooth muscle cells.


In the immune compartment, we observed a decrease in CD8+ T cells from the small intestine to the colon (Fig. 1b, Extended Data Fig. 1f and Supplementary Fig. 7a–c), consistent with previous observations13.
![](images/2024-02-13-15-54-42.png)
a–c, Cell type percentages from CODEX data averaged across eight donors. Cell types are normalized to the stromal (a), immune (b) and epithelial (c) compartments. Statistical analysis was performed using two-sided t-tests comparing the difference in cell type percentage between the small bowel (SB) and the colon (CL); *P < 0.05. ICC, interstitial cells of Cajal; NK, natural killer cells; TA, transit-amplifying cells.

![](images/2024-02-13-15-51-21.png)
F) Immune cell type

![](images/2024-02-13-15-52-41.png)
![](images/2024-02-13-15-53-04.png)
Supplemental Figure 7: Cell type percentages as determined by CODEX multiplexed imaging. A) Immune cell type percentages as a percent of all immune cells. B) Percentage of CD8+ T cells of all cell types across different areas samples from small intestine to colon. C) Heatmap of p values from Tukey post-test after a significant difference was found using a one-way ANOVA for the percent of CD8+ T cells across different areas of the small intestine and colon.

 Conversely, we observed an increase in the percentage of dendritic cells within the colon compared with in the small intestine that is also seen when examining total cell percentages within the mucosa (Fig. 1b and Extended Data Fig. 1f).

In the epithelial compartment, we observed a decrease in enterocytes, an increase in secretory enterocytes (goblet cells) and CD66+ enterocytes and an absence of Paneth cells when moving from the small intestine to the colon (Fig. 1c, Extended Data Fig. 1g and Supplementary Fig. 7d). 
![](images/2024-02-13-15-56-37.png)
a–c, Cell type percentages from CODEX data averaged across eight donors. Cell types are normalized to the stromal (a), immune (b) and epithelial (c) compartments. Statistical analysis was performed using two-sided t-tests comparing the difference in cell type percentage between the small bowel (SB) and the colon (CL); *P < 0.05. ICC, interstitial cells of Cajal; NK, natural killer cells; TA, transit-amplifying cells.
![](images/2024-02-13-15-58-27.png)
G) epithelial cell type percentages either as a percent of all cells restricted to the Mucosa tissue unit. 

![](images/2024-02-13-15-59-06.png)
D) Epithelial cell type percentages as a percent of all epithelial cells. 

We also detected a rare population of CD57+ enterocytes that is enriched within the duodenum compared with in other areas of the intestine (Extended Data Fig. 1h and Supplementary Fig. 7e). These gastric-like cells are enriched in areas of the duodenum within submucosal glands (Extended Data Fig. 1i and Supplementary Fig. 7f).

## Cell type associations with clinical data
We also evaluated cell type changes with donor metadata. M1 macrophage levels had the highest correlation with body mass index (BMI) (Fig. 1d) and were restricted to the mucosa (Fig. 1e). 

![](images/2024-02-13-16-10-23.png)
d, The percentage of M1 macrophages within the small bowel and colon for all donors plotted versus donor BMI (Pearson correlation r = 0.86). e, Cell type maps of the mid-jejunum from representative individuals (n = 8 donors) with high or low BMI with M1 macrophages (black) highlighted among stromal (light grey) and epithelial (grey) cell types also shown. Scale bar, 250 µm. 

M1 macrophages are pro-inflammatory and have been implicated in chronic inflammatory disease, autoimmunity and problems with wound healing in the intestine14,15,16. Similarly, obesity increases the risk of gastrointestinal disorders17. Although the donors did not have histories of gastrointestinal disorders, we found that individuals with a BMI characterized as overweight (25–29.9) have a fivefold increase in M1 macrophages and individuals with obesity (BMI > 30) have an eightfold increase compared with individuals who are normal weight (18.5–25). We also observe decreases in endothelial cells (from 25% to 20%) and CD8+ T cells (from 42% to 25%) in donors with a history of hypertension (Fig. 1f).
![](images/2024-02-13-16-11-30.png)
f, Cell type percentages for endothelial and CD8+ T cells compared for donors with or without a history of hypertension. Statistical analysis was performed using two-sided t-tests; *P = 0.038, ***P = 0.00013. n = 3–5 donors. 

 High pressure due to a lower ratio of total vasculature is expected, but a substantial decrease in CD8+ T cells is surprising (Supplementary Fig. 7a).

![](images/2024-02-13-16-12-30.png)
Supplemental Figure 7: Cell type percentages as determined by CODEX multiplexed imaging. A) Immune cell type percentages as a percent of all immune cells.


## Spatial restriction of immune cells
In addition to cell type composition, cellular density can highlight whether a cell has broad functions over large regions, is spatially restricted for specialized functions or has the need for specific cell–cell interactions. We quantified the local cell density for all cell types (Fig. 1g and Extended Data Fig. 1j,k). 
![](images/2024-02-13-16-13-47.png)
g, Quantification of the same-cell density measured as an average distance of its five nearest same-cell neighbours divided by the maximal possible same-cell distance within the tissue. n = 64 tissue sections. 

![](images/2024-02-13-16-14-39.png)
J-K) Quantification of the same-cell density that is measured as an average distance of its 5 nearest same-cell neighbours normalized by the maximal possible same-cell distance within the tissue (n = 64 tissue sections) for J) stromal and K) epithelial cell types.

Visual inspection suggested that plasma cells (~0.2) with the highest same-cell type density were restricted to specific mucosal areas, followed by CD8+ T cells (~0.37), then M2 macrophages (~0.5), which were diffuse throughout all areas of the intestine (Extended Data Fig. 1l).
![](images/2024-02-13-16-16-05.png)
L) A representative cell type map (one of 64 tissue sections from 8 donors) with only plasma cells, CD8+ T cells, and M2 Macrophages shown (scale bar = 500 µm).

 Indeed, M1 macrophage density (~0.39) was lower than its M2 counterpart. Quantification of the distribution of each macrophage subset within the different intestinal tissue units indicates a spatial restriction of macrophage subsets (Fig. 1h), suggesting important functional roles in these regions and that other macrophage subtypes among M2 macrophages exist that may also be spatially restricted.
![](images/2024-02-13-16-17-31.png)
 h, The percentage of macrophage subsets across major intestinal compartments.

In summary, these results suggest an important role for spatial restriction of immune cell subtypes along the length of the intestine.

## Stromal multicellular neighbourhoods
To provide a global view of intercellular interactions, cellular densities and overall multicellular structures of the intestine, we performed cellular neighbourhood analysis10 (Methods and Extended Data Fig. 1a).
![](images/2024-02-13-16-19-27.png)
A) Schematic for how CODEX multiplexed imaging was performed on arrays of 4 different sections of either colon and small intestine from the same donor simultaneously. Image processing steps done to extract single-cell spatial data. 


 This revealed 18 significant multicellular structures with major epithelial, stromal and immune-based neighbourhoods (Fig. 2a,b and Extended Data Fig. 2b–d).
 ![](images/2024-02-13-16-21-36.png)
 a, Twenty unique intestinal multicellular neighbourhoods were defined by enriched cell types as compared to the overall percentage of cell types in the samples. b, An example in which neighbourhoods mapped back to the tissue show overall tissue structures. Scale bar, 0.5 mm.

 ![](images/2024-02-13-16-20-33.png)
 B-D) Neighbourhood percentages from CODEX data averaged normalized by B) stromal, C) immune, and D) epithelial compartments. Asterix indicates p-value less than 0.05 difference in cell type percentage from the small bowel (SB) to the colon (CL) by two-sided T test.
 
  Eight neighbourhoods were classified as stromal neighbourhoods and identified major structures within the intestine: micro- and macrovasculature, innervated stroma and smooth muscle, and innate immune hubs within the stroma and smooth muscle areas (Fig. 2a).
![](images/2024-02-13-16-22-56.png)
a, Twenty unique intestinal multicellular neighbourhoods were defined by enriched cell types as compared to the overall percentage of cell types in the samples.

Only the Smooth Muscle neighbourhood increased moving from the small intestine to the colon, whereas the innervated and innate immune smooth muscle neighbourhoods did not (Extended Data Fig. 2e and Supplementary Fig. 8a).
![](images/2024-02-13-16-24-05.png)
E) Stromal multicellular neighbourhood percentages either as a percent of all neighbourhoods restricted to the Muscularis Externa tissue unit (* p value< 0.05, *** p value < 0.001, n = 8 donors, by two-sided T test,).

![](images/2024-02-13-16-24-43.png)
Supplemental Figure 8: Multicellular neighborhood percentage analysis from CODEX multiplexed imaging data of the intestine. A) Stromal multicellular neighborhood percentages as a percent of all stromal neighborhoods.

 This further suggests that these dense compartmentalized smooth muscle cell areas (Extended Data Fig. 2f) increase within the colon.


![](images/2024-02-13-16-26-16.png)
F) Quantification of the same-cell density for just smooth muscle cells within different smooth muscle multicellular neighbourhoods (x axis) (n = 32 tissue sections). 

## Immune multicellular neighbourhoods
Congruent with our observation of high plasma cell density (Fig. 1g), we observed a Plasma-Cell-Enriched neighbourhood driven by increased density of plasma cells (Fig. 2a).

![](images/2024-02-13-16-47-34.png)
g, Quantification of the same-cell density measured as an average distance of its five nearest same-cell neighbours divided by the maximal possible same-cell distance within the tissue. n = 64 tissue sections.

![](images/2024-02-13-16-48-32.png)
a, Twenty unique intestinal multicellular neighbourhoods were defined by enriched cell types as compared to the overall percentage of cell types in the samples. 

 This Plasma-Cell-Enriched neighbourhood also exhibits co-enrichment of CD4+ T cells and antigen-presenting cells such as dendritic cells and macrophages (Fig. 2a) and is localized within the mucosa lamina propria (Extended Data Fig. 2g–i).
 ![](images/2024-02-13-16-50-02.png)
 G-H) Cell type maps for a region of the small intestine (one of 64 tissue sections imaged from 8 donors) with G) all cell types plotted for the whole tissue (scale bar = 500 µm), H) cells contained within the plasma cell neighbourhood (scale bar = 500 µm), and a magnified area of denoted by rectangle showing subset of cell types (scale bar = 50 µm). I) CODEX fluorescent imaging with subset of fluorescent markers overlaid for the same tissue as G (Hoechst=Blue, CD4=Green, CD68=magenta, CD38=yellow, CD206=cyan, CD138=grey), (scale bar = 500 µm with magnified insert scale bar = 100 µm).


These observations are consistent with observations suggesting that secretion or ligand engagement of plasma cells from antigen-presenting cells within the bone marrow can maintain long-term survival in plasma-specific niches18,19,20.

Notably, despite their relatively low density in the intestine, CD8+ T cells were enriched in two major neighbourhoods (Fig. 2a). One neighbourhood (CD8+ T Cell-Enriched IEL (intraepithelial lymphocyte)) exhibits enrichment of both epithelial cell types and CD8+ T cells. Thus, the neighbourhood analysis was able to separate the CD8+ T cells that are intraepithelial lymphocytes, which are critical for rapid immunological responses against infection21 and maintenance of epithelial integrity22. This CD8+ T Cell-Enriched IEL neighbourhood was one of the neighbourhoods of which the prevalence changed from the small intestine (~30%) to the colon (~3%) (Extended Data Figs. 2c and 3a and Supplementary Fig. 8a).
![](images/2024-02-13-16-54-53.png)
B-D) Neighbourhood percentages from CODEX data averaged normalized by B) stromal, C) immune, and D) epithelial compartments. Asterix indicates p-value less than 0.05 difference in cell type percentage from the small bowel (SB) to the colon (CL) by two-sided T test. 

![](images/2024-02-13-16-55-46.png)
A) Immune neighbourhood percentages as a percent of immune neighbourhoods. 

![](images/2024-02-13-16-56-31.png)
A) Immune neighbourhood percentages as a percent of immune neighbourhoods. 

 This is the spatial compartment from which we observed a global decrease in CD8+ T cell percentage (Fig. 1b) and also significantly decreases with a history of hypertension (Extended Data Fig. 3b). We suggest that the ability of CD8+ T cells to survive or locate within intraepithelial spaces is negatively affected by hypertension.

![](images/2024-02-13-16-58-14.png)
a–c, Cell type percentages from CODEX data averaged across eight donors. Cell types are normalized to the stromal (a), immune (b) and epithelial (c) compartments. Statistical analysis was performed using two-sided t-tests comparing the difference in cell type percentage between the small bowel (SB) and the colon (CL); *P < 0.05. ICC, interstitial cells of Cajal; NK, natural killer cells; TA, transit-amplifying cells

![](images/2024-02-13-16-57-15.png)
B) Neighbourhood percentages for Microvasculature and CD8+ T cell IEL neighbourhoods compared for donors with or without a history of hypertension (Microvasculature p value = 0.0065<, CD8+ T Enriched IEL p value = 0.0017 by two-sided T test, n = 3-5 donors).



The decrease in the CD8+ T Cell-Enriched IEL neighbourhood is met with an increase in the Plasma-Cell-Enriched neighbourhood within the colon (Extended Data Figs. 2c and 3a).
![](images/2024-02-13-17-00-48.png)
B-D) Neighbourhood percentages from CODEX data averaged normalized by B) stromal, C) immune, and D) epithelial compartments. Asterix indicates p-value less than 0.05 difference in cell type percentage from the small bowel (SB) to the colon (CL) by two-sided T test. 

![](images/2024-02-13-17-01-40.png)
A) Immune neighbourhood percentages as a percent of immune neighbourhoods. 

 In particular, there is a significant decrease in Plasma-Cell-Enriched neighbourhoods within the ileum as compared to the colon (Supplementary Fig. 7c–d).
 
![](images/2024-02-13-17-02-34.png)
C) Heatmap of p values from Tukey post-test after a significant difference was found using a one-way ANOVA for the percent of CD8+ T cells across different areas of the small intestine and colon. D) Epithelial cell type percentages as a percent of all epithelial cells. 
 
 By contrast, there is also an increase in the Adaptive-Immune-Enriched neighbourhood within the ileum as compared to the colon (Supplementary Fig. 7e–f).

![](images/2024-02-13-17-03-22.png)
E) Heatmap of p values from Tukey post-test after a significant difference was found using a one-way ANOVA for the percent of CD8+ T cells across different areas of the small intestine and colon.  F) Power analysis for cell types that were significantly different from the small intestine to the colon using a power of 0.8 and alpha of 0.05. (* p value< 0.05, ** p value< 0.01, *** p value < 0.001, n=8 donors, by two-sided T test). All boxplots in figures are plotted as minimum, 25 percentile, median, 75 percentile, maximum, and outliers as points outside 1.5 the interquartile range.

Notably, although proximal to the colon, the ileum has the most distinct immune microenvironment from the colon.

CD4+ T cells contributed to five diverse multicellular neighbourhoods (Fig. 2a). This broad neighbourhood membership is fitting, given that CD4+ T cells coordinate innate and adaptive immune responses. CD4+ T cell, B cell and dendritic cell membership defined two different follicle-based structures. The first of these structures, which exists in outer regions of the follicle, exhibited higher enrichment of CD4+ T cells, whereas inner regions of the follicle were enriched for B cells (Fig. 2a). The presence of the Inner Follicle (that is, the germinal centre) neighbourhood was dependent on a fully mature lymphoid follicle like a Peyer’s patch within the image (Fig. 2b).

![](images/2024-02-13-17-04-37.png)
b, An example in which neighbourhoods mapped back to the tissue show overall tissue structures. Scale bar, 0.5 mm. 

 However, the Outer Follicle neighbourhood was found across the intestine irrespective of the presence of a fully mature follicle. Out of the 64 tissues that we imaged, 11 had mature follicles that we segmented for comparison (Supplementary Fig. 9a–b).

![](images/2024-02-13-17-05-39.png)
Supplemental Figure 9: Changes in neighborhood composition from the small bowel (SB) to colon (CL). A) Cell type percentage and B) multicellular neighborhood percentage for each follicle region segmented out from individual sections (11/64) imaged by CODEX multiplexed imaging. 

The cell type and neighbourhood compositions differed between each follicle irrespective of location, driven primarily by percentage of dense B cells (Supplementary Fig. 9a), found within the Inner Follicle neighbourhood (Supplementary Fig. 9b). The variation in the ratio of Inner Follicle neighbourhood to Outer Follicle neighbourhood across the intestine suggests a continuum of lymphoid tissues within the intestine23,24,25,26.

Variation in the multicellular composition of cellular neighbourhoods may indicate a core functionality as well as a need for compositional flexibility based on anatomical location. We compared the cell type compositions in the small intestine versus the colon for all neighbourhoods and found that both inner and outer follicle structures are less conserved, whereas stromal neighbourhoods are more conserved (Extended Data Fig. 3c).

![](images/2024-02-13-17-07-05.png)
C) Difference in composition in neighbourhood by cell type for all neighbourhoods based on subtracting the log2 fold enrichment of each cell type found within that neighbourhood compared to average percentages in the tissue in SB from CL. Neighbourhoods and cell types are ordered by summing the absolute value of all rows and columns to denote conservation of a neighbourhood. 


 We observed differences in neighbourhood composition in Paneth-Cell-Enriched (significantly less abundant in the colon than the small bowel) and Transit-Amplifying-Zone (not different in terms of abundance) neighbourhoods that are both enriched for early epithelial progenitor cells, potentially indicating different crypt microenvironments across the intestine (Extended Data Fig. 2d and Supplementary Fig. 9c,d).

![](images/2024-02-13-17-09-34.png)
D) 22 unique intestinal multicellular neighbourhoods (y axis of heatmap) were defined by enriched cell types (x axis of heatmap) as compared to overall percentage of cell types in the samples with 2 unique neighbourhoods not identified with overall neighbourhood analysis. 

![](images/2024-02-13-17-10-14.png)
C) Epithelial neighborhood percentages as a percent of epithelial neighborhoods. D) Power analysis for multicellular neighborhoods that were significantly different from the small intestine to the colon using a power of 0.8 and alpha of 0.05. (* p value< 0.05, ** p value< 0.01, *** p value < 0.001 by two-sided T test, n=8 donors).



## Intestinal crypt neighbourhoods
As we observed differences in neighbourhood cell type conservation, we performed neighbourhood analysis on each individual region of the intestine separately and then concatenated the results. All aggregated neighbourhoods (Fig. 2a) were identified (Extended Data Fig. 3d).

![](images/2024-02-13-17-12-03.png)
D) 22 unique intestinal multicellular neighbourhoods (y axis of heatmap) were defined by enriched cell types (x axis of heatmap) as compared to overall percentage of cell types in the samples with 2 unique neighbourhoods not identified with overall neighbourhood analysis. 

 We also identified two unique neighbourhoods: Neuroendocrine-Enriched, which was found only in the colon, and Neutrophil-Enriched, which was found throughout the intestine but enriched in the colon (Fig. 2c and Extended Data Fig. 3e,f).

![](images/2024-02-13-17-12-58.png)
E) Epithelial neighbourhood percentages as a percent of epithelial neighbourhoods from multicellular analysis performed on each individual region of the intestine separately. F) Immune neighbourhood percentages as a percent of immune neighbourhoods from multicellular analysis performed on each individual region of the intestine separately. (* p value< 0.05, ** p value< 0.01, *** p value < 0.001 by two-sided T test, n = 8 donors). 
 
 The Neutrophil-Enriched neighbourhood was characterized by a high density of neutrophils associated with vasculature and innate immune cells, found often within stromal and smooth muscle areas (Extended Data Fig. 3d). The Neuroendocrine-Enriched neighbourhood had a mixture of epithelial and immune cell types enriched (Extended Data Fig. 3d).

![](images/2024-02-13-17-13-44.png)
D) 22 unique intestinal multicellular neighbourhoods (y axis of heatmap) were defined by enriched cell types (x axis of heatmap) as compared to overall percentage of cell types in the samples with 2 unique neighbourhoods not identified with overall neighbourhood analysis. 

The identification of the Neuroendocrine-Enriched neighbourhood suggested differential organization of neuroendocrine cells in the small intestine compared with in the colon. Indeed, neuroendocrine cells were found to be denser within the colon compared with in the small intestine (Fig. 2d).

![](images/2024-02-13-17-15-03.png)
(d) or the epithelial neighbourhoods as determined by individually characterizing cellular neighbourhoods by region (n = 64 tissue sections) 


Furthermore, neuroendocrine cells are most dense within the Neuroendocrine-Enriched neighbourhood as compared to neuroendocrine cells in other epithelial neighbourhoods (Fig. 2e), and the density decreases with the maturity of the epithelial cell types that define these epithelial neighbourhoods (Fig. 2e).

![](images/2024-02-13-17-15-55.png)
(e). Avg., average; max., maximum.

 This suggests that the Neuroendocrine-Enriched neighbourhood represents the colon crypt neighbourhood, which is confirmed by its localization near the muscularis mucosa (Fig. 2f).

![](images/2024-02-13-17-16-36.png)
f, A subset of epithelial neighbourhoods mapped back to a representative magnified region (n = 8 donors) of the mucosa of a transverse colon section. Scale bar, 250 µm.

Identification of this crypt environment only within the colon and not in the small intestine is consistent with our finding of variation in early epithelial environments in our first neighbourhood analysis (Extended Data Fig. 3c), and Paneth-Cell-Enriched neighbourhoods are observed only within the small intestine (Extended Data Fig. 3e).

![](images/2024-02-13-17-18-00.png)
(c) and tissue units (based on clustering communities)

![](images/2024-02-13-17-18-33.png)
e, Tissue hierarchy graph of the multilevel network of the tissue comprised of the different structures. Shapes correspond to structural level (cell type, neighbourhoods, communities, tissue units); colours represent individual categories as indicated in a–d; the size of shapes represents the percentage of tissue; and the size of connected lines represents the overall contribution to the next level of the structure when moving down the graph in increasing tissue structural hierarchy. The black rectangles highlight a single trajectory highlighted within this Article. The red bracket indicates separation of stromal tissue units from the mucosal tissue units.


Indeed, Paneth cells are known to be restricted to the small intestine and also to be enriched within the intestinal crypt. As a consequence, to understand whether the Neuroendocrine-Enriched neighbourhood was similar to the small intestine crypt environment, we examined the neighbours surrounding Paneth cells with increasing window size (Fig. 2g).

![](images/2024-02-13-17-20-08.png)
g,h, The approach to calculate concentric increasing neighbourhoods around a Paneth cell (g) to generate cellular neighbourhoods for Paneth cells at increasing radii 

This analysis revealed that there was a high enrichment of neuroendocrine cells, but it also underscored that interstitial cells of Cajal, CD4+ T cells and CD8+ T cells were enriched within the local microenvironment (Fig. 2h–j).

![](images/2024-02-13-17-20-53.png)
(h). i,j, Schematic (i) and CODEX fluorescence data illustrating a representative (1 of 32 sections from 8 donors) magnified portion of the proximal jejunum depicting colocalization of Paneth cells (DEFA5, green) and CD8+ T cells (CD8, cyan) and CD4+ T cells (CD4, yellow) in the intestinal crypt environment (j). Scale bar, 50 µm.


This agrees with enrichment of CD4+ T cells and interstitial cells of Cajal found within the Neuroendocrine-Enriched neighbourhood (Extended Data Fig. 3d).

![](images/2024-02-13-17-22-01.png)
D) 22 unique intestinal multicellular neighbourhoods (y axis of heatmap) were defined by enriched cell types (x axis of heatmap) as compared to overall percentage of cell types in the samples with 2 unique neighbourhoods not identified with overall neighbourhood analysis. 



## Hierarchical structural organization
Multicellular neighbourhood analysis revealed key differences in the structural composition across the intestine as well as in the composition of these neighbourhoods, particularly with relation to the adaptive immune system and the intestinal crypt. However, how these multicellular neighbourhoods interact with one another, and how they are spatially structured in the tissue is unclear. Understanding how multicellular groups are related is key to both defining the hierarchy of tissue organization, as well as defining key functional tissue interfaces.

We investigated higher-order structural organization using several methods. First, we clustered windows of neighbourhood compositions in a manner similar to how we clustered windows of cell types (Fig. 3a) to define neighbourhoods (Fig. 3b).

![](images/2024-02-13-17-23-58.png)
a–d, Representation of multiple levels of hierarchical description: cell type (a), multicellular neighbourhood (b), community (based on clustering windows of cell neighbourhoods)

This generated communities of neighbourhoods (Fig. 3c and Extended Data Fig. 4a–c), which we then leveraged to identify major tissue units such as the muscularis mucosa (Fig. 3d and Supplementary Fig. 10).

![](images/2024-02-13-17-25-22.png)
(c) and tissue units (based on clustering communities) (d) comparing the small bowel with the colon for two representative tissue sections (from a total of 64 sections from 8 donors). Scale bar, 1 mm.

![](images/2024-02-13-17-26-17.png)
![](images/2024-02-13-17-26-31.png)
A) Community analysis was done by taking a window across neighbourhood maps and vectorizing the number of each neighbourhood type in each window, clustering windows, and assigning clusters as multi-neighbourhood communities of the intestine. 10 unique intestinal multi-neighbourhood communities (y axis of heatmap) were defined by enriched neighbourhood types (x axis of heatmap) as compared to overall percentage of neighbourhood types in the samples. B) Quantification of neighbourhood types across each section of the intestine (colour legend within panel A). C) Community percentages as a percent of all communities for small intestine and colon (* p value< 0.05, ** p value< 0.01, *** p value < 0.001, n = 8 donors).

![](images/2024-02-13-17-28-07.png)
Supplemental Figure 10: Overall tissue unit represented on all 8 sections. From donors B008-B012 (scale bar = 100 µm).

The Paneth-Cell-Enriched neighbourhood was enriched within the Adaptive-Immune-Enriched community (Extended Data Fig. 4a).

![](images/2024-02-13-17-28-59.png)
A) Community analysis was done by taking a window across neighbourhood maps and vectorizing the number of each neighbourhood type in each window, clustering windows, and assigning clusters as multi-neighbourhood communities of the intestine. 10 unique intestinal multi-neighbourhood communities (y axis of heatmap) were defined by enriched neighbourhood types (x axis of heatmap) as compared to overall percentage of neighbourhood types in the samples.

Indeed, concentric neighbourhood environments surrounding the Paneth-Cell-Enriched neighbourhood also showed colocalization with Outer Follicle and Adaptive-Immune-Enriched neighbourhoods (Extended Data Fig. 4d). These results support the idea that the adaptive immune system forms a conserved niche with the intestinal crypt.

![](images/2024-02-13-17-29-48.png)
D) Concentric multi-neighbourhood analysis surrounding only neighbourhoods labelled as Paneth Cell Enriched neighbourhoods, with number of nearest neighbours for a given row in the heatmap.


To relate the various levels of spatial organization, we created a hierarchical structure network graph (Fig. 3e and Supplementary Fig. 11).

![](images/2024-02-13-17-31-30.png)
e, Tissue hierarchy graph of the multilevel network of the tissue comprised of the different structures. Shapes correspond to structural level (cell type, neighbourhoods, communities, tissue units); colours represent individual categories as indicated in a–d; the size of shapes represents the percentage of tissue; and the size of connected lines represents the overall contribution to the next level of the structure when moving down the graph in increasing tissue structural hierarchy. The black rectangles highlight a single trajectory highlighted within this Article. The red bracket indicates separation of stromal tissue units from the mucosal tissue units.

![](images/2024-02-13-17-32-05.png)
Supplemental Figure 11: Graph of multi-level structure of the tissue as broken down by the different structures. Shapes correspond to structural level, colors represent individual categories, size of shapes represents the percent contribution to tissue, and the size of connected lines represents the overall contribution to the next level of structure as moving down the graph in increasing tissue structural hierarchy. These are separated either by small bowel (SB) or colon (CL).

Each level of this graph is connected to the next by its major contributors. Using this intuitive formalism, we can observe many levels of intestinal cell and tissue-structure organization. For example, we observed crosstalk between stromal and smooth muscle cell types and structures, which are in turn isolated from epithelial and immune components that are more entwined with one another (Fig. 3e (red bracket)).


Using this graph structure, we can also observe multilevel relationships between the structures. For example, Paneth cells (Fig. 3e (green circle)) are a rare cell subset (size) and are primarily enriched within Paneth-Cell-Enriched neighbourhoods (Fig. 3e (light blue square)), which are enriched in the Adaptive-Immune-Enriched community (Fig. 3e (orange triangle)) that, in turn, is enriched within the muscularis mucosa tissue unit (Fig. 3e (red diamond)). This relationship can be seen within the tissue, where we see the Adaptive-Immune-Enriched community localized to the bottom of the colon crypt (Fig. 3f).

![](images/2024-02-13-17-33-04.png)
f, Magnified mucosal area of a colon community map shown within c. Scale bar, 100 µm. 

Visualizing the communities also revealed spatial layering of the intestine, moving from the smooth muscle, stroma and particularly within epithelial areas (Fig. 3f). To formalize these observations of intercommunity-level spatial interactions, we created27 a spatial context map27 (Methods) that revealed major structural relationships between communities within the colon (Fig. 3g).

![](images/2024-02-13-17-33-42.png)
g, The spatial-context maps of the colon highlighting relationships of communities across the entire sample. This structure is defined by the number of unique communities required to make up at least 85% in a given window. The circles represent the number of cells represented by a given structure. The green rectangle highlights a structure discussed in this Article and maps this structure back to g. The colours are as indicated in c.

For example, moving from left to right in the spatial context map parallels tissue organization in a cross-section of the intestine moving from the muscularis externa to the top of the mucosa (Fig. 3f,g). In brief, the Smooth Muscle community (red triangle) is often found alone (size of circle), indicating its compartmentalization from other communities (Fig. 3g). However, it is found next to the Stromal community (grey triangle), with which it forms an interface (grey and red triangle combination) (Fig. 3g (yellow highlighted edge)). This then forms a trio interface with the Adaptive-Immune-Enriched community (orange triangle). Moving to the right, we observe another trio that involves the Smooth Muscle, Adaptive-Immune-Enriched and Secretory Epithelial communities (Fig. 3g (green box)). This pattern continues across the Plasma-Cell-Enriched community (yellow triangle) and then the Mature and CD66+ Epithelial community (teal triangle) (Fig. 3g).

![](images/2024-02-13-17-34-40.png)
 f, Magnified mucosal area of a colon community map shown within c. Scale bar, 100 µm. g, The spatial-context maps of the colon highlighting relationships of communities across the entire sample. This structure is defined by the number of unique communities required to make up at least 85% in a given window. The circles represent the number of cells represented by a given structure. The green rectangle highlights a structure discussed in this Article and maps this structure back to g. The colours are as indicated in c. 

We confirmed these community–community interactions using an established method for identifying two-combination community motifs27 (Methods). Significant associations with just the Adaptive-Immune-Enriched community shared across the intestine demonstrate that there are connections to the Plasma-Cell-Enriched, Smooth Muscle, Secretory Epithelial, Stromal and Follicle communities but not to the Mature Epithelial community (Extended Data Fig. 5b and Supplementary Fig. 12), which aligns with our previous analyses (Fig. 3f,g).

![](images/2024-02-13-17-36-14.png)
B-C) Community-community motifs that are significantly enriched in both the small intestine and colon as compared to a null distribution of motif instances created from random permutation of tissue graph labels, where B) shows only those motifs that interact with the Adaptive Immune Enriched community and

![](images/2024-02-13-17-36-48.png)
Supplemental Figure 12: Multi-community interaction motifs highlight organization of communities within the intestine. A-B) Community-community motifs that are significantly enriched as compared to a null distribution of motif instances created from random permutation of tissue graph labels, where A) shows motifs that are significant in the colon and B) shows motifs that are significant in the small bowel (p values were Bonferroni corrected by multiplying by twice the number of tests conducted in each comparison group).



Similarly, analysis of other shared significant motifs shows that the Plasma-Cell-Enriched community intersects with both the Secretory Epithelial and Mature Epithelial communities (Extended Data Fig. 5c).

![](images/2024-02-13-17-37-55.png)
C) shows all other shared motifs between the SB and CL. Motifs indicated by shape and colour indicate those motifs that have significant p value versus those that are indicated with an x in the graph; p values were Bonferroni corrected by multiplying by twice the number of tests conducted in each comparison group. Colour legend is also the same as panel B. 

 We created a spatial context map for just the cells found in the mucosa (Extended Data Fig. 5d–f) and, again, observed a high-frequency intersection between the Plasma-Cell-Enriched, Secretory Epithelial and Transit-Amplifying Zone neighbourhoods (Extended Data Fig. 5f (red box)) with many connections to the Plasma-Cell-Enriched neighbourhood, implicating an important role in overall intestinal tissue structure.

![](images/2024-02-13-17-38-39.png)
D) Representative neighbourhood map (one of 64 tissue sections from 8 donors) with (scale bar = 500 µm) E) Region magnified as in the main figure of the mucosal area of a colon community map, but this time with the multicellular neighbourhoods coloured (see panel D for legend) (scale bar = 100 µm). F) Spatial context maps of the CL highlighting relationships of multicellular neighbourhoods across just the neighbourhoods found within the tissue unit Mucosa. This structure is defined by the number of unique neighbourhoods required to make up at least 85% in a given window. Circles represent the number of cells represented by a given structure. Red rectangle highlights a structure discussed in the manuscript and maps this structure back to panel K. Colour legend is also the same as panel D.



In summary, these results indicate that immune-cell-enriched neighbourhoods have important roles in intestinal tissue organization. Indeed, we found enrichment of cell types moving from the smooth muscle community to the lumen (Fig. 3h and Extended Data Fig. 5g,h), which shows an increase in adaptive immune cells in the base of the crypt, restricted zones of plasma cells, and an increase in innate immune cells and CD8+ T IELs towards the top of the intestine (Fig. 3h).

![](images/2024-02-13-17-40-29.png)
h, The cell type percentage of immune cells shown for each community ordered in relative order of general increasing proximity to the lumen on the basis of community spatial-context analysis.

![](images/2024-02-13-17-39-42.png)
G-H) Cell type percentage of G) epithelial and H) stromal cells shown for each community ordered in relative order of general increasing proximity to the lumen based on community spatial context analysis.

In conclusion, our hierarchical mapping data further confirm compositional differences in multicellular structures between the small intestine and colon but also highlight conserved multicellular structure interactions and an important distribution of distinct cell types in subregions of the intestine.

## Single-nucleus RNA and chromatin atlas
The CODEX experiments revealed distinct cellular arrangements across intestinal regions, but included only 54 probes, potentially limiting both the number and complexity of cell types identified. To overcome these limitations, we performed 10x multiome sequencing analysis of intestinal regions from six donors and separate 10x snRNA-seq and snATAC-seq analysis of intestine regions from three additional donors (Fig. 4a, Methods and Extended Data Fig. 6a, b).

![](images/2024-02-13-17-48-08.png)
a, Sections of the intestine analysed by separate snRNA-seq and snATAC-seq experiments or multiome experiments. b,c, UMAP representation of all snRNA stromal

![](images/2024-02-13-17-48-52.png)
(a,b) Violin plots of TSS enrichment (a) and RNA counts/cell (b) for different samples included in the study. Samples are coloured by the location from which they were obtained.

We first annotated all snRNA cells from both the snRNA and multiome experiments together, by dividing cells into immune, stromal and epithelial compartments, revealing a total of 10 immune, 16 stromal and 16 epithelial cell types (Fig. 4b–d), and annotated the remaining scATAC cells from three donors separately. Cell types were annotated by examining gene expression levels and gene activity scores of known marker genes as well as by labelling the datasets with previously published scRNA-seq data28 (Methods).

![](images/2024-02-13-17-49-48.png)
b,c, UMAP representation of all snRNA stromal (b) and immune (c) cells coloured by cell type. DC, dendritic cells; fib., fibroblasts; ILC, innate lymphoid cells; myofib., myofibroblasts; SM, smooth muscle cells. d, UMAP representation of snRNA epithelial cells in the four primary regions of the intestine. Jejunum includes both proximal- and mid-jejunum samples. Colon includes samples from the ascending, transverse, descending and sigmoid colon. 

The majority of immune cell types were identified in both the single-nucleus and CODEX data (Supplementary Table 2). To determine which cell types were significantly differentially abundant between locations, we applied two methods that control for the compositional nature of single-cell data29,30. We found that CD8+ T cells were more abundant in the small intestine, whereas B cells were more abundant in the colon (Fig. 4f and Extended Data Fig. 7), consistent with the CODEX results (Fig. 1b).

![](images/2024-02-13-17-50-38.png)
f, Beeswarm plot showing the log-transformed fold change between the small intestine and colon for groups of nearest-neighbour cells from different cell type clusters. Significant changes are indicated in red and blue. Lymph. endo., lymphatic endothelial cells. 

![](images/2024-02-13-17-52-00.png)
a–c) Beeswarm plot showing the log-fold change between the three main regions of the small intestine and colon for groups of nearest neighbour cells from different cell type clusters in the stromal (a), immune (b), and epithelial (c) compartments computed with Milo. Significant changes are indicated in colour. d) Boxplots comparing the fraction of all cells in each sample composed of each cell type for samples from the colon, ileum, jejunum, and duodenum. e) Log2FC in abundance of each cell type between the regions listed on the y-axis as estimated with scCODA. Only significant results at an FDR of 0.05 are shown, with all nonsignificant differences plotted as white.

Within the stromal compartment, we annotated eight fibroblast subtypes—interstitial cells of Cajal (KIT, ANO), glial cells (SOX10, CDH19, PLP1), neurons (SYP, SYT1, RBFOX1), pericytes (NOTCH3, MCAM1, RGS5), adipocytes (PLIN1, LPL) and three endothelial cell clusters (Fig. 4b and Extended Data Fig. 6f).


Cells with high expression of MYH11 and ACTA2 were classified as smooth muscle/myofibroblasts. One of these clusters had high expression of DES, which we labelled DEShigh and may represent smooth muscle. We also identified fibroblasts with high levels of WNT agonists, such as RSPO3, and the BMP antagonist GREM1, which are probably present at the crypts, and fibroblasts with high expression of WNT5B and BMP transcripts thought to be present at the villi28 (Extended Data Fig. 6f). Elsewhere, the ADAMDEC1high population has been referred to as S1 fibroblasts, the WNT5B and BMP signalling fibroblasts as S2 fibroblasts, and the KCNN3high population as S3 fibroblasts6,31. Similar to the immune cells, we observed changes in cell type abundance along the intestine (Fig. 4f and Extended Data Fig. 7). For example, two smooth muscle/myofibroblast clusters were less abundant in the small intestine than in the colon. Conversely, villus fibroblasts and endothelial cells were most abundant in the duodenum and jejunum, less abundant in the Ileum and least abundant in the colon.

As epithelial cells initially clustered on the basis of location (Extended Data Fig. 6c), we subclustered and annotated epithelial cells from different primary locations—duodenum, jejunum, ileum and colon—separately.

![](images/2024-02-17-18-28-06.png)
c) UMAP projection of all snRNA cells coloured by location.

In each intestinal region, we observed a differentiation trajectory from stem cells to mature absorptive cells (enterocytes). We divided this differentiation trajectory into five cell types using similar annotations to other studies (stem > TA2 > TA1 > immature enterocyte > enterocyte)28. However, these cells exist along a continuum and the exact number of cell types and locations of the divisions between cell types is therefore arbitrary, and changing the resolution during clustering results in more or fewer clusters along this trajectory. In addition to absorptive cells, we also observed goblet cells, tuft cells and enteroendocrine cells in all regions of the intestine, while Paneth cells were present only in regions of the small intestine. Consistent with recent reports of BEST4+ enterocytes in the small and large intestine6,32, we observed populations of BEST4+ enterocytes in all eight intestinal regions assayed.

To further examine the diversity of enteroendocrine cells along the intestine, we subclustered enteroendocrine cells from all intestinal regions and annotated the clusters based on expression of enteroendocrine marker genes (Extended Data Fig. 6g,h).

![](images/2024-02-17-18-29-01.png)
g) Sub-clustering of enteroendocrine cells from all regions of the intestine. h) Dotplot representation of the expression of subtype specific enteroendocrine and enterochromaffin marker genes in different enteroendocrine cell types in our datasets.


We identified many known subtypes of enteroendocrine cells, including D cells (SSThigh), I cells (CCKhigh), K cells (GIPhigh), Mo cells (MLNhigh), S cells (SCThigh), L cells (GCGhigh and PYYhigh) and enterochromaffin cells (TPH1high). Two clusters of enteroendocrine cells that did not express any of these specific markers were labelled as enteroendocrine Un1 and enteroendocrine Un2 in the subclustered dataset. L cells can be further divided on the basis of expression of INSL5+, which is primarily expressed by L cells in the colon. To determine which gut cell types the INSL5+ L cells may be signalling, we examined the expression of RXFP4—the cognate receptor for INSL533,34. We found that RXFP4 is primarily expressed by colon enterochromaffin cells and, to a lesser extent, I cells, suggesting that these are the most likely cell types that the INSL5+ L cells are signalling (Fig. 4e).

![](images/2024-02-17-18-30-20.png)
e, Expression of INSL5 and the INSL5 receptor, RXFP4, in different cell types in different regions of the intestine. RXFP4 was expressed in less than 2.5% of all epithelial cell types that were not included in the dot plot. C, colon; D, duodenum; I, ileum; J, jejunum; enterochrom., enterochromaffin cells; enteroendo., enteroendocrine cells. 

Enteroendocrine and enterochromaffin cells were more abundant in the duodenum and jejunum compared with in the colon, and we observed shifts in the fraction of each subtype of enteroendocrine cells along the intestine (Extended Data Fig. 7).

![](images/2024-02-17-18-31-57.png)
a–c) Beeswarm plot showing the log-fold change between the three main regions of the small intestine and colon for groups of nearest neighbour cells from different cell type clusters in the stromal (a), immune (b), and epithelial (c) compartments computed with Milo. Significant changes are indicated in colour. d) Boxplots comparing the fraction of all cells in each sample composed of each cell type for samples from the colon, ileum, jejunum, and duodenum. e) Log2FC in abundance of each cell type between the regions listed on the y-axis as estimated with scCODA. Only significant results at an FDR of 0.05 are shown, with all nonsignificant differences plotted as white.



For example, D cells were most abundant in the duodenum35. These results provide detail on how populations of enteroendocrine and enterochromaffin cells change along the length of the intestine.

Finally, the duodenum also contained an additional cluster of cells that expressed secretory markers, but did not cluster with goblet, tuft, enteroendocrine or Paneth cells. We subclustered these cells (Fig. 4g) and identified one cluster with high expression of MUC5B, one cluster with high expression of MUC6 and TFF2, and one cluster with high expression of the exocrine markers CELA3B and CPB1 (Fig. 4h).

![](images/2024-02-17-18-33-30.png)
g, Subclustering of specialized secretory cells in d coloured by cell type. h, The expression of secretory genes in specialized secretory cells defined in g.

The MUC5B+ and MUC6+ cells are probably different types of mucin-producing cells, with the MUC6+ cells probably representing the cells of the Brunner’s glands36. Notably, the MUC5B+ cells and exocrine cells were primarily present in only one sample in our dataset, making it possible that they are contaminating cells from a different tissue, in which expression of these markers is more common, or a rare cell type in the duodenum (Extended Data Fig. 6i).

![](images/2024-02-17-18-34-32.png)
I) Sub-clustering of specialized secretory cells coloured by sample.

The MUC6+ cells were present in the majority of the samples, so we further validated their presence by labelling cells in CODEX experiments with MUC6 (Fig. 4i,j).

![](images/2024-02-17-18-35-49.png)
i, The percentage of MUC6+ enterocytes among all cell types for the four donors imaged using MUC6 antibodies. j, Representative CODEX fluorescence image of the duodenum (6 out of 57 markers overlaid) (left). Hoechst (nuclei), MUC6, MUC1 (also found in gland areas), cytokeratin (pan-epithelial), α-SMA (muscle) and vimentin (stromal) staining is shown. Right, the magnified area highlights the gland just below the mucosa in the submucosa. This experiment was independently repeated four times. Scale bars, 500 µm (left) and 50 µm (right).

Within the CODEX data, we made the distinction between CD66+ enterocytes and CD57+ enterocytes. When we examined the expression of these markers in the snRNA data, we found that CD66+ enterocytes typically represent mature cell types in the colon (Extended Data Fig. 8a,b). CD57+ cells are much less abundant and CD57 expression was primarily observed only at low levels in the cluster of MUC6+ cells, consistent with the presence of CD57+ cells in glands in the duodenum in the CODEX data (Extended Data Fig. 8a,b).


![](images/2024-02-17-18-37-04.png)
a) Expression of B3GAT1 and four CEACAM transcripts plotted on the UMAP manifold of epithelial cells from the duodenum, jejunum, ileum, and colon. b) Dotplot representation of the expression of B3GAT1 and four CEACAM transcripts by different epithelial cell types in different regions of the intestine.

## Molecular interactions in nearby cells
The CODEX data enable the assignment of neighbouring cell types and the snRNA-seq data provide RNA expression levels in the corresponding cell types. By combining both data types, we can nominate potential ligand–receptor pairs that may facilitate cell-to-cell interactions. We identified significant pairwise cell type colocalizations and focused on those that were significantly different between the small bowel and colon (Extended Data Fig. 8c and Supplementary Table 2).

![](images/2024-02-17-18-44-26.png)
c) Large colon (CL) and small bowel (SB) show differences in cell-cell co-localization patterns; annotated cell-pairs are more colocalized in the colon compared to the small bowel (Student’s T test, two-sided, corrected for multiple hypothesis testing with the Benjamini Hochberg procedure).

Cell type pairs involving plasma cells are more colocalized in the descending-sigmoid colon tissue section than in other sections (Extended Data Fig. 8e).

![](images/2024-02-17-18-45-01.png)
e) Differences in pairwise cell-type colocalization patterns across tissue locations (n = 3 samples for each location).



Using snRNA-seq data from these six cell types, we performed differential expression analyses of ligands and receptors (Methods) and identified 48 pairs of ligands and receptors (across 41 cell–cell pairs) that are more expressed in the colon than in the small bowel (Supplementary Table 3). For example, we found that the ligand SEMA4D and receptor MET were upregulated in plasma cells and TA2, respectively, in colon tissue (Extended Data Fig. 8d), which was not observed in the small intestine (Supplementary Table 3).

![](images/2024-02-17-18-45-48.png)
d) SEMA4D ligand expression in plasma cells and MET receptor gene expression in TA2 cells, showing higher expression in colon than small bowel (one-sided Wilcoxon Rank-Sum Test). 

SEMA4D signalling has been associated with B cell aggregation and long-term survival37. The implication of the MET receptor on TA2 cells in the colon, compared with TA2 cells in the small intestine, is further evidenced by RAS and MAPK signalling (Extended Data Fig. 9b, Supplementary Table 4) and upregulation of plexins (Extended Data Fig. 9b), consistent with the CODEX imaging data (Fig. 3f,g and Extended Data Figs. 5a–f and 9c).

![](images/2024-02-17-18-47-10.png)
b) PLXNA2, RASA1, and MAP2K5 expression in TA2 cells in large colon (CL) and small bowel (SB) (one-sided Wilcoxon Rank-Sum Test). 

![](images/2024-02-17-18-47-46.png)
c) Representative image of a donor’s transverse colon with plasma cells (red), TA cells (blue), and other cell types (grey) highlighted with also a magnified area indicated with rectangle. (left scale bar = 500 µm; right scale bar = 100 µm)

![](images/2024-02-17-18-48-49.png)
A) Schematic of a representative community map and corresponding tissue community network graph (one of 64 tissues). B-C) Community-community motifs that are significantly enriched in both the small intestine and colon as compared to a null distribution of motif instances created from random permutation of tissue graph labels, where B) shows only those motifs that interact with the Adaptive Immune Enriched community and C) shows all other shared motifs between the SB and CL. Motifs indicated by shape and colour indicate those motifs that have significant p value versus those that are indicated with an x in the graph; p values were Bonferroni corrected by multiplying by twice the number of tests conducted in each comparison group. Colour legend is also the same as panel B. D) Representative neighbourhood map (one of 64 tissue sections from 8 donors) with (scale bar = 500 µm) E) Region magnified as in the main figure of the mucosal area of a colon community map, but this time with the multicellular neighbourhoods coloured (see panel D for legend) (scale bar = 100 µm). F) Spatial context maps of the CL highlighting relationships of multicellular neighbourhoods across just the neighbourhoods found within the tissue unit Mucosa. This structure is defined by the number of unique neighbourhoods required to make up at least 85% in a given window. Circles represent the number of cells represented by a given structure. Red rectangle highlights a structure discussed in the manuscript and maps this structure back to panel K. Colour legend is also the same as panel D.

![](images/2024-02-17-18-50-09.png)
f, Magnified mucosal area of a colon community map shown within c. Scale bar, 100 µm. g, The spatial-context maps of the colon highlighting relationships of communities across the entire sample. This structure is defined by the number of unique communities required to make up at least 85% in a given window. The circles represent the number of cells represented by a given structure. The green rectangle highlights a structure discussed in this Article and maps this structure back to g. The colours are as indicated in c.

Using spatial transcriptomics analysis based on Molecular Cartography38,39,40 (Methods), we validated that TA cells positive for MET and plasma cells positive for SEMA4D were more colocalized in the colon (colocalization quotient (CLQ) = 1.57). We also validated nine other receptor–ligand interactions involving plasma cells that were more colocalized in the colon (Supplementary Table 5). Consequently, this indicates a potential differential survival signal that maintains the Plasma-Cell-Enriched neighbourhood in the colon.

In addition to colocalization of receptor–ligand pairs, we probed our spatial transcriptomics dataset and evaluated whether other receptor–ligand pairs were more expressed by target cells in the colon than in the small bowel. We validated 15.3% of our predictions (9 out of 58; P < 0.002; Methods) that have a matching cell type with snRNA-seq (Methods and Supplementary Table 6). One other example that we examined was the expression of ligand FN1 (fibronectin) in myofibroblasts and its receptor PLAUR (urokinase receptor) in enterocytes (Extended Data Fig. 9d).

![](images/2024-02-17-18-51-32.png)
d) Example of receptor ligands expressed at higher levels in the colon than the small intestine (SI) for the FN1 by myofibroblast and PLAUR by enterocyte. 

Overall, these results nominate potential ligand–receptor interactions that mediate specific cell type interactions in distinct regions of the intestine.

## Integration of CODEX and snRNA data
Our multiplexed imaging analysis also enables examination of the cell–cell pairs that are enriched within each neighbourhood or community regardless of tissue location. We used the same approach to calculate cell–cell colocalization in the Follicle community. This resulted in 57 colocalized cell pairs, such as the CD8+ T cell–CD4+ T cell pair, each pair containing a large list of potential receptor–ligand interactions (Extended Data Fig. 9e).

![](images/2024-02-17-18-52-19.png)
e) Colocalization quotient (CLQ) for all cell types found within the follicle community.

To more comprehensively describe potential interactions and expressions within neighbourhoods, we integrated CODEX and snRNA-seq at the single-cell level using MaxFuse41, a method that we specifically designed for these challenging integration tasks: linear assignment coupled with graph smoothing and meta cell construction. The overall matching accuracy was 92.1% and cell types segregated within the co-embedding space, and the same cell types from snRNA-seq and CODEX were well blended while showing concordant RNA/protein expression patterns, indicating robust integration performance (Fig. 5a).

![](images/2024-02-17-18-53-25.png)
a, snRNA-seq and CODEX integration using MaxFuse for both the small bowel and colon. Integrated cells are coloured by modality of origin, cell types or RNA/protein expression levels. MUC2 expression (protein and RNA) is shown on the integrated plots, as well as the top 10 DEGs of the Inner Follicle neighbourhood as determined by CODEX. Min., minimum. CN, cellular neighbourhood.

Using this integration, we calculated the differentially expressed genes (DEGs) among the previously CODEX-defined cellular neighbourhoods with the pair-linked transcriptome information (Extended Data Fig. 9f).

![](images/2024-02-17-18-55-01.png)
f) Heatmap of differentially expressed genes (from MaxFuse matched snRNA-seq cells) among individual CODEX cells, grouped based on previously determined cellular neighbourhoods from CODEX analysis. 

In particular, we examined the expression levels of DEGs involved with the follicle neighbourhoods (Fig. 5a (bottom UMAP)) and identified gene pathways that are enriched in these spatial organizations, including B-cell-receptor signalling, T-cell-polarity regulation and tolerance induction of self antigen pathways (Extended Data Fig. 9g).

![](images/2024-02-17-18-55-39.png)
g) Gene Ontology Enrichment analysis for cellular neighbourhoods “inner folliclle” and “outer folliclle”, based on the differentially expressed genes shown in f.

Thus, integrating CODEX and snRNA-seq data revealed specific expression patterns associated with distinct cellular neighbourhoods.


## Regulatory TFs in cells of the intestine
To obtain insights into the factors that control intestinal differentiation, we next investigated potential transcription factors (TFs) that regulate gene expression in intestinal cell types. We first computed ChromVar deviation scores42 for each cell in our dataset, identifying TF motifs that are associated with chromatin accessibility in different cell types. As many TFs share similar motifs, examining TF expression in conjunction with motif activity helps to identify the specific TFs that are functional in different intestinal cell types. We next identified the TFs with the highest correlation between their gene expression and the chromatin-accessibility activity level of their putative DNA-binding motifs43 to nominate TFs that directly drive accessibility changes. Across the intestine, this analysis revealed 61 TFs with motif activity that was strongly correlated with expression (r > 0.5; Fig. 5b). Broadly, we observed TFs that are active in the secretory lineage and TFs that are active in the absorptive lineage with few TFs that participate in both (for example, KLF4 in colon enterocytes and goblet cells throughout the intestine; Fig. 5b).

This analysis highlights many TFs that are known to have important roles in the intestine. For example, ASCL2, a master regulator of intestinal stem cells44, exhibited high expression and motif accessibility in stem cells. Other TFs with high expression and motif activity in stem cells include NFIX, NFIC and HNF1B. Within the secretory lineage, POU2F3, a regulator necessary for the development of tuft cells in mice45, was highly expressed and had high motif activity in tuft cells throughout the human intestine. When comparing the TF footprinting signal around POU2F3 motifs in tuft cells compared with enterocytes, we observed greater accessibility flanking POU2F3 motifs in tuft cells, suggesting that POU2F3 is more likely to be bound to its motif in tuft cells (Extended Data Fig. 10d). Along with POU2F3, RUNX1 and RUNX2 also exhibited high expression and accessibility in tuft cells throughout the intestine, indicating that they may also have a role in tuft cell differentiation or maintenance. Among goblet cells, KLF4, which is required for terminal differentiation into colonic goblet cells in mice46, exhibited high gene expression and motif activity. Notably, the expression and motif activity of KLF4 was also high in differentiated absorptive epithelial cells (immature enterocytes and enterocytes) in the colon, but not in other regions of the intestine, indicating location-specific regulation.

Several regulatory TFs were nominated in goblet cells, including ATOH1 and FOXA3. ATOH1 is necessary for secretory lineage commitment in the mouse intestine47,48, and here we provide data supporting a similar function in human goblet cells. To provide further evidence that ATOH1 drives accessibility in goblet cells, we compared ATOH1 footprints in goblet cells and enterocytes (Extended Data Fig. 10e). Indeed, we found greater flanking accessibility around ATOH1 motifs in goblet cells, consistent with greater ATOH1 binding in these cells. For FOXA3, there is evidence that FOXA3 leads to goblet cell metaplasia in the lungs49, and our findings indicate that it probably is an important regulatory TF in the colon. We noted above that goblet cells are more abundant in the colon compared with in the small intestine, but it is unclear what biases cells to differentiate into goblet cells with greater frequency in the colon. Possible causes include differences in signalling in the crypts versus differences in stem cells between the regions. We identified motifs that are enriched in differential peaks between small intestine and colon stem cells and found that FOX motifs are enriched in peaks that are more accessible in colon stem cells (Extended Data Fig. 10a–c). Similarly, FOX TFs have greater motif deviation scores in colon stem cells compared with in small intestine stem cells (Extended Data Fig. 10a–c). As we nominate several FOX TFs as potential regulators of goblet cells, increased FOX activity may partially explain why goblet cells are more abundant in the colon.

Within enteroendocrine/enterochromaffin cells, RFX2, RFX3 and RFX6 exhibited high expression and accessibility. Of these, RFX6 is a proposed regulator of enteroendocrine cell differentiation, and loss of RFX6 impairs enteroendocrine cell differentiation in mice50. Together, these results support previous findings and nominate additional TFs that may be important regulators of distinct intestinal cell types that can vary across the different regions of the intestine (for example, KLF4).

To help to validate these findings, we completed this analysis in the two separate cohorts: the multiome samples and the samples with separate snRNA and snATAC data. To examine TF expression in the latter group, we integrated the snRNA and snATAC data using canonical correlation analysis to align the datasets and assign snRNA data to each snATAC cell51,52 (Methods). This analysis reproduced many of the findings in the multiome analysis, with 48 out of the 61 TFs originally identified in the multiome analysis reaching the same significance criteria (Extended Data Fig. 10f).

To determine which TFs may drive cell function in stromal and immune cells in the intestine, we performed the same analysis for cells in each of these compartments. Within the immune compartment, this analysis highlighted many TFs that are known to be important for cell type differentiation and maintenance, including GATA2 in mast cells53 and PAX5 in B cells54 (Extended Data Fig. 10g). Among stromal cells, we identified TFs associated within specific lineages, including EBF1 in pericytes—which was recently suggested to contribute to pericyte cell commitment55—PPARG in adipocytes56 and SOX10 in glia57 (Extended Data Fig. 10h). We also nominate potential regulatory TFs in interstitial cells of Cajal, including HAND1, HOXD11 and MEIS1, as well as potential regulatory TFs for different classes of intestinal fibroblasts.

## Absorptive differentiation trajectories
Intestinal stem cells differentiate into mature enterocytes, goblet cells and specialized cell types such as enteroendocrine, tuft and Paneth cells, renewing the epithelial lining approximately every three to seven days58. To map the regulatory and gene expression changes that accompany stem cell differentiation into mature enterocytes, we defined differentiation trajectories along this pathway in the single-nucleus data from the duodenum, jejunum, ileum and colon (Fig. 6a and Methods). We next identified regions of variable chromatin accessibility (peaks) and variable gene expression across these four differentiation trajectories. An example of the variable genes is TMPRSS15, which encodes the protein that converts trypsinogen to trypsin in the duodenum; its expression gradually increases in more differentiated cells in the duodenum (Extended Data Fig. 10m–p). We clustered these variable peaks and genes to identify sets with shared behaviour (Fig. 6b,c). The resulting clusters include peaks and genes that are open and expressed early in the differentiation pseudotime (for example, in stem cells) in all regions of the intestine, which we denote as early. This cluster includes general markers of intestinal stem cells, including RGMB, SOX9, SMOC2 and LGR5. Other clusters of genes and peaks include those that are predominantly found in differentiated small intestine cells (for example, MTTP, APOA4, APOC3, MME), in undifferentiated colon (for example, GPX2), in ileum (such as PLB1, CUBN) and in differentiated colon (such as SCNN1B59, SLC26A3, CLCA4).
![](images/2024-02-08-13-49-43.png)
a, UMAP projections depicting the cells in the four primary regions of the intestine (duodenum, jejunum, ileum and colon), labelled by cell type (left) and differentiation pseudotime (right). b,c, Variable peaks (b) and genes (c) identified along the absorptive differentiation trajectories. The rows represent the z-scores of accessibility for each peak or expression for each gene. The columns represent the position in pseudotime from the start to the end for each section of the intestine. Peaks and genes were k-means-clustered and the clusters were labelled on the basis of the dominant time and location where they are most accessible/expressed. d, Integrated gene expression of TFs of which the expression is correlated with ChromVar motif activity along the differentiation trajectory. e, Accessibility at peaks correlated with the expression of ETV6 along the differentiation trajectory in each region (left). Each peak is normalized to the maximum accessibility along any of the trajectories. Right, integrated gene expression of ETV6 along the differentiation trajectory in each region is plotted on the right. Norm., normalized. f, Linkage-disequilibrium score regression to identify the enrichment of GWAS SNPs in cell-type-specific marker peaks. Unadjusted coefficient P values computed from linkage-disequilibrium score regression are plotted in the heat map. Significance is indicated by an asterisk, as determined by a Bonferroni-corrected coefficient P value of <0.05. P values for determining significance were adjusted for the number of cell classes tested.
To identify both chromatin drivers of cluster-specific regulation and relevant cluster-specific gene expression programs, we computed TF-motif enrichments in each cluster of peaks (Extended Data Fig. 10k) and KEGG pathway enrichment in each cluster of genes (Extended Data Fig. 10l). Groups of peaks accessible late in the differentiation trajectories were enriched for HNF4 and JUN/FOS motifs. As expected, genes primarily expressed late in the differentiation trajectory in the small intestine (late duodenum jejunum cluster) were enriched for multiple metabolic KEGG pathways including fat digestion and absorption and vitamin digestion and absorption.

We next identified TFs of which the gene expression is correlated with the activity of their motifs in each of the four differentiation trajectories. We found 67 TFs with expression correlated with their motif activity (r > 0.5) and plotted the integrated gene expression of these TFs (Fig. 6d). Many TFs display similar activity along all four differentiation trajectories. For example, ASCL2, a master regulator in intestinal stem cells, is highly expressed at the beginning of all four trajectories. Other TFs, such as ETV6, exhibit different behaviours in different regions of the intestine. ETV6 is a TF with decreased expression in colorectal cancer compared with in the normal colon, and genetic variation in ETV6 may confer colorectal cancer susceptibility60. We found that ETV6 is more highly expressed in the colon compared with in the small intestine and, in contrast to in the small intestine, ETV6 expression increases in more differentiated cells in the colon.

As an example of examining how genes with unique expression patterns may be controlled, we next investigated which regulatory elements may be responsible for the variable expression of ETV6 in different regions of the intestine. We identified accessibility peaks correlated with ETV6 expression along the differentiation pseudotime in any region of the intestine (Fig. 6e). The correlated peaks most accessible in the small intestine (exonic 1 and promoter 1) became less accessible along the differentiation trajectory, consistent with the decreased expression along the differentiation pseudotime in these regions. Similar behaviour was also observed in the colon, in which these peaks became less accessible along the differentiation trajectory. However, multiple other peaks exhibited increasing accessibility in more differentiated cells only in the colon, and we speculate that these regulatory elements may drive the increased expression of ETV6 in differentiated colon cells. The same logic can be applied to identify regulatory elements that may drive changes in gene expression throughout the intestine. For example, we identified three peaks that are highly correlated with expression of TMPRSS15 and may drive its increased expression in the duodenum (Extended Data Fig. 10p). Taken together, this analysis provides a reference for the regulation of stem cell to enterocyte differentiation across the intestine.

We next tested whether disease heritability is enriched in cell-type-specific marker peaks in intestine cell types using linkage-disequilibrium score regression (Fig. 6f and Methods). We identified a significant increase in heritability for Crohn’s disease and coeliac disease in T cell marker peaks, consistent with the importance of T cells in their pathogenesis61. We observed the most significant enrichment of heritability for BMI in enteroendocrine cells, suggesting that genetic variation may have an effect on enteroendocrine cells leading to effects on BMI. As a control, we also tested whether heritability of GWAS SNPs was enriched in an unrelated trait (dental caries) and found no cell-type-specific enrichment. These results map important disease traits to specific cell types in the intestine.

## Discussion
Here we show extensive cellular complexity of the intestine including considerable epithelial heterogeneity and new secretory cell subtypes, that the different regions of the intestine have different cell compositions, and that cells are organized into different neighbourhoods that also form communities defined by both distinct areas of epithelial and immune cells. Additionally, the open chromatin regulatory program defined key regulators and differentiation pathways used in the different regions of the intestine. Our study greatly extends previous single-cell studies by combining both spatial proteomic datasets and single-cell RNA and ATAC technologies, and the resulting datasets serve as a useful resource for the scientific community.

Our multiplexed imaging is the first in-depth spatial study of single cells in the intestine, to our knowledge. Many of our spatial analyses revealed important immune cell type organization within the intestine (Supplementary Discussion). We observed a correlation of M1 macrophages with BMI and spatial restriction of macrophage subtypes17. Although our donors did not have histories of gastrointestinal diseases, an increase in M1 macrophages may potentially indicate an early stage of gastrointestinal disease progression. We also observed that CD8+ T cells decreased from the small intestine to the colon primarily within the CD8+ T Cell-Enriched IEL neighbourhood. Notably, we also found that CD8+ T cells decrease in donors with a history of hypertension and within the CD8+ T Cell-Enriched IEL neighbourhood. Further investigation of T cell levels within the gut in patients with hypertension may provide cell type mechanisms for associations of hypertension with other diseases such as colon cancer62,63.

We identified intestinal crypt multicellular neighbourhoods that were co-enriched with adaptive immune cells such as CD4+ and CD8+ T cells in the small bowel and colon. In the small bowel, stem cell crypt areas were identified by Paneth-Cell-Enriched neighbourhoods, whereas, in the colon, the stem cell crypt was identified with increasing neuroendocrine cell density towards the bottom of the crypt. CD4+ T cells were also the most enriched cell type in the Outer Follicle multicellular neighbourhood, which was present at all sites of the intestine regardless of the presence of fully developed Inner Follicle structures across neighbourhoods. This observation suggests that the immune system appears structurally poised along the intestine to generate germinal-centre-focused immune responses locally as needed. Integration of CODEX and snRNA-seq single-cell data revealed differential gene expression across these cellular neighbourhoods and highlighted important gene modules for the immune response in Inner Follicle neighbourhood structures.

We confirmed the adaptive immune and crypt association with hierarchical spatial analysis and further observed discrete immune cell composition zones across the intestine from an adaptive-immune-enriched area at the base of the crypt, then a plasma-cell-enriched area in the middle of the mucosa, with an innate-immune-enriched zone at the top. Indeed, plasma cells had the highest same-cell density and were also found to co-localize with antigen-presenting cells in a multicellular neighbourhood found in all areas of the intestine. Merging the snRNA-seq data and CODEX data showed that plasma cells and transit-amplifying epithelial cells co-localized more in the colon than in the small intestine, and this was validated by spatial transcriptomics. Restriction and layering of the intestine primarily has focused on epithelial subtypes previously, but we highlight that immune cells share a spatial restriction and zonation. This hierarchical view of multiplexed spatial data can serve as a template for other spatial atlas efforts.

This study extends the work of several scRNA gut atlases6,32. These previous scRNA datasets examined the diversity of cell types in the human intestine, whereas the integrated snRNA and snATAC dataset provides a detailed single-cell regulatory map of the intestine. We used this dataset to identify TFs in different cell types of which the gene expression is highly correlated with the accessibility of the motif to which they bind. This identified TFs that are known to be master regulators of different cell types, including POU2F3 in tuft cells, ASCL2 in stem cells and RFX6 in enteroendocrine cells, while also nominating many additional TFs that are probably important regulators in their respective cell types. This includes RUNX1 and RUNX2 in Tuft cells and FOXA3 and ATOH1 in goblet cells. Finally, with the inclusion of two donors from under-represented backgrounds, our study also extends single-cell analyses to include samples from such groups.

Within all regions of the intestine, intestinal stem cells differentiate into mature absorptive enterocytes. By integrating gene expression and chromatin accessibility data along the differentiation trajectories in different regions of the intestine, we nominate TFs that exhibit consistent behaviour across absorptive differentiation in all regions of the intestine. Among these are known intestinal stem cell regulators such as SOX9 and ASCL2, which are highly expressed and have high chromatin activity of their binding motifs in cells at the beginning of the differentiation trajectory in all regions of the intestine. We also observed differences in TF dynamics between the trajectories in different regions, such as ETV6, which is highly expressed in differentiated absorptive cells in the colon, but not other regions of the intestine. Notably, ETV6 expression is decreased in colorectal cancer and genetic variation in ETV6 may confer colorectal cancer risk60. We speculate that ETV6 is important for normal colon differentiation and its loss may prevent differentiation of colon stem cells. Examining these data also enables us to link specific regulatory elements with the expression of TFs along the trajectory. For the case of ETV6, this analysis identifies one distal and three intronic regulatory elements with similar activity that are probably responsible for driving expression of ETV6 along the absorptive differentiation trajectory in the colon.

Together, these data provide a detailed atlas that can serve as a valuable reference for future studies of the intestine. This includes contextualizing GWAS studies of intestinal disease, similar to the analysis performed above showing heritability of BMI is enriched in enteroendocrine cells, and severing as a reference when comparing disease state such as cancer to the normal colon64.

There are several limitations to our study. First, for each patient, we typically analysed a single sample from each intestinal region. Second, CODEX is limited to 54 markers and does not capture the entire breadth of known cell types within the intestine. Third, it is also important to note that, although there was variation of ages, all individuals were above the age of 24, limiting our analysis of the development of the intestine in children. Also, six out of the nine adults analysed were male. Although our study represents two ethnicities, the patterns across a wide range of ethnicities remain to be elucidated. We are also underpowered to ascertain sex differences, which will probably be important given differences in disease risk for male and female individuals65. These limitations can be addressed in the future with the investigation of more samples.

In summary, we present a detailed map of the human intestine, and the first multiplexed imaging reference for healthy small intestine and colon. In addition to biological insights, this can serve as an important reference for intestinal diseases (such as inflammatory bowel disease) as well as comparisons with other organisms.

## Methods
### Tissue collection and processing
This study complies with all relevant ethical regulations and was approved by the Washington University Institutional Review Board and the Stanford University Institutional Review Board. Human bowel tissues were procured from deceased organ donors. Written informed consent was obtained from the next-of-kin for all donor participants.

Organs were preserved according to surgical protocols to prepare the bowel for transplantation. In brief, a large-bore cannula was placed into the infrarenal aorta before circulatory arrest. Immediately after circulatory cessation, the abdominal viscera was rapidly cooled by flushing ice-cold HTK preservation solution through the aortic cannula and by packing the abdominal cavity with ice. The bowel was kept cold throughout the transport and dissection process until samples could be frozen for long-term storage. Tissue samples collected from the designated bowel sites were preserved by snap freezing in liquid nitrogen for snRNA-seq/scATAC, and embedded and frozen in optimal cutting temperature compound (OCT) for CODEX.

### Array creation
Imaging data were collected from four human donors, each of whom constitutes a dataset. Each dataset includes two arrays of tissues that were imaged together on the same coverslip with four tissues per array: colon (sigmoid, descending, transverse and ascending), and small intestine (ileum, mid-jejunum, proximal jejunum and duodenum). Tissues were individually frozen in OCT moulds and then cut and assembled into arrays of four tissues with known directionality such that a cross-section of each tissue would be achieved cutting the block at once. Arrays were constructed on the cryostat and sectioned at a width of 7 μm.

### Registration of samples with HuBMAP common coordinate framework
We have also registered these blocks within HuBMAP’s tissue registration in a common coordinate framework66. In brief, male and female 3D reference objects for 11 organs including the small bowel and colon were created using Visible Human Project datasets. Using standard surgical anatomical landmarks used to collect the eight bowel sites, the tissue blocks were registered to the reference objects. The anatomical landmarks used for small bowel segments were as follows: (1) descending duodenum to the right of the pancreas head; (2) 5 cm beyond the ligament of Treitz in the jejunum; (3) 200 cm of the jejunum beyond the ligament of Treitz in the mid-bowel; and (4) 5 cm proximal to the ileocecal valve for terminal ileum. Five centimetres of bowel at each site was collected, representing approximately 20 g of tissue at each site. For the colon, the following landmarks used: (1) the right colon midway between the ileocecal valve and the hepatic flexure; (2) the transverse colon midway between the hepatic and splenic flexures; (3) the left colon midway between the splenic flexure to the appearance of the sigmoid mesentery; and (4) the sigmoid colon midway to the rectosigmoid junction where the taenia coli ceased.

### CODEX antibody conjugation and panel creation
CODEX multiplexed imaging was performed according to the CODEX staining and imaging protocol previously described8. Antibody panels were chosen to include targets that identify subtypes of intestinal epithelium and stromal cells, and cells of the innate and adaptive immune system. Detailed panel information is provided in Supplementary Table 7. Each antibody was conjugated to a unique oligonucleotide barcode, after which the tissues were stained with the antibody–oligonucleotide conjugates and we validated that the staining patterns matched the expected patterns already established for immunohistochemistry within positive control tissues of the intestine or tonsil. Similarly, haematoxylin and eosin morphology staining was used to confirm the location of marker staining. First, antibody–oligonucleotide conjugates were tested in low-plex fluorescence assays and the signal-to-noise ratio was also evaluated at this step, then they were tested all together in a single CODEX multicycle.

### CODEX multiplexed imaging
The tissue arrays were then stained with the complete validated panel of CODEX antibodies and imaged8. In brief, this entails cyclic stripping, annealing and imaging of fluorescently labelled oligonucleotides complementary to the oligonucleotide on the conjugate. After validation of the antibody–oligonucleotide conjugate panel, a test CODEX multiplexed assay was run, during which the signal-to-noise ratio was again evaluated, and the optimal dilution, exposure time and appropriate imaging cycle was evaluated for each conjugate (Supplementary Table 7). Finally, each array underwent CODEX multiplexed imaging. Metadata from each CODEX run are provided in Supplementary Table 8.

### CODEX data processing
Raw imaging data were then processed using the CODEX Uploader for image stitching, drift compensation, deconvolution and cycle concatenation. Processed data were then segmented using the CODEX Segmenter or CellVisionSegmenter, a watershed-based single-cell segmentation algorithm and a neural network R-CNN-based single-cell segmentation algorithm, respectively. The donor sample from individual B001 was segmented using the CODEX Segmenter (with parameters tuned as described previously8), whereas all of the other donor samples were segmented using CellVisionSegmenter. CellVisionSegmenter has been shown to work well with segmenting both dense and diffuse cellular tissues with CODEX data67. CellVisionSegmenter is an open-source, pretrained nucleus segmentation and signal quantification software based on the Mask region-convolutional neural network (R-CNN) architecture. Indeed, it was designed and trained on manually annotated images from CODEX multiplexed imaging data within our own group. Consequently, the only parameter that was altered was the growth pixels of the nuclear mask, which we found experimentally to work best at a value of 3. Despite this, no segmentation algorithm does a perfect job of segmentation in cases in which the boundaries identified may capture portions of neighbouring cells, and nuclear segmentation can limit quantified signal that whole-cell segmentation might be able to capture (although also imperfect from lack of consistent cell membrane stains), which has been discussed in more detail in reviews and primary sources of segmentation67,68,69,70,71,72,73,74. For this reason, we performed an in-depth analysis of the different data normalization techniques and unsupervised clustering methods for robust identification of cell types in CODEX intestine data. This analysis revealed that there is some segmentation noise that could affect cell type identification if using manual gating, but using z-normalization, Vortex or Leiden-based unsupervised clustering, over-clustering the data and manually overlaying resultant cell type clusters to the image results in cell type identification at a much higher fidelity75.

Both the CODEX Uploader and Segmenter software can be downloaded from GitHub (https://github.com/nolanlab/CODEX), and the CellVisionSegmenter software is available at GitHub (https://github.com/bmyury/CellVisionSegmenter or https://github.com/michaellee1/CellSeg). After the upload, the images were again evaluated for specific signal: any markers that produced an untenable pattern or a low signal-to-noise ratio were excluded from the ensuing analysis. Uploaded images were visualized in ImageJ (https://imagej.nih.gov/ij/).

### Cell type analysis
B001 and B004 cell type identification was performed according to methods developed previously75. In brief, nucleated cells were selected by gating DRAQ5, Hoechst double-positive cells, followed by z-normalization of protein markers used for clustering (some phenotypic markers were not used in the unsupervised clustering). Cells positive (z > 1) for greater than 35 fluorescent markers were removed from the data. Then the data were overclustered with X-shift (https://github.com/nolanlab/vortex) or Leiden-based clustering with the scanpy Python package (v.1.9.1). These processing steps were performed based on an in-depth analysis of normalization techniques and unsupervised clustering algorithms used for CODEX multiplexed imaging data of the intestine75. These are not new approaches and many packages have emerged for integrating these clustering algorithms into libraries such as Squidpy75. Clusters were assigned a cell type on the basis of average cluster protein expression and the location within image. Impure clusters were split or reclustered after mapping back to the original fluorescence images.

### Cell type annotation using STELLAR
CODEX cell type labels were transferred to other donors using the STELLAR framework for annotating spatially resolved single-cell data, as we described previously12. In brief, STELLAR is a geometric deep learning method that uses the spatial and molecular cell information to transfer cell type labels across different datasets. While SpaGCN76 and Spage2vec77 can leverage spatial and molecular data to annotate cells, these methods are unsupervised clustering methods. As such, they require manual effort to assign cell clusters to corresponding cell types, and can also require additional manual effort for multiple iterative cluster refinements. On the other hand, STELLAR automatically identifies existing cell types and discovers cell types without requiring manual effort, so we used STELLAR as the preferred method. To apply STELLAR, we used B004 donor data as the labelled training dataset as defined in STELLAR. This dataset was curated and annotated by clustering, merging, reclustering, subclustering and assigning cells to cell types based on average marker expression. Each cluster’s purity and accuracy were confirmed by location of the cell within CODEX images with corresponding fluorescence images and also H&E staining. We used B004, B005 and B006 donor dataset to train STELLAR and transfer annotations to all other donor datasets that were treated as unannotated test datasets in the STELLAR framework. We did not expect to find any new cell types across different donors so we used STELLAR to identify existing cell types across donors. All datasets were z-normalized as suggested previously75. We then manually confirmed the quality of STELLAR’s cell type assignments in all donor datasets by looking at average marker expression profiles of predicted cell types. We found that protein marker distributions match expert hand-annotated profiles12.

### CODEX cell type percentage normalization
We normalized the cell type percentage to the overall cell category for three reasons. First, we captured a cross-section of each individual intestinal piece; however, a few of the intestinal pieces (4 out of 64) were not representative cross-sections. Second, with a fixed CODEX imaging window, we attempted to capture the full mucosal area, as this contains the majority of cell types identified by antibodies in our panel, which led to variable amounts of the muscularis externa captured. Third, it is useful to normalize by overall cell type to understand how cell type compositions change across the three compartments.

### CODEX same-cell density analysis
CODEX same-cell density was analysed by taking the average distance of the five nearest neighbours of the same cell type for each individual cell in each imaged region. This average distance was divided by the most diffuse distance for same cell types. The most diffuse same cell distance was calculated by taking the total number of cells of a given cell type divided by the total area of the region. Thus, numbers that are closer to 1 are least dense and numbers closer to 0 are more dense with cells of the same cell type.

### Neighbourhood identification analysis
Neighbourhood analysis was performed as described previously10,27. In brief, this analysis involved (1) taking windows of cells across the entire cell type map of a tissue with each cell as the centre of a window; (2) calculating the number of each cell type within this window; (3) clustering these vectors; and (4) assigning overall structure on the basis of the average composition of the cluster (Extended Data Fig. 2a). In brief, determining window size cut-offs for cellular neighbourhood analysis is an important metric to be chosen. In general, smaller window sizes will identify more local or microstructures, whereas larger window sizes will lead to the identification of similarly composed structures that require a larger window size. For our neighbourhood analysis here, we chose to have window size cut-offs by selecting the ten nearest neighbours around a given cell. This number has worked well to identify conserved compositions representing a cell’s immediate microenvironment or local neighbours in other tissues10,12,27,75,78,79. We chose this strategically to look at the microstructures at the neighbourhood level because we also were curious to understand how these microstructures work together and come together to form macrostructures of the intestine at a multihierarchical scale. In general, the size of the structure does not directly relate to the window size choice, but instead relates to how compartmentalized the conserved cell types are within a given structure. Neighbourhoods were overclustered to 30 clusters. These clusters were mapped back to the tissue and evaluated for cell type enrichments to determine overall structure and merged down into 20 unique structures.

### Neighbourhood conservation analysis
To determine neighbourhood compositional (cell type) conservation across the small bowel and colon, neighbourhood enrichment scores were found separately for both the small bowel and colon samples across all donors. This enrichment score is the average cell type percentage within the average of the neighbourhood cluster divided by the average cell type percentage for all cells in the tissue. The colon enrichment scores for each cell type were subtracted from the small bowel scores to provide the heat map that was ordered both in terms of the greatest absolute sum of differences for both neighbourhood and cell type in conservation. Thus, differences in cell type enrichment for a given neighbourhood indicate that this cell type is not compositionally conserved across the small and large intestines for this neighbourhood structure.

### Community and tissue unit identification analysis
Communities were determined similarly to how multicellular neighbourhoods were determined with some small differences. In brief, the cells in the neighbourhood tissue maps were taken with a larger window size of 100 nearest neighbours. These windows were taken across the entirety of the tissue and the vectors then clustered with k-means clustering and overclustering with 20 total clusters. These clusters were mapped back to the tissue and evaluated for neighbourhood composition and enrichment to determine overall community type. This same approach was applied to communities with a window size of 300 nearest neighbours.

### Hierarchical intestine structural graphs
Each hierarchical level was connected to the next by either what it contributed to the largest in the next level, or what made up at least 15% of this next hierarchy. The percentage of each feature in the level was represented by size of the shape. The shape and colour combination correspond to the level and feature respectively. The size of the connecting line represents the amount that a feature contributes to the next feature.

### Spatial context maps
Spatial context maps were created as previously described27. In brief, the spatial context analysis of neighbourhood–neighbourhood or community–community associations has some similarities with our method to identify multicellular neighbourhoods but also contains a few key differences. First, windows of neighbourhoods or communities were calculated with either 100 or 300 nearest neighbours respectively. For the neighbourhood spatial context maps, only the cells classified in the mucosa tissue unit were included in the analysis, whereas the community spatial context maps included all cells from all tissues. Once windows were calculated (number of each cell type within the window), then the combinations representing more than 85% of the neighbourhoods within that window were selected as a combination. This combination informs about prominent associations of neighbourhoods or communities in the window, a feature that we termed spatial context. Combinations were then counted and represented in size by the size of the black circle underneath the square neighbourhood combination and only combinations that had a greater frequency than 0.1% of all combinations were plotted for visualization purposes. Each combination was then connected to each combination containing it with another combination in sublayers of the graph. For example, if the Secretory Epithelial community was found to represent 85% of a window, then this would be its own combination (purple triangle). If it is found as a combination with the Adaptive-Immune-Enriched community, then it is connected with this in a combination (purple triangle and orange triangle). Similarly, if it is found as a combination with the Plasma-Cell-Enriched community, then it is connected with this in a combination (purple triangle and yellow triangle). The single combination is therefore connected (through black edges) to these combinations (nodes) in the spatial context graph. Similarly, combinations of the Secretory Epithelial and Adaptive-Immune-Enriched communities (purple triangle and orange triangle) derive from this combination (for example, Secretory Epithelial, Adaptive-Immune-Enriched and Follicle (purple, orange and blue triangles)).

### Tissue motif identification
We used a previously developed method to identify significantly associated cellular neighbourhood-neighbourhood motifs27. In brief, motif identification uses segmented areas of the tissue where multiple cells of the same community are co-located, instead of individual cells (Extended Data Fig. 5a). The tissue network graphs therefore represent shared edges between instances of communities. To create a tissue graph for each treatment group, we took the union of the tissue graphs of each unique imaging region. We then created a null-set as the graph of the set of cell neighbourhood or community assignments by a sequence of valid transpositions of cell neighbourhood or community assignments. Permuting neighbourhood or community assignments and fixing the number of vertices created the maximum entropy null distribution. Only two chains with at least five instances were considered. To identify significant chains, P values were Bonferroni corrected by multiplying by twice the number of tests conducted in each comparison group (small bowel and CL).

### Tissue dissociation and nucleus isolation for single-nucleus experiments
Nuclei were isolated using the OmniATAC protocol80. Isolation of nuclei was carried out on wet ice. A total of 40–60 mg of flash-frozen tissue was gently triturated and thawed in 1 ml HB (lysis) buffer (1.0341× HB stable solution, 1 M DTT, 500 mM spermidine, 150 mM spermine, 10% NP40, cOmplete Protease Inhibitor, Ribolock) for 5 min. Tissue was then dounced 10 times with pestle A and 20 times with pestle B, or until there was no resistance from either pestle. The samples were then filtered through a 40 μm cell strainer (Falcon, 352340) and the resulting homogenate was transferred to a prechilled 2 ml LoBind tube. The samples were centrifuged in a 4 °C fixed-angle centrifuge for 5 min at 350 rcf to pellet the nuclei. After centrifugation, all but 50 μl of supernatant was removed. Then, 350 μl HB was added to the nucleus pellet for a total volume of 400 μl and the nuclei were gently resuspended using a wide bore pipet. One volume of 50% iodixanol (60% OptiPrep (Sigma Aldrich; D1556), diluent buffer (2 M KCl, 1 M MgCl2, 0.75 M Tricine-KOH pH 7.8), water) was added and the resulting solution was gently triturated. Next, 600 μl of 30% iodixanol was carefully layered under the 25% mixture. Finally, 600 μl of 40% iodixanol was layered under the 30% mixture. The sample was then centrifuged for 20 min at 3,000 rcf in a 4 °C swinging-bucket centrifuge, resulting in a visible band of nuclei. The supernatant was aspirated down to within 200–300 μl of the nucleus band. The nucleus band was then collected at 200 μl and transferred to a fresh 1.5 ml tube. The sample was diluted with one volume (200 μl) of resuspension buffer (1× PBS, 1% BSA, 0.2 U μl−1 Ribolock). The nucleus concentration was determined using the Countess II FL Automated Cell Counter (Thermo Fisher Scientific; AMQAF1000).

### snATAC–seq
snATAC-seq targeting 9,000 nuclei per sample was performed using the Chromium Next GEM Single Cell ATAC Library & Gel Bead Kit v1.1 (10x Genomics, 1000175) and the Chromium Next GEM Chip H (10x Genomics, 1000161) or Chromium Single Cell ATAC Library & Gel Bead Kit (10x Genomics, 1000110). Libraries were sequenced on the Illumina NovaSeq 6000 system (1.4 pM loading concentration, 50 × 8 × 16 × 49 bp read configuration) targeting an average of 25,000 reads per nucleus.

Single-nucleus transcriptome sequencing using snRNA-seq
snRNA-seq targeting 9,000 nuclei per sample was performed using Chromium Next GEM Single Cell 3’ Reagent Kits v3.1 (10x Genomics, 1000121) and the Chromium Next GEM Chip G Single Cell Kit (10x Genomics, 1000120). Libraries were pooled and sequenced on the Illumina NovaSeq 6000 system (read 1 = 28 bp, i7 index = 8 bp, i5 index = 0 bp, read 2 = 91 bp read configuration) targeting an average of 20,000 reads per nucleus.

### Single-nucleus multiome experiments
snMultiome experiments targeting 9,000 nuclei per sample were performed using Chromium Chromium Next GEM Single Cell Multiome ATAC + Gene Expression (10x Genomics, 1000283). ATAC (read 1 = 50 bp, i7 index = 8 bp, i5 index = 24 bp, read 2 = 49 bp read configuration) and RNA (read 1 = 28 bp, i7 index = 10 bp, i5 index = 10 bp, read 2 = 90 bp read configuration) libraries were sequenced separately on the Illumina NovaSeq 6000 system.

### Initial processing of single-nucleus data
Initial processing of scATAC-seq data was performed using the Cell Ranger ATAC Pipeline (https://support.10xgenomics.com/single-cell-atac/software/pipelines/latest/what-is-cell-ranger-atac) by first running cellranger-atac mkfastq to demultiplex the bcl files and then running cellranger-atac count to generate scATAC fragments files. Initial processing of snRNA-seq data was performed using the Cell Ranger Pipeline (https://support.10xgenomics.com/single-cell-gene-expression/software/pipelines/latest/what-is-cell-ranger) by first running cellranger mkfastq to demultiplex the bcl files and then running cellranger count. As nuclear RNA was sequenced, data were aligned to a pre-mRNA reference. Initial processing of the mutiome data, including alignment and generation of fragments files and expression matrices, was performed using the Cell Ranger ARC Pipeline.

### Colocalization analyses
The CODEX data were used to compute and compare the CLQ between all cell-type pairs in the small bowel versus the colon. The colocalization quotient between cell type A and cell type B was calculated using the expression 
 $`\left.\mathrm{CLQ}_{\mathrm{A} \rightarrow \mathrm{B}}=\frac{C_{\mathrm{A} \rightarrow \mathrm{B}} / N_{\mathrm{A}}}{N_{\mathrm{B}} /(N-1)} \text { (ref. }{ }^{81}\right)`$, where CA→B is the number of cells of cell type A among the defined nearest neighbours of cell type B. N is the total number of cells and NA and NB are the numbers of cells for cell type A and cell type B. Student’s t-tests, adjusted for multiple-hypothesis testing, were used identity statistically significant different CLQs between the small bowel and colon.


### Ligand and receptor analyses
The FANTOM5 database82 and 12 more literature-supported experimentally validated ligand and receptor pairs were used to obtain the final list of validated ligand receptor pairs83. Non-parametric Wilcoxon rank-sum tests were used to identify differentially expressed ligands and receptors in the small bowel versus the colon (adjusted P-value cut-off = 0.05).

### Quality control, dimensionality reduction and clustering of snATAC–seq data
The snATAC fragments files were loaded into R (v.4.1.2) using the createArrowFiles function in ArchR52. Quality-control metrics were computed for each cell and any cells with TSS enrichments less than 5 were removed. Cells were also filtered on the basis of the number of unique fragments sequenced using a unique fragment cut-off that was defined for each individual sample. The sample-specific cut-offs enabled us to account for differences in sequencing depth between samples and ranged from 1,000 to 10,000, with the most common cut-off being 3,000 fragments per cell. After quality control and filtering, doublet scores for all multiome cells and all non-multiome snATAC cells were computed using the ArchR function addDoubletScores with k = 10, knnMethod = “UMAP” and LSIMethod = 1. An ArchR project was then created and doublets were filtered with filterDoublets with a filter ratio of 1.2. A small number of snATAC samples did not separate into distinct clusters of expected cell types and were removed from downstream analysis. For the non-multiome scATAC cells, an IterativeLSI dimensionality reduction was generated using addIterativeLSI, with iterations = 3, sampleCellsPre = 25000, dimsToUse = 1:25 and varFeatures = 15000. Next, clusters were added with addClusters with resolution = 1.5, nOutlier = 20, seed = 1, sampleCells = 40000 and maxClusters = 40, and the resulting clusters were divided into groups on the basis of whether the cells exhibited high gene activity scores52, a measure of accessibility within and around a gene body, for known immune, stromal or epithelial marker genes.

### Quality control, dimensionality reduction and clustering of snRNA-seq data
After running Cell Ranger, the raw_feature_bc_matrix produced by Cell Ranger was read into R with the Seurat84 function Read10X. The data were filtered to remove nuclei with fewer than 400 unique genes per nucleus, greater than or equal to 10,000 genes per nucleus, greater than or equal to 20,000 counts per nucleus, or greater than or equal to 5% mitochondrial RNA per nuclei. To limit the contributions of ambient RNA, we also filtered out nuclei that did not have at least three times as many counts as the median number of counts in all droplets, which should reflect the median number of counts in an empty droplet, as the large majority of droplets are empty. This limits the fraction of RNA that can come from ambient RNA in droplets that are included in the dataset. DoubletFinder85 was run for each non-multiome snRNA sample using principal components 1–20. nExp was set to 0.076 × nCells2/10,000, pN to 0.25 and pK was determined using paramSweep_v3, and cells that were classified as doublets were removed before downstream analysis. snRNA data for both multiome and non-multiome cells was corrected for possible ambient RNA correction using DecontX86.

The remaining cells from all samples were merged into a single seurat object. The data was then processed using Seurat’s standard pipeline84. First, NormalizeData was run using the method LogNormalize and scale.factor of 10,000. Variable features were identified with Seurat’s findVariableFeatures using the vst method and 2,000 features. ScaleData was then run on all genes and principal components were computed with RunPCA. To account for batch effects between different donors in clustering, the RunHarmony87 function was run with the data being grouped by donor. RunUMAP was then used to generate a UMAP dimensionality reduction from the harmony reduction and the cells were clustered by first using FindNeighbors with reduction = “harmony” and dims = 1:20 and then FindClusters with a resolution of 1. Expression of marker genes in the resulting clusters was then used to label clusters as epithelial, stromal or immune for downstream analysis.

### Annotation of single-nucleus data
The snATAC and snRNA data were annotated in the following groups: epithelial duodenum, epithelial jejunum, epithelial ileum, epithelial colon, stromal and immune. The snATAC data were further divided into separate projects for multiome and nonmultiome cells and the RNA annotations were used for the multiome cells while the snATAC-only cells were annotated separately. For the ATAC data, the cells in each of these compartments were subset into a new ArchR project. addIterativeLSI was then run for each compartment. addHarmony was then run using the LSI dimensions as input. After computation of the harmony dimensions, the cells were clustered using addClusters and a UMAP was computed on the basis of the harmony coordinates using addUMAP. Clusters were annotated by examining gene activity scores of known marker genes. Marker genes were used for initial annotation of cell types including BEST4+ enterocytes (BEST4, OTOP2), goblet cells (MUC2, TFF1, SYTL2), immature goblet cells (KLK1, RETNLB, CLCA1), stem cells (RGMB, SMOC2, LGR5, ASCL2), tuft cells (SH2D6, TRPM5, BMX, LRMP, HCK), enteroendocrine cells (SCGN, FEV, CHGA, PYY, GCG), cycling transit-amplifying cells (TICRR, CDC25C) and Paneth cells (LYZ, DEFA5).

Within the immune compartment, we identified clusters of CD4+ and CD8+ T cells (CD2, CD3E, IL7R, CD4, CD8), B cells (PAX5, MS4A1, CD19), plasma cells (IGLL5, AMPD1), natural killer cells (SH2D1B), macrophages/monocytes (CD14) and mast cells (HDC, GATA2, TPSAB1) (Fig. 4c and Extended Data Fig. 6d). Natural killer cells and T cells from one donor clustered separately from the other T cells in the snRNA data (Extended Data Fig. 6e), possibly because this donor was much younger (24 years) than the others in this study (Supplementary Table 1). Smooth muscle/myofibroblast clusters exhibited high expression of ACTA2, MTH11 and TAGLN. Villus fibroblasts exhibited high expression of WNT5B and some crypt fibroblasts exhibited high expression of RSPO3.

For the snRNA cells, cells were divided into six Seurat objects from the compartments listed above. Cells from the immune and stromal compartments were run through a pipeline analogous to the pipeline listed above for initial clustering (NormalizeData, ScaleData, RunHarmony, FindNeighbors and FindClusters). For cells in the four epithelial groups, we integrated the data using a different approach, first running SCTransform on the epithelial cells from each sample with assay = “decontXcounts”, method = “glmGamPoi”, and vars.to.regress = c(“percent.mt”, “percent.ribo”). We then ran the Seurat functions SelectIntegrationFeatures with features = 3000, PrepSCTIntegration, FindIntegrationAnchors using reference-based integration and dims 1–30, and finally IntegrateData. We then ran RunPCA on the integrated data followed by FindNeighbors and FindClusters to cluster the resulting integrated data.

In addition to removing probable doublets based on simulating doublets as described above, we also identified clusters with expression of markers from multiple lineages (for example, stromal and immune) during downstream clustering and annotation. For example, some cells that initially clustered with immune cells expressed higher levels of stromal genes than would be expected. For these cases, we took the following approach: we first clustered all of the cells initially classified as immune cells and identified marker genes for each cluster. We next compared the marker genes to a previously published list of colon marker genes28 to nominate clusters that may not contain singlet immune cells. Next, we moved these cells to the stromal or epithelial compartments, in which we clustered them with all of the cells that were initially classified as epithelial or stromal cells. In this case, if the cells had high expression of immune marker genes when compared to stromal cells, we reasoned that they were most likely immune/stromal doublets and removed the cluster of cells before downstream analysis. After initial annotation of epithelial cells, enteroendocrine cells in the snRNA data from all samples were integrated according to the SCTransform-based integration approach by running SCTranform on all epithelial cells from all samples and integrating all epithelial cells using reference-based integration as described above. After integration of all cells, we subset only the enteroendocrine cells and then computed the principal components using RunPCA and identifyied clusters using FindNeighbors and FindClusters. Known subtypes of enteroendocrine cells were then annotated based on expression of marker genes (Fig. 4 and Extended Data Fig. 6h). To annotate the MUC6+, MUC5B+ and exocrine cells, we subset the integrated duodenum data and computed the principal components using RunPCA and identified clusters using FindNeighbors and FindClusters. Exocrine cells were annotated on the basis of expression of CELA3B and CPB1, and MUC5B+ and MUC6+ cells were annotated on the basis of expression of MUC5B and MUC6 (Fig. 4h). Comparisons in cell-type abundance between regions of the intestine were done using the packages scCoda29 and Milo30.

### Peak calling for single-nucleus data
Peak calling was performed with MACS2 using ArchR52. Peak sets were defined independently for epithelial cells, stromal cells and immune cells. For epithelial cells, we wanted to generate a union peak set that captured both cell-type-specific and location-specific peaks in the epithelial compartment. To accomplish this, we divided the cells into groups, generated pseudobulk replicates for each group, called peaks on the pseudobulk replicates, generated a reproducible peak set for each group using the peaks called for the pseduobulk replicates, and then iteratively merged the peak sets for each group into a union peak set using the approach implemented in ArchR. Groups used for epithelial peak calling were the cells from each epithelial cell type—with all enteroendocrine subtypes combined, and MUC5B+, MUC6+, exocrine and unknown cells combined—in the four main regions of the intestine. Tuft cells from the small intestine were merged into a single group owing to the low number of tuft cells in the dataset. For defining the immune and stromal peak sets, cells were divided by cell type, but not location, as there were fewer cells in these compartments. Finally, an additional peak set for all cell types in the immune, stromal and epithelial cell types was defined for determining marker peaks for linkage-disequilibrium score regression.

### Integration of snRNA and snATAC data
To assign snRNA profiles to the non-multiome snATAC samples, the snRNA and snATAC datasets from the four primary regions of the intestine (duodenum, jejunum, ileum and colon) were integrated separately using the ArchR function addGeneIntegrationMatrix with reducedDims = “Harmony” and useMatrix = “GeneScoreMatrix”.

### Nomination of regulatory TFs in single-nucleus data
We next identified TF regulators according to the ArchR manual for identifying TF regulators for each region, with a correlation cut-off of 0.5. TFs that met the criteria for regulators in any of the four primary regions of the intestine are plotted in Fig. 5b. This process was performed separately for the multiome datasets and the integrated singleome datasets. Cell types with few cells in each region of the intestine (for example, L cells) were combined into a single group regardless of location of origin, leading to the final cell type groupings on the x-axis of Fig. 5b. Regulators were identified separately for cells in the immune and stromal compartment with the final cell type groupings indicated on the x-axis of Extended Data Fig. 10g,h. TF footprints were computed using the ArchR functions getFootprints and plotFootprints.

### Analysis of absorptive differentiation trajectories in single-nucleus data
Absorptive differentiation trajectories for each main section of the colon (duodenum, jejunum, ileum and colon) were inferred by running the ArchR function addTrajectory with the trajectory set as harmony clusters moving from Stem to TA2 to TA1 to immature enterocytes to enterocytes and reducedDims set to the harmony dimensions. To identify variable peaks along the trajectory, a matrix of accessibility in all peaks along the trajectory was first generated with getTrajectory with useMatrix = “PeakMatrix” and log2Norm = TRUE. Peaks with variance > 0.9 in any of the four regions were then identified with the function plotTrajectoryHeatmap with varCutOff = 0.9, returnMatrix = TRUE, scaleRows = FALSE and maxFeatures = 100000. The four matrices returned by getTrajectory were then concatenated into a single matrix and the matrix was subset to include only peaks that met the variance criteria of 0.9 in at least one of the four regions and had an absolute difference in magnitude of at least 0.2. Row z-scores for the resulting matrix were computed using the ArchR function .rowZscore. The resulting row z-scores were k-means clustered using the function kmeans with the number of clusters set to 7 and iter.max = 500. Two clusters of peaks did not show a characteristic pattern and were not included in Fig. 6. Hypergeometric enrichment of motifs in marker peaks was computed with peakAnnoEnrichment and the resulting P values are plotted in Extended Data Fig. 10k. Variable genes along the trajectory were identified with an analogous method, using GeneExpressionMatrix for the multiome data or GeneIntegrationMatrix (for the separate snATAC and snRNA data) instead of PeakMatrix when running getTrajectory and plotTrajectoryHeatmap. For gene expression, log2Norm was set to TRUE when running getTrajectory and genes were filtered to include only those with an absolute difference in magnitude of at least 0.5. Row z-scores of the resulting matrices were again k-means clustered using the function kmeans with the number of clusters set to 7 and iter.max = 500. Enrichment of KEGG pathways in these clusters of genes was determined using the limma function kegga88, and the resulting unadjusted P values are plotted in Extended Data Fig. 10l. Plots of gene expression versus pseudotime were generated using the ArchR function plotTrajectory with the default parameters, including using imputeWeights added by addImputeWeights. TFs with correlated motif activity and RNA expression were identified with correlateTrajectories as outlined in the ArchR manual. The row z-scores of the smoothed expression of TFs along the pseudotime trajectories is plotted in Fig. 6d. TFs that were correlated with expression in any of the four trajectories were included in the heat map in Fig. 6d. Peaks correlated with gene expression were identified with addPeak2GeneLinks. In Fig. 6e, the set of peaks that were correlated with ETV6 expression with a correlation of at least 0.4 in one of the four main intestinal regions was determined. For TMPRSS15, a correlation cut-off of 0.55 was used to show the most correlated peaks in the figure. The smoothed trajectory peak accessibility for each of these peaks was then plotted along the differentiation trajectory. This process was performed separately for the multiome datasets and the integrated singleome datasets.

### Cell-type-specific linkage-disequilibrium score regression
Linkage-disequilibrium score regression is a method that aims to distinguish heritability from confounding factors such as population stratification and cryptic relatedness. To run cell-type-specific linkage-disequilibrium score regression, we first computed marker peaks for coarse cell types in our dataset. To do this, we added cell type annotations to the full ArchR project with all cells and then defined a peak set for this object by running addGroupCoverages with groupBy = “CellType” followed by addReproduciblePeakSet and addPeakMatrix. We next defined less granular cell types by merging all myofibroblast clusters and pericytes into a single group, all non-villus fibroblast clusters into a single group, all non-stem absorptive epithelial cells into a single group, cycling TA cells into a single group, all enteroendocrine cells except for EnteroendocrineUn into a single group, and lymphatic endothelial and endothelial cells into a single group. We determined marker peaks for the resulting groups of cells with getMarkerFeatures and ten selected peaks with getMarkers with cutOff = “FDR <= 0.1 & Log2FC >= 0.5”. Marker peaks from cell types with very few cells were not included (T cells, unknown, exocrine, secretory specialized MUC5B+, DC, ILC, adipocytes, neurons, EnteroendocrineUn) The resulting peaks were then lifted over to hg19 from hg38. We then followed the linkage-disequilibrium score regression tutorial (https://github.com/bulik/ldsc/wiki) for cell-type-specific analysis89,90,91. We used summary statistics from a number of UKBB traits (https://nealelab.github.io/UKBB_ldsc/downloads.html) related to the intestine, including non-cancer illness code;self-reported: crohns disease, non-cancer illness code;self-reported: ulcerative colitis, non-cancer illness code;self-reported: malabsorption/coeliac disease, BMI as well as traits less clearly related to the intestine including non-cancer illness code;self-reported: hypertension and diagnoses—main ICD10: K02 dental caries. Coefficient P values from ldsc are plotted in the heat map in Fig. 6. Significance was determined by correcting the coefficient P values for the number of cell types tested with Bonferroni correction with the R function p.adjust.

### Processing of single-nucleus data for ligand–receptor analysis and snRNA-CODEX integration
The ligand–receptor analysis and scRNA-seq CODEX integration were performed with an initial dataset consisting of samples from donors B001, B004, B005 and B006 before collection of the remaining data. This dataset was annotated similarly to the full dataset with the following differences. First, all analysis was carried out in R v.4.0.2. Second, the quality-control cut-offs used were slightly different, with the requirement to have three times as many RNA counts as an empty droplet not implemented in the initial dataset. Third, when running doubletFinder, pK was set as 0.09 instead of running paramSweep_v3. Fourth, scTransform was not used in the subclustering analysis for the epithelial compartments. Instead, Seurat’s standard normalize and scale pipeline followed by Harmony was run to compute an integrated dimensionality reduction that was then clustered using Seurat’s findNeighbors and FindClusters for the immune and stromal cells as well as the epithelial cells from the four main regions of the intestine. As the ligand–receptor analysis involved making predictions that we later attempted to validate using Molecular Cartography, this analysis could not be redone with the remaining dataset.

### Molecular Cartography validation of ligand–receptor pairs
Small intestine (duodenum) and colon (sigmoid/descending) samples from donors B004, B008 and B009 were analysed for spatial transcriptomics. The cryosections (thickness, 10 µm) from the same OCT-embedded tissue arrays were placed onto the glass slides provided by Resolve Biosciences for Molecular Cartography assay. The Molecular Cartography assay was performed by the Resolve Biosciences team with their optimized protocol ‘human colon v1.3’ and targeting a panel of total 100 transcripts of interest, including 63 genes from our ligand–receptor predictions (Supplementary Table 3) and 37 genes for cell type annotation (Supplementary Table 9). Segmentation was performed using DAPI signal with cellPose (https://github.com/MouseLand/cellpose; v.2.0.5) and followed by Baysor (https://github.com/kharchenkolab/Baysor; v.0.5.1). Gene counts were quantified per cell and cells were removed by area (<50 or >8,000 pixels) and total gene counts (<2). Manual cell type annotation was performed on the basis of the marker gene expression after Leiden clustering (Scanpy). As only 37 genes were used as cell type markers and the sample number (n = 6) is limited, only 20 cell types were identified in this dataset. To validate the ligand–receptor repair (Supplementary Table 3), we first match the cell type with snRNA-seq annotation. Only 58 out of 152 predictions have matching cell types. We compared ligand and receptor expression (log transformed) between the colon and small intestine in their predicated cell types (one sided Wilcoxon rank-sum test). P values were corrected for multiple testing using the Benjamin–Hochberg procedure. In total, 15 pairs have consistent higher expression in the colon compared with in the small intestine (both adjusted P < 0.05; Supplementary Table 6). Permutation tests were used to assess whether the success rate (15.5%, 9 out of 58) of our validation is higher than random. Gene labels were swapped and the same DEG procedure was repeated 10,000 times.

### snRNA-seq/CODEX single-cell matching and integrational analysis using MaxFuse

snRNA-seq cells and CODEX cells were matched and downstream integrative analysis was performed using MaxFuse, of which the methodology details were described previously41. In brief, MaxFuse is an algorithm that matches cells across different single-cell modalities by linear assignment, using both shared (when available) and unshared features, and implements signal boosting steps (for example, graph smoothing and meta cell construction) to enable matching cells across weakly correlated modalities (for example, RNA to protein). Although various methods are available for integration tasks on modalities with robust sharing information (such as scRNA/scATAC)84,92,93, when such tasks involve integration between protein and sequencing modalities, with much weaker shared features available (<60 versus thousands), a specialized method is needed94. We applied MaxFuse to match snRNA-seq cells to CODEX cells. Cells that were previously annotated as B, T, monocyte, macrophage, plasma, goblet, endothelial, enteroendocrine, smooth muscle and stromal cells were used during this integration process, whereas other cell types were not used owing to limited sharing information across modalities. Subsequently, a shared co-space was calculated to embed both modalities, with visualization of the embedding (first 20 MaxFuse-components) using UMAP. To evaluate single-cell matching performance across RNA to protein modality, we used cell type annotation accuracy (for example, a single CODEX plasma cell matched to a snRNA-seq plasma cell) as a proxy, and both CL and small bowel matching achieved >90% accuracy. Using the single-cell-level pairing information, we transferred the transcriptome expression profile to each individual CODEX cell, and subsequently performed analysis of the DEGs across various CODEX cellular neighbourhoods. The DEGs were selected with the function FindAllMarkers in the R package Seurat, with the parameters only.pos = TRUE, min.pct = 0.3, logfc.threshold = 0.25. The genes with adjusted P < 0.05 and shared across the CL and small bowel datasets were shown on the heat map. Gene Ontology enrichment analysis was performed for individual CNs with the DEGs, by using the PANTHER database. We have uploaded the code that we used to perform the MaxFuse matching for the snRNA-seq and CODEX datasets within the paper here (https://github.com/shuxiaoc/maxfuse/tree/main/Archive/hubmap_nature). This includes both the dataset preparation and analysis features of the code.

## Reporting summary
Further information on research design is available in the Nature Portfolio Reporting Summary linked to this article.

## Data availability
All of the datasets (snRNA-seq, snATAC–seq and CODEX) can be visualized and accessed through a website portal (https://portal.hubmapconsortium.org/). Our landing page links all of the raw dataset IDs and the HuBMAP ID for this Collection is HBM692.JRZB.356 and the DOI is https://doi.org/10.35079/HBM692.JRZB.356. Supplementary Table 10 also lists all of the dataset IDs within the HuBMAP portal where all raw datasets are stored that can be downloaded and also viewed in a processed state. We provide the processed fluorescence CODEX multiplexed image stacks (https://doi.org/10.5061/dryad.76hdr7t1p and https://doi.org/10.5061/dryad.gmsbcc2sq). We also provide processed, quantified and annotated single-cell CODEX datasets with labelled cell types, neighbourhoods, communities, tissue units and also protein expression at Dryad (https://doi.org/10.5061/dryad.pk0p2ngrf). Processed snRNA-seq and snATAC-seq datasets are available at https://doi.org/10.5061/dryad.8pk0p2ns8 and https://doi.org/10.5061/dryad.0zpc8672f. Unprocessed snRNA-seq and snATAC–seq datasets are available at dbGaP (phs002272.v1.p1). Source data are provided with this paper.

## Code availability
Code for analysis of the snATAC and snRNA data is available at GitHub (https://github.com/winstonbecker/scColonHuBMAP/), and code for processing CODEX multiplexed imaging data (https://github.com/nolanlab/CODEX)8, for clustering (https://github.com/nolanlab/vortex), for transferring cell type labels with STELLAR (https://github.com/snap-stanford/stellar), for neighbourhood analysis (https://github.com/nolanlab/NeighborhoodCoordination), for tissue schematics (https://github.com/nolanlab/TissueSchematics) and for MaxFuse (https://github.com/shuxiaoc/maxfuse) is available at GitHub.

## References



## Acknowledgements
We thank the patients for donating their tissues. This work was supported by the US National Institutes of Health (3U54HG010426; P50HG007735; U19AI057266; U01HG011762); Cancer Research UK (C27165/A29073); the Parker Institute for Cancer Immunotherapy (PICI0025); Hope Realized Medical Foundation (209477). J.W.H. was supported by an NIH T32 Fellowship (T32CA196585) and an American Cancer Society—Roaring Fork Valley Postdoctoral Fellowship (PF-20-032-01-CSM). S.A.N. was supported in part by the Stanford Graduate Fellowship and the NHGRI Stanford Genome Training Program 5 T32 000044. C.M.S. was supported by the Swiss National Science Foundation (P300PB_171189, P400PM_183915). Figs. 2g,i and 4a and Extended Data Figs. 1a, 2a and 6a were created using BioRender. We thank the members of the HuBMAP consortium for their many contributions to this project.


## Contributions
S.B. and C.M.S. developed the original CODEX panel and acquired the CODEX data from B001. J.W.H., S.B. and C.C. developed gut-specific CODEX antibodies and ran the remaining donor samples. V.V. helped to establish CODEX data-processing pipelines and integration with HuBMAP data transfers. M.B., K.C., J.W.H. and J.L. created STELLAR, which was used for cell type label transfer of the CODEX data. J.W.H. processed and analysed CODEX multiplexed imaging data. R.C., D.C., S.A.N., A.H. and W.R.B. established experimental protocols and collected the snRNA-seq and snATAC–seq data. A.E.P. and W.Z. analysed CODEX and snRNA-seq data for neighbourhood crosstalk. C.Z. and J.W.H. analysed the spatial transcriptomics dataset based on Molecular Cartography. B.Z., S.C., N.Z. and Z.M. integrated CODEX and snRNA datasets using MaxFuse. W.R.B. analysed snATAC–seq and snRNA-seq data. W.R.B., J.W.H., W.J.G. and M.S. wrote the manuscript and created figures. D.C. handled data management and submission to repositories. A.H., A.K.W. and E.M. were involved in project coordination. T.L. assessed morphological staining of samples. E.D.E. assisted in metadata annotation and biological interpretation. Y.L., Z.Z. and S.L. procured samples. Y.L., S.K.P., G.P.N., W.J.G. and M.S. supervised the study. All of the authors revised the manuscript and accepted its final version.

## Corresponding authors
Correspondence to Garry P. Nolan, William J. Greenleaf or Michael Snyder.

## Ethics declarations
## Competing interests
C.M.S. is a scientific advisor to, has stock options in and has received research funding from Enable Medicine. 10X Genomics holds the license to patents in which W.J.G. is listed as an inventor. W.J.G. is an equity holder of 10X Genomics, and a co-founder of Protillion Biosciences. W.J.G. consults for Guardant Health, Quantapore, Protillion Biosciences, Ultima Genomics, Lamar Health, and Erdio Biosciences. M.P.S. is a cofounder and an advisory board member of Personalis, Qbio, January AI, Mirvie, Filtricine, Fodsel, Protos, RTHM, Marble Therapeutics and Crosshair Therapeutics. G.P.N. received research grants from Pfizer, Vaxart, Celgene and Juno Therapeutics; and has equity in and is a scientific advisory board member of Akoya Biosciences. The other authors declare no competing interests.

## Peer review
Peer review information
Nature thanks Shalev Itzkovitz, Caroline Wählby and the other, anonymous, reviewer(s) for their contribution to the peer review of this work. Peer reviewer reports are available.

## Additional information
Publisher’s note Springer Nature remains neutral with regard to jurisdictional claims in published maps and institutional affiliations.

## Data availability
All of the datasets (snRNA-seq, snATAC–seq and CODEX) can be visualized and accessed through a website portal (https://portal.hubmapconsortium.org/). Our landing page links all of the raw dataset IDs and the HuBMAP ID for this Collection is HBM692.JRZB.356 and the DOI is https://doi.org/10.35079/HBM692.JRZB.356. Supplementary Table 10 also lists all of the dataset IDs within the HuBMAP portal where all raw datasets are stored that can be downloaded and also viewed in a processed state. We provide the processed fluorescence CODEX multiplexed image stacks (https://doi.org/10.5061/dryad.76hdr7t1p and https://doi.org/10.5061/dryad.gmsbcc2sq). We also provide processed, quantified and annotated single-cell CODEX datasets with labelled cell types, neighbourhoods, communities, tissue units and also protein expression at Dryad (https://doi.org/10.5061/dryad.pk0p2ngrf). Processed snRNA-seq and snATAC-seq datasets are available at https://doi.org/10.5061/dryad.8pk0p2ns8 and https://doi.org/10.5061/dryad.0zpc8672f. Unprocessed snRNA-seq and snATAC–seq datasets are available at dbGaP (phs002272.v1.p1). Source data are provided with this paper.

## Code availability
Code for analysis of the snATAC and snRNA data is available at GitHub (https://github.com/winstonbecker/scColonHuBMAP/), and code for processing CODEX multiplexed imaging data (https://github.com/nolanlab/CODEX)8, for clustering (https://github.com/nolanlab/vortex), for transferring cell type labels with STELLAR (https://github.com/snap-stanford/stellar), for neighbourhood analysis (https://github.com/nolanlab/NeighborhoodCoordination), for tissue schematics (https://github.com/nolanlab/TissueSchematics) and for MaxFuse (https://github.com/shuxiaoc/maxfuse) is available at GitHub.

## References
Boland, M. Human digestion—a processing perspective. J. Sci. Food Agric. 96, 2275–2283 (2016).


## Supplementary information

### Extended Data Fig. 1: CODEX mulitplexed imaging across the healthy human intestine reveals changes in cell composition and organization.
![](images/2024-02-08-14-20-39.png)
A) Schematic for how CODEX multiplexed imaging was performed on arrays of 4 different sections of either colon and small intestine from the same donor simultaneously. Image processing steps done to extract single-cell spatial data. B) An example CODEX fluorescent image of one region of the small bowel (SB) (1 of 64 tissue sections) for CODEX with 6/54 markers shown for one donor (scale bar = 1 mm and magnified insert = 100 µm) with C) accompanying cell type map following cell segmentation and unsupervised clustering. D-E) Stromal cell type percentages either as a percent of D) All stromal cells, or E) all cells restricted to the Muscularis Externa tissue unit. F) Immune cell type or G) epithelial cell type percentages either as a percent of all cells restricted to the Mucosa tissue unit. H) Percentage of CD57+ Enterocyte cells of all cell types across different areas samples from small intestine to colon. (for D-H: * p value< 0.05, ** p value< 0.01, *** p value < 0.001 by two-sided T test, n=8 donors). (All boxplots in figures are plotted as minimum, 25 percentile, median, 75 percentile, maximum, and outliers as points outside 1.5 the interquartile range). I) Cell map of a representative section (one of 8 donors) of the Duodenum that shows CD57+ Enterocyte presence in glands in the Submucosa where Enterocytes and TA cells are shown in dark grey and Smooth muscle cells in light grey (other cell types not shown) (scale bar = 500 µm). J-K) Quantification of the same-cell density that is measured as an average distance of its 5 nearest same-cell neighbours normalized by the maximal possible same-cell distance within the tissue (n = 64 tissue sections) for J) stromal and K) epithelial cell types. L) A representative cell type map (one of 64 tissue sections from 8 donors) with only plasma cells, CD8+ T cells, and M2 Macrophages shown (scale bar = 500 µm).
### Extended Data Fig. 2: Multicellular neighbourhood analysis of CODEX imaging data indicates conserved cellular structures across the intestine.
![](images/2024-02-08-14-22-10.png)
A) Neighbourhood analysis was done by taking a window across cell type maps and vectorizing the number of cell types in each window, clustering windows, and assigning clusters as cellular neighbourhoods of the intestine. B-D) Neighbourhood percentages from CODEX data averaged normalized by B) stromal, C) immune, and D) epithelial compartments. Asterix indicates p-value less than 0.05 difference in cell type percentage from the small bowel (SB) to the colon (CL) by two-sided T test. E) Stromal multicellular neighbourhood percentages either as a percent of all neighbourhoods restricted to the Muscularis Externa tissue unit (* p value< 0.05, *** p value < 0.001, n = 8 donors, by two-sided T test,). F) Quantification of the same-cell density for just smooth muscle cells within different smooth muscle multicellular neighbourhoods (x axis) (n = 32 tissue sections). G-H) Cell type maps for a region of the small intestine (one of 64 tissue sections imaged from 8 donors) with G) all cell types plotted for the whole tissue (scale bar = 500 µm), H) cells contained within the plasma cell neighbourhood (scale bar = 500 µm), and a magnified area of denoted by rectangle showing subset of cell types (scale bar = 50 µm). I) CODEX fluorescent imaging with subset of fluorescent markers overlaid for the same tissue as G (Hoechst=Blue, CD4=Green, CD68=magenta, CD38=yellow, CD206=cyan, CD138=grey), (scale bar = 500 µm with magnified insert scale bar = 100 µm).

### Extended Data Fig. 3: Change in multicellular neighbourhoods across the intestine.
![](images/2024-02-08-14-23-56.png)
A) Immune neighbourhood percentages as a percent of immune neighbourhoods. B) Neighbourhood percentages for Microvasculature and CD8+ T cell IEL neighbourhoods compared for donors with or without a history of hypertension (Microvasculature p value = 0.0065<, CD8+ T Enriched IEL p value = 0.0017 by two-sided T test, n = 3-5 donors). C) Difference in composition in neighbourhood by cell type for all neighbourhoods based on subtracting the log2 fold enrichment of each cell type found within that neighbourhood compared to average percentages in the tissue in SB from CL. Neighbourhoods and cell types are ordered by summing the absolute value of all rows and columns to denote conservation of a neighbourhood. D) 22 unique intestinal multicellular neighbourhoods (y axis of heatmap) were defined by enriched cell types (x axis of heatmap) as compared to overall percentage of cell types in the samples with 2 unique neighbourhoods not identified with overall neighbourhood analysis. E) Epithelial neighbourhood percentages as a percent of epithelial neighbourhoods from multicellular analysis performed on each individual region of the intestine separately. F) Immune neighbourhood percentages as a percent of immune neighbourhoods from multicellular analysis performed on each individual region of the intestine separately. (* p value< 0.05, ** p value< 0.01, *** p value < 0.001 by two-sided T test, n = 8 donors).

### Extended Data Fig. 4: Multi-neighbourhood community analysis of the intestine.

![](images/2024-02-08-14-25-22.png)
A) Community analysis was done by taking a window across neighbourhood maps and vectorizing the number of each neighbourhood type in each window, clustering windows, and assigning clusters as multi-neighbourhood communities of the intestine. 10 unique intestinal multi-neighbourhood communities (y axis of heatmap) were defined by enriched neighbourhood types (x axis of heatmap) as compared to overall percentage of neighbourhood types in the samples. B) Quantification of neighbourhood types across each section of the intestine (colour legend within panel A). C) Community percentages as a percent of all communities for small intestine and colon (* p value< 0.05, ** p value< 0.01, *** p value < 0.001, n = 8 donors). D) Concentric multi-neighbourhood analysis surrounding only neighbourhoods labelled as Paneth Cell Enriched neighbourhoods, with number of nearest neighbours for a given row in the heatmap.

### Extended Data Fig. 5: Multicellular neighbourhood and community interactions across the intestine.

![](images/2024-02-08-14-26-45.png)

A) Schematic of a representative community map and corresponding tissue community network graph (one of 64 tissues). B-C) Community-community motifs that are significantly enriched in both the small intestine and colon as compared to a null distribution of motif instances created from random permutation of tissue graph labels, where B) shows only those motifs that interact with the Adaptive Immune Enriched community and C) shows all other shared motifs between the SB and CL. Motifs indicated by shape and colour indicate those motifs that have significant p value versus those that are indicated with an x in the graph; p values were Bonferroni corrected by multiplying by twice the number of tests conducted in each comparison group. Colour legend is also the same as panel B. D) Representative neighbourhood map (one of 64 tissue sections from 8 donors) with (scale bar = 500 µm) E) Region magnified as in the main figure of the mucosal area of a colon community map, but this time with the multicellular neighbourhoods coloured (see panel D for legend) (scale bar = 100 µm). F) Spatial context maps of the CL highlighting relationships of multicellular neighbourhoods across just the neighbourhoods found within the tissue unit Mucosa. This structure is defined by the number of unique neighbourhoods required to make up at least 85% in a given window. Circles represent the number of cells represented by a given structure. Red rectangle highlights a structure discussed in the manuscript and maps this structure back to panel K. Colour legend is also the same as panel D. G-H) Cell type percentage of G) epithelial and H) stromal cells shown for each community ordered in relative order of general increasing proximity to the lumen based on community spatial context analysis.

### Extended Data Fig. 6: Quality control and clustering of single-nucleus data.

![](images/2024-02-08-14-28-53.png)
(a,b) Violin plots of TSS enrichment (a) and RNA counts/cell (b) for different samples included in the study. Samples are coloured by the location from which they were obtained. (c) UMAP projection of all snRNA cells coloured by location. (d) Dotplot representation of expression of immune marker genes by immune cell types. (e) UMAP projection of scRNA immune cells coloured by donor. (f) Dotplot representation of expression of stromal marker genes by stromal cell types. g) Sub-clustering of enteroendocrine cells from all regions of the intestine. h) Dotplot representation of the expression of subtype specific enteroendocrine and enterochromaffin marker genes in different enteroendocrine cell types in our datasets. I) Sub-clustering of specialized secretory cells coloured by sample.

### Extended Data Fig. 7: Differential cell type abundance.

![](images/2024-02-08-14-30-31.png)
a–c) Beeswarm plot showing the log-fold change between the three main regions of the small intestine and colon for groups of nearest neighbour cells from different cell type clusters in the stromal (a), immune (b), and epithelial (c) compartments computed with Milo. Significant changes are indicated in colour. d) Boxplots comparing the fraction of all cells in each sample composed of each cell type for samples from the colon, ileum, jejunum, and duodenum. e) Log2FC in abundance of each cell type between the regions listed on the y-axis as estimated with scCODA. Only significant results at an FDR of 0.05 are shown, with all nonsignificant differences plotted as white.

### Extended Data Fig. 8: Pairing of CODEX multiplexed imaging and snRNA-seq for cell-cell colocalization analysis.

![](images/2024-02-08-14-31-36.png)

a) Expression of B3GAT1 and four CEACAM transcripts plotted on the UMAP manifold of epithelial cells from the duodenum, jejunum, ileum, and colon. b) Dotplot representation of the expression of B3GAT1 and four CEACAM transcripts by different epithelial cell types in different regions of the intestine. c) Large colon (CL) and small bowel (SB) show differences in cell-cell co-localization patterns; annotated cell-pairs are more colocalized in the colon compared to the small bowel (Student’s T test, two-sided, corrected for multiple hypothesis testing with the Benjamini Hochberg procedure). d) SEMA4D ligand expression in plasma cells and MET receptor gene expression in TA2 cells, showing higher expression in colon than small bowel (one-sided Wilcoxon Rank-Sum Test). e) Differences in pairwise cell-type colocalization patterns across tissue locations (n = 3 samples for each location).

### Extended Data Fig. 9: Integration of snRNA-seq and CODEX datasets.
![](images/2024-02-08-14-33-09.png)
a) Average MET expression for all TA cells from a given donor and average SEMA4D expression for all plasma cells from a given donor. b) PLXNA2, RASA1, and MAP2K5 expression in TA2 cells in large colon (CL) and small bowel (SB) (one-sided Wilcoxon Rank-Sum Test). c) Representative image of a donor’s transverse colon with plasma cells (red), TA cells (blue), and other cell types (grey) highlighted with also a magnified area indicated with rectangle. (left scale bar = 500 µm; right scale bar = 100 µm) d) Example of receptor ligands expressed at higher levels in the colon than the small intestine (SI) for the FN1 by myofibroblast and PLAUR by enterocyte. e) Colocalization quotient (CLQ) for all cell types found within the follicle community. f) Heatmap of differentially expressed genes (from MaxFuse matched snRNA-seq cells) among individual CODEX cells, grouped based on previously determined cellular neighbourhoods from CODEX analysis. g) Gene Ontology Enrichment analysis for cellular neighbourhoods “inner folliclle” and “outer folliclle”, based on the differentially expressed genes shown in f.

### Extended Data Fig. 10: Regulatory TFs in the intestine.

![](images/2024-02-08-14-34-28.png)

a) Hypergeometric p-values of selected TF motifs in differential peaks between colon stem cells and stem cells from other regions of the intestine. Colour represents the log10 adjusted p-value computed with ArchR. b) Violin plots of motif deviation scores for FOXA3 for goblet cells, immature goblet cells, stem cells, and enterocytes in different regions of the intestine. c) Dotplot representation of expression of different transcription factors in goblet cells, immature goblet cells, stem cells, and enterocytes in different regions of the intestine. d) TF motif footprints for POU2F3 in proximal jejunum tuft cells and enterocytes. e) TF motif footprints for ATOH1 in duodenum goblet cells and enterocytes. Error bands in d and e represent the standard deviation. f) Overlap of epithelial regulators identified with the multiome data and separate snRNA and snATAC datasets.(g, h) Heatmap representation of transcription factors whose integrated gene expression was correlated with their motif activity in one region of the intestine for immune (g) and stromal (h) cell types. Row z-scores of ChromVar deviation scores are shown on the left and row z-scores of integrated TF expression are shown on the right. i, j) Overlap of immune (i) and stromal (j) regulators identified with the multiome data and separate snRNA and snATAC datasets. k) Hypergeometric p-values of TF motifs enriched in the clusters of peaks identified in b. l) Enrichment of KEGG pathways in the clusters of genes identified in c. Uncorrected p-values as determined by kegga are plotted. (m–o) Integrated gene expression of MTTP (m) and SCNN1B (n) and LGR5 (o) along the differentiation trajectory. (p) Accessibility at peaks correlated with the expression of TMPRSS15 along the differentiation trajectory in each region is plotted on the left. Each peak is normalized to the maximum accessibility along any of the trajectories. Integrated gene expression of TMPRSS15 along the differentiation trajectory in each region is plotted on the right.


## Supplementary Discussion

Aberrations in cellular density have been associated with disease states such as inflammatory
bowel disease (IBD). As the intestine is the largest immune organ in the body21, evaluating
immune cell localization and cellular interactions in the gut is critical for understanding oral
vaccine design22, interactions regulating the gut microbiota23, regulation of allergic food
responses24, axes critical for wound repair25, and immune system responses and
immunotherapies for cancer26–29. We observed that plasma cells have one of the highest samecell densities within the intestine. Plasma cells require a special niche for survival in the bone
marrow85 with survival factors such as CD44, a proliferation-inducing ligand (APRIL), IL-6, and
SDF-185,86. Localization of plasma cells is critical in gut-associated lymphoid tissue, playing an
important role in immunity by secreting IgA antibodies, the most abundantly produced
antibody, critical for maintaining a homeostatic relationship with microbiota and food
antigens83,84. We found the plasma cell enriched neighborhood form an important crossroads of
several other immune and epithelial neighborhoods within the mucosa. We also found plasma
cells colocalized with antigen-presenting cells, sources of APRIL, which drives ectopic germinal
center formation and plasma cell infiltration in cases of inflammation32. Collectively, these
observations suggest a role for antigen-presenting cells in curating a subepithelial niche for
plasma cells in the intestine in addition to transit amplifying epithelial cells.
CD8+ T cells are critical for antiviral cytotoxic function and were one of the few cell types
defined within the CODEX data shown to decrease from the small intestine to the colon. This
compositional change likely reflects differences in antigen availability from both initial exposure
as well as greater access to food antigens and foreign material with less mucus-secreting cells
as compared to the colon33,88 that may also be a cause for increased DCs we see within the
colon. Dysregulation of CD8+ T IEL cells is associated with IBD and celiac disease. And the
identification of CD8+ T IEL neighborhood further confirms the phenotypic distinction of IEL
CD8+ T cells from the rest of CD8+ T cells within the intestine and merits additional study to
understand maintenance, regulation, and renewal89 of these cells. Finally, studying changes in T
cell percentages within the gut in patients with hypertension may provide cell type mechanisms
for associations of hypertension with other diseases such as colon cancer93,94. Indeed, CD8+ T
cells presence and density correlate with beneficial anti-cancer outcomes90 and cancer rates are
increased within the colon as compared to the small intestine91,92. It will be interesting to
explore this correlation in the future and understand if intraepithelial immune cells help prune
defective epithelial cells.
CD4+ T cells are involved both in CD4+ T cell support of B cell and CD8+ T cell activation. We
found that CD4+ T cells were broadly distributed and enriched in all immune-rich multicellular
structures (innate immune enriched, inner follicle, outer follicle, adaptive immune enriched, and
plasma cell enriched) characteristic of their supportive functions. Consequently, the broad
involvement of CD4+ T cells in diverse immune multicellular structures suggests their
modulation might be akey therapeutic target for regulating immune responses in the intestine.
Integration of CODEX and snRNAseq at the single-cell level enabled analysis of the inner follicle
neighborhood gene expression where we see differential expression of genes involved in active
immune responses. Further understanding gene expression by location and validation with
spatial transcriptomics will be important to clarify functional differences, development, and
maintenance, as follicles are associated with beneficial cancer outcomes, increased
autoimmunity, and clearance of infection10,87.
Interestingly, we are able to find major structures of the intestine by common neighborhood
analysis, but also are able to identify differences in the cellular makeup of these
neighborhoods. We investigated this more broadly to see which neighborhoods and cell types
within these neighborhoods were conserved as defined by common cell type enrichment scores
between the small and large intestine. One of the cell neighborhoods that were most
differential were the intestinal crypt cellular neighborhoods. We also observed CD4+ T cells and
CD8+ T cells enriched at the base of the crypt with the stem cell zones of the small intestine and
colon. Understanding the colocalization with the crypt, interactions with stem cells, and
signaling to other stromal cells will be important to learn how the role these cells play in this
curated microenvironment.
We generated a spatially hierarchical description of the intestine that is derived from the cell
type labels we generate in our CODEX multiplexed imaging data. The first level we computed
was the immediate cellular neighborhoods within the tissues by examining conserved cell type
composition within ten nearest neighbors of cells10. These represented and identified
microstructures found within the intestine such as the vasculature or immune follicles. We
further built upon the neighborhood concept to understand how neighborhoods of cells are
interacting with each other and tend to colocalize. We quantitatively characterized these within
communities of multicellular structures which can be further categorized into major tissue
units. This categorization isolated mucosal areas of the tissue enriched with immune and
epithelial cells and defined overall structures and interactions of multicellular neighborhoods in
comparing the colon and small intestine. Using this hierarchical description of the intestine we
were able to capture the spatial layering of the intestine from the muscularis mucosa to the
lumen of the intestine.
Leveraging paired transcriptome and chromatin accessibility data, we achieved further
granularity to define the diversity of cell types in the intestine. Overall, different regions of the
colon exhibited highly concordant cell type abundances. However, the cell type compositions of
the small intestine regions were more diverse as compared to the colon, with the ileum often
exhibiting immune and stromal cell type fractions shared between the small intestine regions
and the colon. We observe greater diversity of specialized epithelial cells, including
enteroendocrine and mucin-secreting cells in the small intestine. Within all regions, we
identified goblet cells with high expression of MUC2. However, in the duodenum we identified
an additional cluster containing cells characterized by high expression of the gel forming mucin,
MUC6. The MUC6 cluster may represent cells of the duodenal Brunner’s glands, which have
been shown to express high levels of MUC651.
We also further improved our analysis of the data by integrating the molecular detail of the
snRNAseq and the spatial detail of the CODEX multiplexed imaging datasets at the single cell
level. While various computational tools are available to integrate single cells across sequencing
modalities49–51, integration involving protein modalities, especially spatial-proteo modalities like
CODEX, remain challenging. This is mostly due to the fact that protein modalities have limited
shared features and therefore is an information bottleneck (~30-60 shared features vs >1000
available across sequencing modalities). To solve this, we implemented with MaxFuse
(manuscript in preparation), a method we specifically designed towards such challenging
integration tasks: linear assignment coupled with graph smoothing and meta cell construction.
This works on both weakly correlated-shared features and non-shared features and was used to
generate single-cell level pairing information across CODEX and snRNAseq datasets that
allowed us to evaluate differential gene expression across cellular neighborhoods.
This work follows and extends the work of several scRNA gut atlases, including an atlas of the
small intestine in mice (Nature 2017) and two recent atlases describing the small and large
intestine in humans (Nature 2021, Cellular and Molecular Gastroenterology and Hepatology
2022). The first of these human studies additionally provides information on intestinal
development in addition to mapping cell types and features of the adult human intestine. Our
work supports many of the findings in these previously published atlases. For example, the two
recent human gut atlases both identified Best4+ enterocytes, first identified in the colon
(Smillie et al 2019), in human small intestine and large intestine, which we observe in our data
as well.
Chromatin accessibility data also allow assessment of the cell-type specific enrichment with
regulatory elements of common genetic variation linked to prevalent intestinal diseases (e.g.
GWAS hits) such as Celiac, ulcerative colitis, and Crohn’s disease. This analysis can nominate the
specific cell types through which these GWAS hits may be functioning, as well as the cell types
that may be driving disease etiology. We find that T cells are most enriched in the autoimmune
conditions, Celiac disease, ulcerative colitis, and Crohn’s. We also find that heritability of BMI is
enriched in enteroendocrine cells, suggesting that variation in BMI is likely partially driven by
genetic variation in regions that are functional in intestine enteroendocrine cells. Regardless,
overall we can assign heritability of specific diseases to specific intestinal cell types. 

### Reporting Summary
Supplementary Figures
Supplementary Figs. 1–12 and their figure legends.

![Alt text](image.png)
Supplemental Figure 1: CODEX multiplexed imaging of first donor B001 for small intestine and colon samples. A) 44 marker antibody base panel used for imaging. B) CODEX imaging of one of the 8 different sites taken from the colon for B001, with 5/44 markers shown (scale bar = 500 µm). Four zoomed in regions (scale bar = 100 µm) with various 5 color combinations of markers from the larger image (denoted by colored outline) with also an H&E image shown for the tissue. C) Multicellular neighborhood map for the same region with both cell type and neighborhood maps zoomed in around immune follicle regions. Representative image taken here is one of 8 taken from donor B001. 


![](images/2024-02-08-14-41-08.png)
Supplemental Figure 2: Cell type maps for all 8 regions imaged. For donor 1 (B001) of the small intestine and colon (scale bar = 1 mm). 

![](images/2024-02-08-14-42-22.png)
Supplemental Figure 3: Determination of multicellular neighborhoods in CODEX multiplexed imaging for donor 1 across all 8 regions. A) Cell type enrichment score within each neighborhood as represented in the heatmap. B) Cell type mapped back to each individual sample imaged (scale bar = 1 mm).

![](images/2024-02-08-14-43-11.png)
Supplemental Figure 4: CODEX multiplexed imaging with expanded 54 antibody CODEX panel. A) One region of B004 (total of 8) shown with 6 markers shown (Vimentin, CD3, aSMA, CD45, Cytokeratin, and CD31) (scale bar = 500 µm) B) Zoomed in regions with 6 markers each shown for the region highlighted (yellow box) in A with additional markers added to the panel highlighted (scale bar = 100 µm). C)  Cell type by marker heatmap normalized both by column and row to show markers which define cell types from CODEX multiplexed imaging for samples B004,5,6. 


![](images/2024-02-08-14-43-54.png)
Supplemental Figure 5: Cell type maps for all 8 regions imaged. For donors A) B004, B) B005, and C) B006 of the small intestine and colon (scale bar = 1 mm).

![](images/2024-02-08-14-45-19.png)
Supplemental Figure 6: Quantification of cell type percentages for all donors (n=8, error bars indicate standard deviation). A) Cell type percentage separated by donor. B) Cell type percentage grouped by location in the intestine. C) Cell type percent summation graph by location in the intestine with all cell types shown.

![](images/2024-02-08-14-45-57.png)
Supplemental Figure 7: Cell type percentages as determined by CODEX multiplexed imaging. A) Immune cell type percentages as a percent of all immune cells. B) Percentage of CD8+ T cells of all cell types across different areas samples from small intestine to colon. C) Heatmap of p values from Tukey post-test after a significant difference was found using a one-way ANOVA for the percent of CD8+ T cells across different areas of the small intestine and colon. D) Epithelial cell type percentages as a percent of all epithelial cells. E) Heatmap of p values from Tukey post-test after a significant difference was found using a one-way ANOVA for the percent of CD8+ T cells across different areas of the small intestine and colon.  F) Power analysis for cell types that were significantly different from the small intestine to the colon using a power of 0.8 and alpha of 0.05. (* p value< 0.05, ** p value< 0.01, *** p value < 0.001, n=8 donors, by two-sided T test). All boxplots in figures are plotted as minimum, 25 percentile, median, 75 percentile, maximum, and outliers as points outside 1.5 the interquartile range.

![](images/2024-02-08-14-47-46.png)
Supplemental Figure 8: Multicellular neighborhood percentage analysis from CODEX multiplexed imaging data of the intestine. A) Stromal multicellular neighborhood percentages as a percent of all stromal neighborhoods. B-C) Heatmap of p values from Tukey post-test after a significant difference was found using a one-way ANOVA for the percent of B) CD8+ T cell IEL neighborhood and C) Plasma Cell Enriched neighborhood across different areas of the small intestine and colon.  D) Percentage of Plasma Cell Enriched neighborhood of all neighborhoods across different areas samples from small intestine to colon. E) Heatmap of p values from Tukey post-test after a significant difference was found using a one-way ANOVA for the percent of Adaptive Immune Enriched neighborhood. F)  Percentage of Adaptive Immune Enriched neighborhood of all neighborhoods across different areas samples from small intestine to colon. (* p value< 0.05, ** p value< 0.01, *** p value < 0.001 by two-sided T test, n=8 donors).

![](images/2024-02-08-14-48-29.png)
Supplemental Figure 9: Changes in neighborhood composition from the small bowel (SB) to colon (CL). A) Cell type percentage and B) multicellular neighborhood percentage for each follicle region segmented out from individual sections (11/64) imaged by CODEX multiplexed imaging. C) Epithelial neighborhood percentages as a percent of epithelial neighborhoods. D) Power analysis for multicellular neighborhoods that were significantly different from the small intestine to the colon using a power of 0.8 and alpha of 0.05. (* p value< 0.05, ** p value< 0.01, *** p value < 0.001 by two-sided T test, n=8 donors).

![](images/2024-02-08-14-49-19.png)
Supplemental Figure 10: Overall tissue unit represented on all 8 sections. From donors B008-B012 (scale bar = 100 µm)


![](images/2024-02-08-14-49-52.png)
Supplemental Figure 11: Graph of multi-level structure of the tissue as broken down by the different structures. Shapes correspond to structural level, colors represent individual categories, size of shapes represents the percent contribution to tissue, and the size of connected lines represents the overall contribution to the next level of structure as moving down the graph in increasing tissue structural hierarchy. These are separated either by small bowel (SB) or colon (CL).

![](images/2024-02-08-14-50-29.png)
Supplemental Figure 12: Multi-community interaction motifs highlight organization of communities within the intestine. A-B) Community-community motifs that are significantly enriched as compared to a null distribution of motif instances created from random permutation of tissue graph labels, where A) shows motifs that are significant in the colon and B) shows motifs that are significant in the small bowel (p values were Bonferroni corrected by multiplying by twice the number of tests conducted in each comparison group).

### Supplementary Table 1
Donor-specific metadata. Metadata such as age, sex, race, BMI, histories of diabetes/cancer/hypertension/gastrointestinal disease are listed for each donor.
![](images/2024-02-08-14-52-15.png)

### Supplementary Table 2
The relationship between CODEX and scRNA-seq cell type nomenclature. Mapping of cell type label for both with following symbols: an asterisk (*) indicates that the class is not well defined; a plus (+) indicates that the cell type is not identified in snRNA or in CODEX
![](images/2024-02-08-14-53-53.png)

### Supplementary Table 3
Ligand–receptor pairs colocalized cells in the large colon with the number of times occurring across samples and the percentage appearing in other cell–cell pairs. The uniqueness of ligand–receptor pairs across colocalized cells in the large colon with listed pairs of ligands, respective cell–cell pairs, n times and the percentage seen across samples.
![](images/2024-02-08-14-56-19.png)
![](images/2024-02-08-14-56-50.png)


### Supplementary Table 4
KEGG significant pathways from upregulated genes in the colon associated with MET receptor. This included the ID, description, gene ratio, P values and adjusted P, with the counts.
![](images/2024-02-08-14-58-57.png)

### Supplementary Table 5
Molecular-cartography-validated cell–cell pairs with expressed ligand–receptors expressed within the colon. This includes the CLQ score for each cell type expressing the pair within the molecular cartography dataset, the tissue it came from, cell type names and the ligand–receptor pairs.
![](images/2024-02-08-15-00-13.png)

### Supplementary Table 6
Molecular Cartography-validated receptor–ligand expression higher in the colon than small intestine. A list of the ligand–receptor pairs and which cell type each pair is expressed on with the adjusted P value for greater expression.
![](images/2024-02-08-15-01-21.png)

### Supplementary Table 7
Detailed information for CODEX multiplexed imaging antibodies used herein. A list of names, RRID, UniProt, lot, dilution, conjugation format and tag and validation used.
![](images/2024-02-08-15-02-23.png)

### Supplementary Table 8
Detailed microscopy metadata for the CODEX multiplexed imaging data acquired herein. This is information that is ingested for HuBMAP processing and standardization of imagin
![](images/2024-02-08-15-03-16.png)

### Supplementary Table 9
Processed molecular cartography data with associated cell type labels.


### Supplementary Table 10
HuBMAP identifiers that can be used within the HuBMAP portal to access all data used within this study. This links the donor (listed within the manuscript and processed data) with HuBMAP donor IDs with associated organ piece nomenclature and raw dataset IDs for accessing from the HuBMAP portal.



## Rights and permissions
Open Access This article is licensed under a Creative Commons Attribution 4.0 International License, which permits use, sharing, adaptation, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons licence, and indicate if changes were made. The images or other third party material in this article are included in the article’s Creative Commons licence, unless indicated otherwise in a credit line to the material. If material is not included in the article’s Creative Commons licence and your intended use is not permitted by statutory regulation or exceeds the permitted use, you will need to obtain permission directly from the copyright holder. To view a copy of this licence, visit http://creativecommons.org/licenses/by/4.0/.

## Reprints and permissions

About this article
Check for updates. Verify currency and authenticity via CrossMark
Cite this article
Hickey, J.W., Becker, W.R., Nevins, S.A. et al. Organization of the human intestine at single-cell resolution. Nature 619, 572–584 (2023). https://doi.org/10.1038/s41586-023-05915-x

Download citation

Received
29 November 2021

Accepted
02 March 2023

Published
19 July 2023

Issue Date
20 July 2023

DOI
https://doi.org/10.1038/s41586-023-05915-x

Share this article
Anyone you share the following link with will be able to read this content:

Get shareable link
Provided by the Springer Nature SharedIt content-sharing initiative

Subjects
Functional genomics
Gene regulation
Multicellular systems
Single-cell imaging
This article is cited by
Cell ‘atlases’ offer unprecedented view of placenta, intestines and kidneys
Heidi Ledford
Nature (2023)

Single-cell genomics: the human biomolecular and cell atlases
Yuqing MeiJingjing WangGuoji Guo
Signal Transduction and Targeted Therapy (2023)

Decoding the tumor microenvironment with spatial technologies
Logan A. WalshDaniela F. Quail
Nature Immunology (2023)

MaxFuse enables data integration across weakly linked spatial and single-cell modalities
Nature Biotechnology (2023)

Cell-level reference maps for the human body take shape
Roser Vento-TormoRoser Vilarrasa-Blasi
Nature (2023)

## Comments
By submitting a comment you agree to abide by our Terms and Community Guidelines. If you find something abusive or that does not comply with our terms or guidelines please flag it as inappropriate.