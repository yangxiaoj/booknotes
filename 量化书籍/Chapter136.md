# 量化实战入门136—怎样用python计算信息比率 

信息比率（Information Ratio）是一个用于衡量投资策略表现的指标，它反映了单位超额风险所带来的超额收益。这个比率可以帮助投资者评估一个策略相对于基准的优劣。

信息比率的计算公式是：

       信息比率 = 每日超额收益的均值 / 每日超额收益的标准差

其中：

       每日超额收益 = 投资组合的日收益率 – 基准的日收益率

每日超额收益是投资组合的日收益率与基准的日收益率之间的差值。这个差值反映了策略相对于基准的表现。如果这个值是正的，那么策略就在基准之上产生了额外的回报；如果是负的，策略的表现就不如基准。

每日超额收益的均值反映了超额收益的平均水平。

每日超额收益的标准差代表了超额收益的波动性，这个值越大，说明超额收益的波动性越大，投资的不确定性和风险也就越高。

这个公式将超额收益的均值除以标准差，得到的信息比率可以告诉我们，投资策略每承担一个单位的风险，能够带来多少超额收益。一个高信息比率意味着策略在每单位风险上获得了更高的超额收益，即投资组合比较稳定地超越基准，这通常是投资者所追求的。

下面我们举例说明如何计算信息比率：
## 1. 获取标的股票和基准的基础数据
我们从AKShare数据源获取沪深300和山西汾酒的收盘价数据。AKShare的接口有时会有更新，如果提示接口不存在，请参考AKShare的网站。

```python 

# 导入需要使用的库
import akshare as ak
import pandas as pd
import numpy as np
# 关闭警告信息
import warnings
warnings.filterwarnings('ignore')

# 设置取数日期范围
start_date = '20140101'
end_date = '20231229'
# 获取基准指数的收盘价数据
benchmark = "000300"
bars = ak.stock_zh_index_hist_csindex(symbol=benchmark, start_date=start_date, end_date=end_date)
# 将日期设置为datetime格式
bars['日期'] = pd.to_datetime(bars['日期'])
prices_df = pd.DataFrame(index=bars['日期'])
prices_df[f'{benchmark}'] = bars.set_index('日期')['收盘']

# 获取股票的收盘价数据
stock = "600809"
bars = ak.stock_zh_a_hist(symbol=stock, period="daily", start_date=start_date, end_date=end_date, adjust="qfq")
# 将日期设置为datetime格式
bars['日期'] = pd.to_datetime(bars['日期'])
prices_df[f'{stock}'] = bars.set_index('日期')['收盘']

```

## 2. 计算信息比率

```python 

# 计算信息比率（Information Ratio）
annual_periods = 244  # 年化期数，一年约244个交易日
# 计算基准和标的股票的日收益率
returns = prices_df.pct_change().fillna(0)
# 计算日超额收益率 = 标的股票日收益率 - 基准日收益率
returns_diff = returns[f'{stock}'] - returns[f'{benchmark}']
# 计算信息比率（Information Ratio） = 每日超额收益的均值 / 每日超额收益的标准差
information_ratio = returns_diff.mean() / returns_diff.std() * np.sqrt(annual_periods)

```
在上述代码中，我们在计算信息比率时乘上了年化系数：np.sqrt(annual_periods)，这样可以将信息比例进行简单年化处理，以使得不同时间频率的信息比率能够进行标准化比较。