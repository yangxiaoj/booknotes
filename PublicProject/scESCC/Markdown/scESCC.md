

``` bash

# 直接进入  session


tmux attach -t scESCC_Anna


``` 


*******


``` python

# 激活conda环境



source activate scRNA


```

``` python

# 进入python环境


ipython


```

``` python 


# 加载项目所需要的包




from re import sub
import scvi
import scanpy as sc
import numpy as np
import pickle
import os
import pandas as pd
import logging
import anndata as ad
import seaborn as sns


import time
import os, wget





```

``` python 

# 测试GPU是否能用




# check if GPU is available
import torch

if torch.cuda.is_available():
    print("GPU is available")
else:
    print("GPU is not available")
print(torch.cuda.is_available())

# print gpu name
print(torch.cuda.get_device_name())



```



``` python 

# 切换目录

def change_work_directory(dir):

    # check if dir is an absolute path
    if not os.path.isabs(dir):
        logging.error(f"{dir} is not an absolute path!")
        return

    if not os.path.exists(dir):
        os.makedirs(dir)
    else:
        logging.info(f"{dir} already exists, no need to create it.")
    
    os.chdir(dir)
    
    logging.info(f"Change to the directory: {dir}")






```

``` python


# 加载adata

change_work_directory("/mnt/mydisk/scESCC/scESCC/Analysis/Results/Global")

esca_query_adata = pickle.load(open("/mnt/mydisk/scESCC/scESCC/Analysis/Results/Global/SingleR/esca_query_level1_adata.pkl", "rb"))

esca_query_adata.obs["level1"].value_counts()

esca_query_adata.obs["study"].value_counts()


```


``` python

# 随机抽取10000个细胞 



sub_adata = esca_query_adata[np.random.choice(esca_query_adata.obs.index, 10000, replace=False)]




```


如何查看sub_adata中有多少样本?

``` python

# 如何查看sub_adata中有多少样本

    
sub_adata.obs["study"].value_counts()


```


``` python 

# 万能测试方法


# 输入: sub_adata代表一个scanpy的adata对象，其中有一个字段是sample_id; 输出: 我希望知道这个字段中有多少个不同的值


sub_adata.obs["sample_id"].value_counts()



``` 

``` python 

# 如何查看sub_adata 都有哪些数据

sub_adata


``` 

self test

``` python 

# 如何查看sub_adata中含有多少group_id

    
sub_adata.obs["group_id"].value_counts()


```



******



## 测试函数使用


``` python




``` 
















加载global的adat文件是存储为pickle格式的文件

这里的adata 文件路径是`/home/cuis/common/projects/IBDNanostring/RawData/scESCC/Analysis/Results/Global/SingleR/esca_query_adata.pkl`

``` python



# 切换到工作目录下

os.chdir('/common/cuis/projects/IBDNanostring/RawData/scLIHC/AnnaProjects/scESCC/Results')



# 加载adata文件

esca_query_adata = pickle.load(open("/home/cuis/common/projects/IBDNanostring/RawData/scESCC/Analysis/Results/Global/SingleR/esca_query_adata.pkl", "rb"))




```

查看文件

``` python

file_size = os.path.getsize('/home/cuis/common/projects/IBDNanostring/RawData/scESCC/Analysis/Results/Global/SingleR/esca_query_level1_adata.pkl')

print(f"""File size is {file_size / 1024 / 1024 / 1024} GB""")

```

``` python

esca_query_adata.obs['study'].value_counts()



```
``` python


esca_query_adata.obs['study'].nunique()


```

查看`group_id`的内容

``` python

esca_query_adata.obs['group_id'].value_counts()

```

查看`study`的内容

``` python

esca_query_adata.obs['study'].value_counts()

```

请获取adata对象的obs的列名

``` python

    
esca_query_adata.obs.columns


```

请获取study列的信息

``` python

    
esca_query_adata.obs['study'].value_counts()

    
```

******



### 画umap图

按sutdy画umap图



``` python

def plotEnhancedUMAPV02(adata, 
                        obs_field_name,
                        output_prefix,
                        color_palette = None, # {"PoorSurvival": "tab:red", "Others": "tab:grey"},
                        point_size = 10,
                        fig_width = 15,
                        fig_height = 15):
    import scanpy as sc
    import matplotlib.pyplot as plt

    with plt.rc_context({"figure.figsize": (fig_width, fig_height), "figure.dpi": 600, "figure.frameon": False}):
        sc.pl.umap(adata,
                color=obs_field_name,
                size=point_size,
                show=False,
                legend_loc="right margin",
                legend_fontoutline=2,
                legend_fontsize=32,
                frameon=False,
                title = "",
                palette=color_palette,
                save = f"_{output_prefix}_enhancedUMAPV02_umap.png")

    with plt.rc_context({"figure.figsize": (15, 15), "figure.dpi": 600, "figure.frameon": False}):
        sc.pl.umap(adata,
                color=obs_field_name,
                size=point_size,
                show=False,
                legend_loc="right margin",
                legend_fontoutline=2,
                legend_fontsize=32,
                frameon=False,
                title = "",
                palette=color_palette,
                save = f"_{output_prefix}_enhancedUMAPV02_umap.pdf")

```


