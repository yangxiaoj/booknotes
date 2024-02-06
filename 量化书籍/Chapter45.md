# 从零学量化45：QuantStats库之金融指标中文指南（一）

QuantStats 是一个开源的 Python 库，专门为量化交易策略的分析和开发而设计。这个库提供了一系列简单易用的函数，允许你计算各种性能指标，生成美观的图表，以及进行深度的策略分析，是量化研究常用的工具。

QuantStats 由3个主要模块组成：

### 1. quantstats.stats - 用于计算各种金融指标，如夏普比率、胜率、波动性等。
### 2. quantstats.plots - 用于可视化性能、回撤、滚动统计、月回报等。
### 3. quantstats.reports - 用于生成批量指标报告、批量绘图和创建可另存为 HTML 文件的撕纸（tear sheets）。

现介绍第一个模块——金融指标模块的使用。QuantStats库实现的金融指标非常多，因此分为若干篇来写。
## 一、安装 QuantStats
安装 QuantStats 非常简单，可以用以下两种安装方法：

1. 用 pip 安装：
```python

pip install quantstats --upgrade --no-cache-dir

```
2. 用 conda 安装：

```python 

conda install -c ranaroussi quantstats

```
## 二、 使用金融指标库 quantstats.stats

使用前首先要导入 QuantStats：
```python

import quantstats as qs

```
然后就可以调用 quantstats.stats 的相关函数，例如计算年化收益率：
```python

annual_return = qs.stats.cagr(returns)

```
## 三、quantstats.stats 金融指标函数介绍（按字母排序）
### 1. adjusted_sortino(returns, rf=0, periods=252, annualize=True, smart=False)
adjusted_sortino 是 QuantStats 库中的一个函数，用于计算 Jack Schwager 版本的 Sortino 比率。

以下是参数的解释：

- returns：投资组合或策略的回报率序列。
- rf：无风险利率，默认值为0。这是一个表示无风险投资（如国库券）年回报率的十进制数。
- periods：年度期数，默认值为252（一年交易日的通常数量）。
- annualize：是否对 Sortino 比率进行年化处理，默认值为True。如果此参数设为 True，那么 Sortino 比率将会被转换为年化值。
- smart：是否使用 "smart" (即去除极值) 方式计算 Sortino 比率，默认值为 False。

Sortino 比率是一个风险调整后的性能度量标准，类似于 Sharpe 比率，但它只考虑下行波动性，而不是总波动性。这意味着 Sortino 比率只惩罚负面的波动性，而不考虑正面的波动性。这对于许多投资者来说更具吸引力，因为他们只关心损失，而不关心盈利的不确定性。
### 2. autocorr_penalty(returns, prepare_returns=False)
autocorr_penalty 是 QuantStats 库中的一个函数，用于计算考虑了自相关性的度量。

以下是参数的解释：

- returns：投资组合或策略的回报率序列。
- prepare_returns：是否对 returns 进行预处理：将价格数据转换为回报率，并根据需要将回报率转换为超额回报。同时，它也会对正无穷、负无穷和NaN数据进行清理。

自相关是一种统计性质，表示一个时间序列与其自身的滞后版本之间的关联性。在金融上，自相关性可以帮助我们理解今天的回报是否会影响明天或未来的回报。
### 3. avg_loss(returns, aggregate=None, compounded=True, prepare_returns=True)
avg_loss 是 QuantStats 库中的一个函数，用于计算一段时间内的平均损失。这个函数计算的是负回报（即损失）的平均值。
以下是参数的解释：

- returns：投资组合或策略的回报率序列。
- aggregate：聚合的频率，如 'A'（年度），'M'（月度），'W'（周度），'D'（日度）。默认情况下，不进行聚合。
- compounded：是否使用复利方式计算平均损失，默认值为True。
- prepare_returns：是否对 returns 进行预处理：将价格数据转换为回报率，并根据需要将回报率转换为超额回报。同时，它也会对正无穷、负无穷和NaN数据进行清理。

这个函数只考虑负回报，也就是说它只关心损失。此外，如果 compounded 参数设置为 True，这个函数将使用连续复利公式来计算平均损失。否则，它将直接计算损失的算术平均值。

这个度量标准可以帮助投资者理解他们的投资策略在不利市场条件下可能会遭受多大的损失。
### 4. avg_return(returns, aggregate=None, compounded=True, prepare_returns=True)
avg_return 是 QuantStats 库中的一个函数，用于计算一段时间内的平均回报。这个函数计算的是回报的平均值。

以下是参数的解释：

