# 从零学量化68—价值因子评价：低市盈率(PE)是否仍然是价值投资的良方？ 

在上一篇文章《价值因子：从“便宜”中挖掘低估宝藏》中，我们介绍了价值因子的概念和价值因子的具体指标，本文将对价值因子的常见指标——市盈率因子进行评价。关于市盈率的介绍详见上文。

本文进行因子评价的工具为Alphalens库，Alphalens库的用法详见《量化工具箱：因子评价神器Alphalens库超详细教程》。本文进行因子评价的相关代码在上述文章中已有详细讲解，如果对这些代码不清楚的可以查看以前的文章，本文不再对代码进行过多的解释。

我为大家整理了计算和评价因子所需的全部沪深股票2010年1月1日至2023年6月30日的数据，数据文件名为：value_factor.csv，在后台回复“价值因子”可获取。

市盈率的计算可以使用最近一个年度的年报数据，也可以使用TTM数据，本文使用的是TTM数据。

当公司的盈利为负数时，市盈率（P/E）计算将会产生负值，当分母出现负值时会出现预料之外的结果。常见的处理方法有删除市盈率为负的数据和使用市盈率的倒数（E/P），本文采用的方法为删除市盈率为负的数据。

## 01 使用Alphalens库进行因子评价的代码

```python 


# 导入相关的库
import numpy as np
import pandas as pd
import statsmodels.api as sm
import alphalens as al

# 关闭警告信息
import warnings
warnings.filterwarnings('ignore')

# 从CSV文件读取数据
file_path = 'e:temp/value_factor.csv'  # 文件的路径和文件名，注意：此处要换成你的文件地址
data_df = pd.read_csv(file_path, encoding='gbk', index_col=0) 
data_df['日期'] = pd.to_datetime(data_df['日期'])  # 将日期统一为datetime格式

# 设置将要评价的因子
factor_name = 'pe_ttm'

# 生成符合Alphalens要求格式的因子值数据

factor = data_df.set_index(['日期','股票代码'])[factor_name]
# 生成符合Alphalens要求格式的交易价格数据
prices = data_df.pivot(index='日期', columns='股票代码', values='开盘价')
prices = prices.shift(-1)  # 将第二天的开盘价作为交易价格，避免用到“未来数据”

# 预处理因子数据，得到符合Alphalens需要的数据格式。
factor_data = al.utils.get_clean_factor_and_forward_returns(
    factor=factor,
    prices=prices,
    quantiles=10,
    periods=(1, 10))
    
# 生成因子性能报告
al.tears.create_full_tear_sheet(factor_data)


```