``` python

os.chdir('/common/cuis/projects/IBDNanostring/RawData/scLIHC/AnnaProjects/scESCC/Results')

esca_adata = pickle.load(open("/common/cuis/projects/IBDNanostring/RawData/scESCC/Analysis/Results/Global/scANVI/esca_scANVI_adata.pkl", "rb"))

# PRJCA016745    
# GSE145370      103356
# GSE53624        96123
# GSE222078       66970
# GSE160269
#E41A1C", "#377EB8", "#4DAF4A", "#984EA3" "#FF7F00"

plotEnhancedUMAPV02(adata= esca_adata,
                        obs_field_name="study",
                        output_prefix= "ESCCbystudy",
                        color_palette = {"PRJCA016745": "#E41A1C", "GSE145370": "#377EB8", "GSE53624": "#4DAF4A", "GSE222078": "#984EA3", "GSE160269": "#FF7F00"},
                        point_size = 10,
                        fig_width = 15,
                        fig_height = 15)



```



****

study细胞数量

``` python



def plotCellNumberBarPlotByGroup(adata, 
                                 groupby,
                                 prefix,
                                 color_palette = {}, # {"PHT": "#E41A1C", "LRT": "#377EB8"}
                                 xlab_text = "",
                                 ylab_text = "Cell Number",
                                 fig_width = 10,
                                 fig_height = 5):


    import diopy
    import anndata as ad
    import scanpy as sc

    # create directory named cell_number_barplot_by_group
    os.makedirs("cell_number_barplot_by_group", exist_ok = True)
    os.chdir("cell_number_barplot_by_group")
    
    adata = ad.AnnData(X=adata.X, obs=adata.obs, var=adata.var)
    
    nature_colors = ["#E41A1C", "#377EB8", "#4DAF4A", "#984EA3",
                     "#FF7F00", "#FFFF33", "#A65628", "#F781BF",
                    "#999999", "#E7298A", "#66C2A5", "#FC8D62",
                    "#8DA0CB", "#E78AC3", "#A6D854", "#FFD92F",
                    "#E5C494", "#B3B3B3", "#8DD3C7", "#BEBADA",
                    "#FB8072", "#80B1D3", "#FDB462", "#B3DE69"]


    if len(color_palette) == 0:
        color_palette = "c(" + ", ".join([f'"{k}" = "{v}"' for k, v in zip(adata.obs[groupby].unique(), nature_colors)]) + ")"
    else:
        # convert color_palette to R vector
        color_palette = "c(" + ", ".join([f'"{k}" = "{v}"' for k, v in color_palette.items()]) + ")"
        
    # save the obs to csv file
    adata.obs.to_csv(f"obs.csv", index = False)
    
    
    
    r_code = """

library(Seurat)
library(ggplot2)
library(dplyr)
library(dior)

setwd("{outdir}")

meta_frame <- read.csv("obs.csv", header = TRUE)

# get the total cell number of each group
total_cell_number_frame <- meta_frame %>% group_by({groupby}) %>% summarise(total_cell_number = n())

# get the groupA cell number

sub_group_cell_number_frame <- meta_frame %>% group_by({groupby}) %>% summarise(sub_group_cell_number = n())

gp <- ggplot(sub_group_cell_number_frame, aes(x = {groupby}, y = sub_group_cell_number, fill = {groupby})) +
    geom_bar(stat = "identity") +
    scale_fill_manual(values = {color_palette}) +
    labs(y = "{ylab_text}", x = "{xlab_text}") +
    guides(fill=guide_legend(title="")) +
    theme_classic() +
    # add the text on the top of the bar
    geom_text(aes(label = sub_group_cell_number), vjust = -0.3, size = 3) +
    theme(axis.text.x = element_text(angle = 45, hjust = 1), strip.background = element_blank())

ggplot2::ggsave("{prefix}_cell_number_bar_plot.png", plot = gp, width = {fig_width}, height = {fig_height})

ggplot2::ggsave("{prefix}_cell_number_bar_plot.pdf", plot = gp, width = {fig_width}, height = {fig_height})


# get the total count of all cells and add it to the total_cell_number_frame
total_cell_number <- sum(total_cell_number_frame$total_cell_number)
total_cell_number_frame <- rbind(total_cell_number_frame, data.frame({groupby} = "Total", total_cell_number = total_cell_number))

# write the total cell number to a tab-delimited file
write.table(total_cell_number_frame, file = "{prefix}_total_cell_number.txt", sep = "\t", quote = FALSE, row.names = F, col.names = TRUE)

    """.format(outdir = os.getcwd(),
               groupby = groupby,
               fig_height = fig_height,
               fig_width = fig_width,
               color_palette = color_palette,
               xlab_text = xlab_text,
               ylab_text = ylab_text,
               prefix = prefix)

    # write the r code to a file
    r_file = open("plotCellNumberBarPlotByGroup.R", "wt", encoding="utf-8")
    r_file.write(r_code)
    r_file.close()
    # run the r code
    os.system("/common/cuis/tools/miniconda/envs/rapid/bin/Rscript plotCellNumberBarPlotByGroup.R")

```