- returns：投资组合或策略的回报率序列。
- aggregate：聚合的频率，例如 'A'（年度），'M'（月度），'W'（周度），'D'（日度）。默认情况下，不进行聚合。
- compounded：是否使用复利方式计算平均回报，默认值为True。
- prepare_returns：是否对 returns 进行预处理：将价格数据转换为回报率，并根据需要将回报率转换为超额回报。同时，它也会对正无穷、负无穷和NaN数据进行清理。

这个函数将计算所有回报（包括正回报和负回报）的平均值。如果 compounded 参数设置为 True，这个函数将使用连续复利公式来计算平均回报。否则，它将直接计算回报的算术平均值。

这个度量标准可以帮助投资者理解他们的投资策略在一段时间内的平均性能。
### 5. avg_win(returns, aggregate=None, compounded=True, prepare_returns=True)
avg_win 是 QuantStats 库中的一个函数，用于计算一段时间内的平均盈利。这个函数专注于计算正收益（即盈利）的平均值。

以下是参数的解释：

- returns：投资组合或策略的回报率序列。
- aggregate：聚合的频率，如 'A'（年度），'M'（月度），'W'（周度），'D'（日度）。默认情况下，不进行聚合。
- compounded：是否使用复利方式计算平均盈利，默认值为True。
- prepare_returns：是否需要准备回报序列，默认为 True。如果设置为 True，回报序列将被转换为百分比形式并进行了日度化处理。

这个函数只考虑正回报，也就是说它只关心盈利。此外，如果 compounded 参数设置为 True，这个函数将使用连续复利公式来计算平均盈利。否则，它将直接计算盈利的算术平均值。

这个度量标准可以帮助投资者理解他们的投资策略在有利市场条件下可能会获得多大的盈利。
### 6. best(returns, aggregate=None, compounded=True, prepare_returns=True)
best 是 QuantStats 库中的一个函数，用于计算一段时间内的最佳回报。这个函数返回的是回报序列中的最大值。

以下是参数的解释：

- returns：投资组合或策略的回报率序列。
- aggregate：聚合的频率，如 'A'（年度），'M'（月度），'W'（周度），'D'（日度）。默认情况下，不进行聚合。
- compounded：是否使用复利方式计算最佳回报，默认值为True。
- prepare_returns：是否对 returns 进行预处理，将价格数据转换为回报率，并根据需要将回报率转换为超额回报。同时，它也会对正无穷、负无穷和NaN数据进行清理。

这个函数将返回给定回报序列中的最大值，也就是说，它找出的是投资策略在一段时间内的最佳表现。如果 compounded 参数设置为 True，这个函数将使用连续复利公式来计算最佳回报。否则，它将直接返回回报序列中的最大值。

这个度量标准可以帮助投资者理解他们的投资策略在最理想的市场条件下可能会达到的最高盈利。
### 7. cagr(returns, rf=0.0, compounded=True, periods=252)
cagr 是 QuantStats 库中的一个函数，用于计算复合年化增长率（CAGR%）。复合年化增长率是一个投资的平均年度增长率，它假设投资的收益是被再投资的，并且增长是复合的。

以下是参数的解释：

- returns：投资组合或策略的回报率序列。
- rf：无风险利率，默认值为0。这是一个无风险投资（如国库券）的年回报率。如果 rf 是非零的，你必须指定 periods 参数。在这种情况下，假定 rf 是以年化形式表示的。
- compounded：是否使用复利方式计算 CAGR，默认值为True。
- periods：年度期数，默认值为252（一年交易日的通常数量）。

CAGR 是一个重要的投资度量，它提供了一个投资组合或策略在一段时间内的平均年度增长率。这是一个非常有用的度量，因为它可以帮助投资者理解他们的投资在长期内的增长情况。
### 8. calmar(returns, prepare_returns=True)
calmar 是 QuantStats 库中的一个函数，用于计算 Calmar 比率。Calmar 比率是一个衡量风险调整后回报的指标，它是复合年化增长率 (CAGR%) 与最大回撤 (MaxDD%) 的比值。

以下是参数的解释：

- returns：投资组合或策略的回报率序列。
- prepare_returns：是否对 returns 进行预处理，将价格数据转换为回报率，并根据需要将回报率转换为超额回报。同时，它也会对正无穷、负无穷和NaN数据进行清理。

Calmar 比率得出的是每单位最大回撤所能获得的复合年化回报。这个比率越高，表明投资策略的风险调整后的回报越好。换句话说，对于具有相同回报的两个策略，具有较低最大回撤的策略将具有较高的 Calmar 比率。

请注意，Calmar 比率只考虑最大回撤，而不考虑回撤的频率或持续时间，因此可能会过度优化那些只有少数几个大回撤的策略。