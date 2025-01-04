






加载所需要的项目包

``` python




from re import sub
import scvi
import scanpy as sc
import numpy as np
import pickle
import os
import pandas as pd
import logging
import anndata as ad
import logging



import time
import os, wget




```

加载global的adat文件是存储为pickle格式的文件

这里的adata 文件路径是`/home/cuis/common/projects/IBDNanostring/RawData/scESCC/Analysis/Results/Global/SingleR/esca_query_adata.pkl`

``` python



# 切换到工作目录下

os.chdir('/common/cuis/projects/IBDNanostring/RawData/scLIHC/AnnaProjects/scESCC/Results')



# 加载adata文件

esca_query_adata = pickle.load(open("/home/cuis/common/projects/IBDNanostring/RawData/scESCC/Analysis/Results/Global/SingleR/esca_query_adata.pkl", "rb"))




```

查看文件大小


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

















































