``` python


os.chdir('/common/cuis/projects/IBDNanostring/RawData/scLIHC/AnnaProjects/scESCC/Results')



plotCellNumberBarPlotByGroup(adata = esca_adata, 
                            groupby = 'study',
                            prefix = "ESCCbystudy",
                            color_palette = color_palette = {"PRJCA016745": "#E41A1C", "GSE145370": "#377EB8", "GSE53624": "#4DAF4A", "GSE222078": "#984EA3", "GSE160269": "#FF7F00"},
                            xlab_text = "",
                            ylab_text = "Cell Number",
                            fig_width = 10,
                            fig_height = 5)


```


如何使用markdown放入路径的图片



<img src="..\Results\P001_ESCC_UMAP_by_level1\Global_ESCC_enhancedV01_umap.png" alt="drawing" width="800"/>


****



``` python


esca_adata.obs.columns


```


``` python

esca_adata.obs['level2'].value_counts()



````


``` python

# show me tissue column
    
esca_adata.obs['tissue'].value_counts()

```



``` python

# show me treatment column

    
esca_adata.obs['treatment'].value_counts()


```



``` python



def plotEnhancedUMAPV02(adata, 
                        obs_field_name,
                        output_prefix,
                        color_palette = None, # {"PoorSurvival": "tab:red", "Others": "tab:grey"},
                        point_size = 10,
                        fig_width = 15,
                        fig_height = 15):
    import scanpy as sc
    import matplotlib.pyplot as plt

    # create plot_enhanced_umap_v02 directory
    os.makedirs(f"{output_prefix}_plot_enhanced_umap_v02", exist_ok=True)
    os.chdir(f"{output_prefix}_plot_enhanced_umap_v02")

    with plt.rc_context({"figure.figsize": (fig_width, fig_height), "figure.dpi": 600, "figure.frameon": False}):
        sc.pl.umap(adata,
                color=obs_field_name,
                size=point_size,
                show=False,
                legend_loc="right margin",
                legend_fontoutline=2,
                legend_fontsize=32,
                frameon=False,
                title = "",
                palette=color_palette,
                save = f"_{output_prefix}_enhancedUMAPV02_umap.png")

    with plt.rc_context({"figure.figsize": (15, 15), "figure.dpi": 600, "figure.frameon": False}):
        sc.pl.umap(adata,
                color=obs_field_name,
                size=point_size,
                show=False,
                legend_loc="right margin",
                legend_fontoutline=2,
                legend_fontsize=32,
                frameon=False,
                title = "",
                palette=color_palette,
                save = f"_{output_prefix}_enhancedUMAPV02_umap.pdf")





```


``` python

# show me the study column

esca_adata.obs['study'].value_counts()


```


``` python



# GSE160269      208659
# PRJCA016745    164957
# GSE145370      103356
# GSE53624        96123
# GSE222078       66970


# #E41A1C", "#377EB8", "#4DAF4A", "#984EA3",
#                      "#FF7F00", "#FFFF33", "#A65628",





os.chdir('/common/cuis/projects/IBDNanostring/RawData/scLIHC/AnnaProjects/scESCC/Results')



color_palette = {"PRJCA016745": "#E41A1C", "GSE145370": "#377EB8", "GSE53624": "#4DAF4A", "GSE222078": "#984EA3", "GSE160269": "#FF7F00"}


plotEnhancedUMAPV02(adata = esca_adata, 
                    obs_field_name = 'study',
                    output_prefix = "ESCCbystudy",
                    color_palette = color_palette,
                    point_size = 10,
                    fig_width = 15,
                    fig_height = 15)
                    



```

``` python



