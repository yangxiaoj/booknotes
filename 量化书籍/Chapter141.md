# 量化实战入门141—超越夏普比率：索提诺比率的新标准 


索提诺比率（Sortino Ratio）是一种风险调整收益率的指标，用于评估投资策略、基金或投资组合在考虑下行风险的情况下的表现。它与夏普比率类似，但区别在于索提诺比率仅考虑了投资回报下跌的风险，即下行风险，而不是总体波动性。
索提诺比率的计算公式如下：

        索提诺比率 =（投资组合收益率- 无风险利率）/ 下行标准差

其中，下行标准差是指投资回报低于某个给定目标或最低期望回报率时回报率的波动性。这个目标通常设为无风险利率，但也可以是零收益或投资者的最低期望回报。


索提诺比率的核心优势在于它只惩罚那些投资者不希望承担的风险——亏损的风险。这与夏普比率不同，后者将所有的波动性都视为风险，无论是向上还是向下。因此，如果一个投资组合或策略的收益率分布是非对称的，特别是在收益率倾向于在正面有大的波动时，索提诺比率可能是一个更合适的性能衡量标准。


在实际应用中，索提诺比率可以帮助投资者识别和选择那些在相同的下行风险水平下能够提供更高超额回报的投资组合。高索提诺比率意味着在承受较低的不利波动性（或损失风险）的情况下，投资策略或基金的性能更好。这使得索提诺比率成为评估投资风险-收益特性的重要工具，尤其是对于那些对损失更为敏感的投资者。


下面我们举例说明如何用python计算索提诺比率：


## 1. 获取基础数据

我们从AKShare数据源获取沪深300的10年收盘价数据。AKShare的接口有时会有更新，如果提示接口不存在，请参考AKShare的网站。

```python 

# 导入需要使用的库
import akshare as ak
import pandas as pd
import numpy as np
# 关闭警告信息
import warnings
warnings.filterwarnings('ignore')

# 获取沪深300指数10年的收盘价数据
start_date = '20140101'  # 开始日期
end_date = '20231229'  # 结束日期
bars = ak.stock_zh_index_hist_csindex(symbol='000300', start_date=start_date, end_date=end_date)
prices = bars[['日期','收盘']]
# 将日期设置为datetime格式
prices['日期'] = pd.to_datetime(prices['日期'])
prices = prices.set_index('日期')
# 计算日收益率
returns = prices['收盘'].pct_change()

```

跟夏普比例类似，我们可以用简单年化收益率和复合年化收益率两种方法来计算索提诺比率。简单年化收益率没有考虑复利效应，而复合年化收益率考虑了复利效应。


## 2. 用简单年化收益率计算索提诺比率

```python 

# 索提诺比率：使用简单年化收益率
rf = 0.0  # 假设无风险利率为0
annual_periods = 244  # 年化期数，一年约244个交易日
n = len(returns)

# 计算超额收益
returns = returns - rf

# 计算下行差异：如果returns的值小于0则保留，大于0的值则设为0
downside_returns = np.clip(returns, -np.inf, 0)
# 计算年化下行波动率
downside_variance = np.sum(downside_returns ** 2) / n
downside_deviation = np.sqrt(downside_variance * 244)

# 简单年化收益率 = 投资组合的平均超额收益率 * 年化期数
return_mean = np.mean(returns) * annual_periods

# 索提诺比率 = 简单年化收益率 / 年化下行波动率
sortino = return_mean / downside_deviation

```

## 3. 用复合年化收益率计算索提诺比率

复合年化收益率法代码的前半部分跟简单年化收益率法是相同的，只是年化收益率的计算方法不同，这里只列出差异部分的代码：

```python 


# 索提诺比率：使用复合年化收益率
# 复合年化收益
years = n / annual_periods  # 投资年数
total = np.prod(1 + returns) - 1  # 总收益率
annualized_return = abs(total + 1.0) ** (1.0 / years) - 1  # 复合年化收益率

# 索提诺比率 = 复合年化收益率 / 年化下行波动率
sortino = annualized_return / downside_deviation

```