def plotEnhancedUMAPV02(adata, 
                        obs_field_name,
                        output_prefix,
                        color_palette = None, # {"PoorSurvival": "tab:red", "Others": "tab:grey"},
                        point_size = 10,
                        fig_width = 15,
                        fig_height = 15):
    import scanpy as sc
    import matplotlib.pyplot as plt

    # create plot_enhanced_umap_v02 directory
    os.makedirs(f"{output_prefix}_plot_enhanced_umap_v02", exist_ok=True)
    os.chdir(f"{output_prefix}_plot_enhanced_umap_v02")

    with plt.rc_context({"figure.figsize": (fig_width, fig_height), "figure.dpi": 600, "figure.frameon": False}):
        sc.pl.umap(adata,
                color=obs_field_name,
                size=point_size,
                show=False,
                legend_loc="right margin",
                legend_fontoutline=2,
                legend_fontsize=32,
                frameon=False,
                title = "",
                palette=color_palette,
                save = f"_{output_prefix}_enhancedUMAPV02_umap.png")

    with plt.rc_context({"figure.figsize": (15, 15), "figure.dpi": 600, "figure.frameon": False}):
        sc.pl.umap(adata,
                color=obs_field_name,
                size=point_size,
                show=False,
                legend_loc="right margin",
                legend_fontoutline=2,
                legend_fontsize=32,
                frameon=False,
                title = "",
                palette=color_palette,
                save = f"_{output_prefix}_enhancedUMAPV02_umap.pdf")


```

``` python


esca_adata.obs['sample_id'].value_counts()

```


``` python



def plotCellNumberBarPlotByGroup(adata, 
                                 groupby,
                                 prefix,
                                 color_palette = {}, # {"PHT": "#E41A1C", "LRT": "#377EB8"}
                                 xlab_text = "",
                                 ylab_text = "Cell Number",
                                 fig_width = 10,
                                 fig_height = 5):


    import diopy
    import anndata as ad
    import scanpy as sc

    # create directory named cell_number_barplot_by_group
    os.makedirs("cell_number_barplot_by_group", exist_ok = True)
    os.chdir("cell_number_barplot_by_group")
    
    adata = ad.AnnData(X=adata.X, obs=adata.obs, var=adata.var)
    
    nature_colors = ["#E41A1C", "#377EB8", "#4DAF4A", "#984EA3",
                     "#FF7F00", "#FFFF33", "#A65628", "#F781BF",
                    "#999999", "#E7298A", "#66C2A5", "#FC8D62",
                    "#8DA0CB", "#E78AC3", "#A6D854", "#FFD92F",
                    "#E5C494", "#B3B3B3", "#8DD3C7", "#BEBADA",
                    "#FB8072", "#80B1D3", "#FDB462", "#B3DE69"]


    if len(color_palette) == 0:
        color_palette = "c(" + ", ".join([f'"{k}" = "{v}"' for k, v in zip(adata.obs[groupby].unique(), nature_colors)]) + ")"
    else:
        # convert color_palette to R vector
        color_palette = "c(" + ", ".join([f'"{k}" = "{v}"' for k, v in color_palette.items()]) + ")"
        
    # save the obs to csv file
    adata.obs.to_csv(f"obs.csv", index = False)
    
    
    
    r_code = """

library(Seurat)
library(ggplot2)
library(dplyr)
library(dior)

setwd("{outdir}")

meta_frame <- read.csv("obs.csv", header = TRUE)

# get the total cell number of each group
total_cell_number_frame <- meta_frame %>% group_by({groupby}) %>% summarise(total_cell_number = n())

# get the groupA cell number

sub_group_cell_number_frame <- meta_frame %>% group_by({groupby}) %>% summarise(sub_group_cell_number = n())

gp <- ggplot(sub_group_cell_number_frame, aes(x = {groupby}, y = sub_group_cell_number, fill = {groupby})) +
    geom_bar(stat = "identity") +
    scale_fill_manual(values = {color_palette}) +
    labs(y = "{ylab_text}", x = "{xlab_text}") +
    guides(fill=guide_legend(title="")) +
    theme_classic() +
    # 增加柱状图顶部的数字标签
    geom_text(aes(label = sub_group_cell_number), vjust = -0.3, size = 3) +
    # 设置 X 轴文字字体大小
    theme(axis.text.x = element_text(size = 36, angle = 45, hjust = 1),  # 修改字体大小为 36
          strip.background = element_blank())


ggplot2::ggsave("{prefix}_cell_number_bar_plot.png", plot = gp, width = {fig_width}, height = {fig_height})

ggplot2::ggsave("{prefix}_cell_number_bar_plot.pdf", plot = gp, width = {fig_width}, height = {fig_height})


# get the total count of all cells and add it to the total_cell_number_frame
total_cell_number <- sum(total_cell_number_frame$total_cell_number)
total_cell_number_frame <- rbind(total_cell_number_frame, data.frame({groupby} = "Total", total_cell_number = total_cell_number))

# write the total cell number to a tab-delimited file
write.table(total_cell_number_frame, file = "{prefix}_total_cell_number.txt", sep = "\t", quote = FALSE, row.names = F, col.names = TRUE)

    """.format(outdir = os.getcwd(),
               groupby = groupby,
               fig_height = fig_height,
               fig_width = fig_width,
               color_palette = color_palette,
               xlab_text = xlab_text,
               ylab_text = ylab_text,
               prefix = prefix)

    # write the r code to a file
    r_file = open("plotCellNumberBarPlotByGroup.R", "wt", encoding="utf-8")
    r_file.write(r_code)
    r_file.close()
    # run the r code
    os.system("/common/cuis/tools/miniconda/envs/rapid/bin/Rscript plotCellNumberBarPlotByGroup.R")




```

``` python

os.chdir('/common/cuis/projects/IBDNanostring/RawData/scLIHC/AnnaProjects/scESCC/Results')

color_palette = {"PRJCA016745": "#E41A1C", "GSE145370": "#377EB8", "GSE53624": "#4DAF4A", "GSE222078": "#984EA3", "GSE160269": "#FF7F00"}



# show me cell number by study using barplot
plotCellNumberBarPlotByGroup(adata = esca_adata, 
                             groupby = 'study',
                             prefix = "ESCCbystudy",
                             color_palette = color_palette,
                             xlab_text = "",
                             ylab_text = "Cell Number",
                             fig_width = 10,
                             fig_height = 5)



```


****

``` python




def plot_umap_colored_by_gene_list(adata,
                    gene_list,
                    output_prefix,
                    ncols = 5,
                    point_size = 10,
                    axes_title_fontsize = 50,
                    fig_width = 15,
                    fig_height = 6):

    import scanpy as sc
    import matplotlib.pyplot as plt

    plt.rcParams.update({'axes.labelsize' : 'large', 'axes.titlesize' : axes_title_fontsize}) 
    # this can control the size of the gene label in the plot
    sc.set_figure_params(scanpy=True, fontsize=34)
    plt.legend(markerscale=2)

    
    with plt.rc_context({"figure.figsize": (fig_width, fig_height), "figure.dpi": 600, "figure.frameon": False}):
        sc.pl.umap(adata,
                color=gene_list,
                size=point_size,
                show=False,
                legend_loc="right margin",
                legend_fontoutline=2,
                legend_fontsize=32,
                ncols = ncols,
                frameon=False,
                color_map='plasma',
                save = f"_{output_prefix}_mosaic_umap.png")


    with plt.rc_context({"figure.figsize": (fig_width, fig_height), "figure.dpi": 600, "figure.frameon": False}):
        sc.pl.umap(adata,
                color=gene_list,
                size=point_size,
                show=False,
                legend_loc="right margin",
                legend_fontoutline=2,
                legend_fontsize=32,
                ncols = ncols,
                frameon=False,
                color_map='plasma',
                save = f"_{output_prefix}_mosaic_umap.pdf")





```



``` python






def show_scanpy_adata(adata):
    
    import scanpy as sc
    import numpy as np
    
    logging.info(f"adata shape: {adata.shape}")
    
    logging.info("the scanpy object's columns are:")
    for i in range(len(adata.obs.columns.tolist())):
        print('%d: %s' % (i, adata.obs.columns.tolist()[i]))
    
    logging.info("the scanpy object's matrix are:")
    
    # check adata.X is a np.array
    if type(adata.X) == np.ndarray:
        matrix_value = adata.X[1:10, 1:10]
        # only show the value does not equal to 0
        matrix_value = matrix_value[matrix_value != 0]
        print(matrix_value)
        
    else:
        matrix_value = adata.X[1:30, 1:30].toarray()
        for i in matrix_value[1:10]:
            print(i)
    




```

***


``` python

# 找出所有Tcell

esca_adata.obs['level1'].value_counts()

# get the subset of Tcell

adata_Tcell = esca_adata[esca_adata.obs['level1'] == 'Tcell', :]

adata_Tcell.obs['level1'].value_counts()


```





``` python

esca_adata.obs['level1'].value_counts()

# get the subset of Bcell

adata_Bcell = esca_adata[esca_adata.obs['level1'] == 'Bcell', :]

adata_Bcell.obs['level1'].value_counts()

```




``` python




def plot_cell_subpopulation_proportion_by_group_using_boxplot(adata,
                                            groupby,
                                            sample_id_field_name,
                                            celltype_field_name,
                                            group_to_compare, # "A:B;B:C"
                                            color_palette, # "PHT:#E41A1C;LRT:#377EB8;PHN:#4DAF4A;LRN:#984EA3"
                                            output_prefix,
                                            xlab_text = "",
                                            ylab_text = "",
                                            fig_width = 18,
                                            fig_height = 16):

    import diopy
    import pandas as pd
    import scanpy as sc
    import os
    import anndata as ad
    

    # create directory named cell_subpopulation_proportion_by_group_using_boxplot
    os.makedirs(f"{output_prefix}_cell_subpopulation_proportion_by_group_using_boxplot", exist_ok = True)
    os.chdir(f"{output_prefix}_cell_subpopulation_proportion_by_group_using_boxplot")

    # save the adata to a feather file
    adata.obs.to_csv("adata_obs.csv", index = False)


    r_code = """

library(ggsignif)
library(ggplot2)
library(dplyr)
library(dior)
library(arrow)
library(data.table)



# Input parameters


groupby <- "{groupby}"
sample_id_field_name <- "{sample_id_field_name}"
celltype_field_name <- "{celltype_field_name}"
group_to_compare <- "{group_to_compare}"
color_palette <- "{color_palette}"
output_prefix <- "{output_prefix}"


setwd("{outdir}")

metadata_frame <- read.csv("adata_obs.csv", header = TRUE)


metadata_frame <- metadata_frame %>% select("{sample_id_field_name}", "{celltype_field_name}", "{groupby}")

# calculate the proportion of each subcelltype in each sample
freq_frame <- metadata_frame %>% group_by({celltype_field_name}, {sample_id_field_name}, {groupby}) %>% summarise(freq = n())

# split group_to_compare using ':' and convert to list
# First, split by ';'
first_split <- unlist(strsplit(group_to_compare, split = ';'))

# Then, split each of those results by ':'
group_to_compare_list <- lapply(first_split, function(x) unlist(strsplit(x, split = ':')))


# prepare color mapping
color_split <- lapply(unlist(strsplit(color_palette, split = ';')), function(x) unlist(strsplit(x, split = ':')))

color_mapping <- unlist(lapply(color_split, function(x) x[2]))
names(color_mapping) <- unlist(lapply(color_split, function(x) x[1]))


# calculate the proportion of each subcelltype in each sample
prop_frame <- freq_frame %>% group_by({sample_id_field_name}, {groupby}) %>% mutate(proportion = freq/sum(freq))


nature_colors <- c("#E41A1C", "#377EB8", "#4DAF4A", "#984EA3", 
                    "#FF7F00", "#FFFF33", "#A65628", "#F781BF")

gp <- ggplot(prop_frame, aes(x={groupby}, y=proportion, fill={groupby})) +
    geom_boxplot() +
    # add the points
    geom_jitter(width = 0.2, height = 0, alpha = 0.3) +
    ylab("Cell Subpopulation Proportion") +
    xlab("") +
    theme_bw() +
    theme(axis.text.x = element_text(angle = 90, hjust = 1), strip.background = element_blank(), plot.margin = margin(1, 1, 1, 1, "cm")) +
    geom_signif(comparisons = group_to_compare_list,
                textsize = 3,
                step_increase = 0.1,
                map_signif_level=TRUE) +
    scale_fill_manual(values = color_mapping) + 
    facet_wrap(~{celltype_field_name}, scales = "free_y")

ggsave("{output_prefix}_proportion.pdf", plot=gp, width={fig_width}, height={fig_height})

# use inch as the unit
ggsave("{output_prefix}_proportion.png", plot=gp, width={fig_width}, height={fig_height}, units="in")

""".format(groupby = groupby,
                sample_id_field_name = sample_id_field_name,
                celltype_field_name = celltype_field_name,
                group_to_compare = group_to_compare,
                color_palette = color_palette,
                output_prefix = output_prefix,
                xlab_text = xlab_text,
                ylab_text = ylab_text,
                fig_width = fig_width,
                fig_height = fig_height,
                outdir = os.getcwd())
    
    # write the R code to a file
    r_file = open("plotCelltypeProportionBoxPlotByGroupV01.R", "w", encoding = "utf-8")
    r_file.write(r_code)
    r_file.close()

    # run the R code
    os.system(f"/common/cuis/tools/miniconda/envs/rapid/bin/Rscript plotCelltypeProportionBoxPlotByGroupV01.R")






```



``` python


esca_adata.obs['study'].value_counts()

# GSE160269      293
# PRJCA016745    268
# GSE145370      179
# GSE53624       172
# GSE222078       88

# generate color
color_palette = "GSE160269:#E41A1C;PRJCA016745:#377EB8;GSE145370:#4DAF4A;GSE53624:#984EA3;GSE222078:#FF7F00"



plot_cell_subpopulation_proportion_by_group_using_boxplot(adata = esca_adata,
                                            groupby = 'study',
                                            sample_id_field_name = 'sample_id',
                                            celltype_field_name = 'level1',
                                            group_to_compare = "GSE160269:PRJCA016745;GSE145370:GSE222078;GSE53624:GSE222078" , # "A:B;B:C"
                                            color_palette = color_palette, # "PHT:#E41A1C;LRT:#377EB8;PHN:#4DAF4A;LRN:#984EA3"
                                            output_prefix = 'by_study',
                                            xlab_text = "",
                                            ylab_text = "",
                                            fig_width = 18,
                                            fig_height = 16)






```




``` python



esca_adata.obs['disease'].value_counts()



``` 


``` python





def plot_cell_subpopulation_proportion_by_group_using_boxplot(adata,
                                            groupby,
                                            sample_id_field_name,
                                            celltype_field_name,
                                            group_to_compare, # "A:B;B:C"
                                            color_palette, # "PHT:#E41A1C;LRT:#377EB8;PHN:#4DAF4A;LRN:#984EA3"
                                            output_prefix,
                                            xlab_text = "",
                                            ylab_text = "",
                                            fig_width = 18,
                                            fig_height = 16):

    import diopy
    import pandas as pd
    import scanpy as sc
    import os
    import anndata as ad
    

    # create directory named cell_subpopulation_proportion_by_group_using_boxplot
    os.makedirs(f"{output_prefix}_cell_subpopulation_proportion_by_group_using_boxplot", exist_ok = True)
    os.chdir(f"{output_prefix}_cell_subpopulation_proportion_by_group_using_boxplot")

    # save the adata to a feather file
    adata.obs.to_csv("adata_obs.csv", index = False)


    r_code = """

library(ggsignif)
library(ggplot2)
library(dplyr)
library(dior)
library(arrow)
library(data.table)



# Input parameters


groupby <- "{groupby}"
sample_id_field_name <- "{sample_id_field_name}"
celltype_field_name <- "{celltype_field_name}"
group_to_compare <- "{group_to_compare}"
color_palette <- "{color_palette}"
output_prefix <- "{output_prefix}"


setwd("{outdir}")

metadata_frame <- read.csv("adata_obs.csv", header = TRUE)


metadata_frame <- metadata_frame %>% select("{sample_id_field_name}", "{celltype_field_name}", "{groupby}")

# calculate the proportion of each subcelltype in each sample
freq_frame <- metadata_frame %>% group_by({celltype_field_name}, {sample_id_field_name}, {groupby}) %>% summarise(freq = n())

# split group_to_compare using ':' and convert to list
# First, split by ';'
first_split <- unlist(strsplit(group_to_compare, split = ';'))

# Then, split each of those results by ':'
group_to_compare_list <- lapply(first_split, function(x) unlist(strsplit(x, split = ':')))


# prepare color mapping
color_split <- lapply(unlist(strsplit(color_palette, split = ';')), function(x) unlist(strsplit(x, split = ':')))

color_mapping <- unlist(lapply(color_split, function(x) x[2]))
names(color_mapping) <- unlist(lapply(color_split, function(x) x[1]))


# calculate the proportion of each subcelltype in each sample
prop_frame <- freq_frame %>% group_by({sample_id_field_name}, {groupby}) %>% mutate(proportion = freq/sum(freq))


nature_colors <- c("#E41A1C", "#377EB8", "#4DAF4A", "#984EA3", 
                    "#FF7F00", "#FFFF33", "#A65628", "#F781BF")

gp <- ggplot(prop_frame, aes(x={groupby}, y=proportion, fill={groupby})) +
    geom_boxplot() +
    # 添加散点
    geom_jitter(width = 0.2, height = 0, alpha = 0.3) +
    ylab("Cell Subpopulation Proportion") +
    xlab("") +
    theme_bw() +
    theme(strip.text = element_text(size = 20),  # 修改分面标题字体大小
          axis.text.x = element_text(angle = 90, hjust = 1),
          strip.background = element_blank(),
          plot.margin = margin(1, 1, 1, 1, "cm")) +
    geom_signif(comparisons = group_to_compare_list,
                textsize = 3,
                step_increase = 0.1,
                map_signif_level = TRUE) +
    scale_fill_manual(values = color_mapping) +
    facet_wrap(~{celltype_field_name}, scales = "free_y")


ggsave("{output_prefix}_proportion.pdf", plot=gp, width={fig_width}, height={fig_height})

# use inch as the unit
ggsave("{output_prefix}_proportion.png", plot=gp, width={fig_width}, height={fig_height}, units="in")

""".format(groupby = groupby,
                sample_id_field_name = sample_id_field_name,
                celltype_field_name = celltype_field_name,
                group_to_compare = group_to_compare,
                color_palette = color_palette,
                output_prefix = output_prefix,
                xlab_text = xlab_text,
                ylab_text = ylab_text,
                fig_width = fig_width,
                fig_height = fig_height,
                outdir = os.getcwd())
    
    # write the R code to a file
    r_file = open("plotCelltypeProportionBoxPlotByGroupV01.R", "w", encoding = "utf-8")
    r_file.write(r_code)
    r_file.close()

    # run the R code
    os.system(f"/common/cuis/tools/miniconda/envs/rapid/bin/Rscript plotCelltypeProportionBoxPlotByGroupV01.R")




```



``` python

os.chdir("/common/cuis/projects/IBDNanostring/RawData/scLIHC/AnnaProjects/scESCC/Results")

esca_adata.obs['study'].value_counts()

# ESCC    567433
# EAC      72632

# generate color
color_palette = "ESCC:#E41A1C;EAC:#377EB8"



plot_cell_subpopulation_proportion_by_group_using_boxplot(adata = esca_adata,
                                            groupby = 'disease',
                                            sample_id_field_name = 'sample_id',
                                            celltype_field_name = 'level1',
                                            group_to_compare = "ESCC:EAC", # "A:B;B:C"
                                            color_palette = color_palette, # "PHT:#E41A1C;LRT:#377EB8;PHN:#4DAF4A;LRN:#984EA3"
                                            output_prefix = 'by_disease',
                                            xlab_text = "",
                                            ylab_text = "",
                                            fig_width = 18,
                                            fig_height = 16)






``` python



# 从GSE53624_adata 中 查看sample 数量

GSE53624_adata.obs['sample_id'].value_counts()

```
``` python


# 输入：GSE53624_adata  代表一份scanpy adata 对象,其中一个字段是tissue；
# 输出：我希望知道这个字段中有多少个不同的值
    
GSE53624_adata.obs['tissue'].value_counts()


```

``` python


# 输入：esca_adata  代表一份scanpy adata 对象,其中一个字段是study；
# 输出：我希望知道这个字段中有多少个不同的值
        
esca_adata.obs['study'].value_counts()

```

如何使用barplot展示在分组中的细胞亚群的比例

``` python




def plotCellProportiontByGroupBarPlot(
                                 adata, 
                                 groupbyA, # sample_id
                                 groupbyB, # scissor_status
                                 prefix,
                                 ylab_text = "Cell Proportion",
                                 xlab_text = "",
                                 fig_width = 5,
                                 fig_height = 5):
    
    import diopy
    import anndata as ad
    import scanpy as sc
    
    # create directory named cell_proportion_by_group_barplot
    os.makedirs("cell_proportion_by_group_barplot", exist_ok = True)
    os.chdir("cell_proportion_by_group_barplot")

    
    # save the adata.obs to csv file
    adata.obs.to_csv(f"{prefix}_cell_proportion.csv", index = False)
    

    
    r_code = """
    
library(Seurat)
library(ggplot2)
library(dplyr)
library(dior)

setwd("{outdir}")

message("load the adata")

# load the adata
meta_frame <- read.csv("{prefix}_cell_proportion.csv", header = TRUE)

# get the total cell number of each group
total_cell_number_frame <- meta_frame %>% dplyr::select(c("{groupbyA}", "{groupbyB}")) %>% group_by({groupbyA}, {groupbyB}) %>% summarise(total_cell_number = n())


# calculate the proportion of each group
total_cell_number_frame <- total_cell_number_frame %>% group_by({groupbyA}) %>% mutate(proportion = total_cell_number / sum(total_cell_number))

# only keep two digits after the decimal point

total_cell_number_frame$proportion <- round(total_cell_number_frame$proportion, 2)


# write the total cell number to a tab-delimited file
write.table(total_cell_number_frame, file = "{prefix}_cell_proportion.txt", sep = "\t", quote = FALSE, row.names = F, col.names = TRUE)


nature_colors = c("#E41A1C", "#377EB8", "#4DAF4A", "#984EA3", 
        "#FF7F00", "#FFFF33", "#A65628", "#F781BF",
        "#999999", "#E7298A", "#66C2A5", "#FC8D62",
        "#8DA0CB", "#E78AC3", "#A6D854", "#FFD92F",
        "#E5C494", "#B3B3B3", "#8DD3C7", "#BEBADA",
        "#FB8072", "#80B1D3", "#FDB462", "#B3DE69",
        "#FCCDE5", "#D9D9D9", "#BC80BD", "#CCEBC5",
        "#FFED6F", "#C4E4FF")

gp <- ggplot(total_cell_number_frame, aes(x = {groupbyA}, y = total_cell_number, fill = {groupbyB})) +
    geom_bar(stat = "identity", position = "fill") +
    scale_fill_manual(values = nature_colors) +
    labs(y = "{ylab_text}", x = "{xlab_text}") +
    # set the title of legend
    guides(fill=guide_legend(title="")) +
    theme_classic() +
    theme(axis.text.x = element_text(angle = 45, hjust = 1, size = 10), strip.background = element_blank())

ggplot2::ggsave("{prefix}_cell_proportion_bar_plot.png", plot = gp, width = {fig_width}, height = {fig_height})

message("save the figure to {prefix}_cell_proportion_bar_plot.png")

ggplot2::ggsave("{prefix}_cell_proportion_bar_plot.pdf", plot = gp, width = {fig_width}, height = {fig_height})

message("save the figure to {prefix}_cell_proportion_bar_plot.pdf")

    """.format(outdir = os.getcwd(),
               groupbyA = groupbyA,
               groupbyB = groupbyB,
               fig_width = fig_width,
               fig_height = fig_height,
               ylab_text = ylab_text,
               xlab_text = xlab_text,
               prefix = prefix)

    # write the r code to a file
    r_file = open("plotCellProportiontByGroupBarPlot.R", "wt", encoding="utf-8")
    r_file.write(r_code)
    r_file.close()
    # run the r code
    os.system("/common/cuis/tools/miniconda/envs/rapid/bin/Rscript plotCellProportiontByGroupBarPlot.R")





```



``` python 



```









