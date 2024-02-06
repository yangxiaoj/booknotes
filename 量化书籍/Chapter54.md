# 从零学量化54：QuantStats库之可视化分析中文指南（一）
QuantStats 是一个开源的量化交易 Python 库，这个库提供了一系列简单易用的函数，可以计算各种性能指标和进行可视化析，是量化研究常用的工具。

QuantStats 由3个主要模块组成：
### 1. quantstats.stats - 用于计算各种金融指标，如夏普比率、胜率、波动性等。
### 2. quantstats.plots - 用于可视化性能、回撤、滚动统计、月回报等。
### 3. quantstats.reports - 用于生成批量指标报告、批量绘图和创建可另存为 HTML 文件的撕纸（tear sheets）。

上一章《QuantStats库之金融指标中文指南》介绍了quantstats.stats金融指标模块，本章将介绍另外两个模块：quantstats.plots 和 quantstats.reports，这两个模块的作用主要是量化分析的可视化输出，其中quantstats.plots模块用于绘制各种量化分析图表；quantstats.reports用于生成量化分析报告，在报告里包含了完整的量化分析指标和图表。

用QuantStats库进行可视化分析的例子参见前期的系列文章如：《策略的收益评价（使用empyrical和quantstats库）》。

由于 quantstats.plots 和 quantstats.reports 这两个模块的内容较多，因此分为若干篇系列文章来写，本篇为系列的第一篇。

需要注意的是，建议在 Jupyter Notebook 这种交互式的Python代码编辑器中使用 quantstats.plots 和 quantstats.reports 模块，否则可能会有图表显示问题。
## 一、使用方法
使用前首先要导入 QuantStats：
```python

import quantstats as qs

```

然后就可以调用 quantstats.plots 和 quantstats.reports，例如绘制投资组合回报率的直方图：

```python

qs.plots.histogram(returns)

```
生成一个HTML页面的报告，报告中包含投资组合的完整统计指标和相关的数据图表：

```python 

qs.reports.html(returns)

```
## 二、quantstats.plots 函数介绍（按字母排序）
### 1. daily_returns
daily_returns函数是quantstats.plots库中的一个函数，它用于计算并可视化投资组合的每日回报率。它可以帮助投资者和资产管理者了解投资组合的日常表现，并与基准进行比较。

以下是函数的定义和使用方法：

```python 

daily_returns(returns, benchmark, grayscale=False, figsize=(10, 4), fontname='Arial', lw=0.5, log_scale=False, ylabel='Returns', subtitle=True, savefig=None, show=True, prepare_returns=True, active=False)



```

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- benchmark：这是一个数组或序列，代表基准的回报率。这可以帮助你比较投资组合的表现和市场或其他基准的表现。
- grayscale：这是一个布尔值，决定是否以灰度模式显示图表。
- figsize：这是一个元组，代表图表的大小。
- fontname：这是一个字符串，代表图表中使用的字体。
- lw：这是一个数值，代表线条的宽度。
- log_scale：这是一个布尔值，决定是否以对数尺度显示图表。
- ylabel：这是一个字符串，代表y轴的标签。
- subtitle：这是一个布尔值，决定是否显示副标题。
- savefig：这是一个字符串，代表保存图表的文件路径。
- show：这是一个布尔值，决定是否显示图表。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。
- active：这是一个布尔值，决定是否显示超额收益，即投资组合回报减去基准回报。

### 2. distribution
distribution是quantstats.plots库中的一个函数，它用于绘制投资组合回报的分布图。分布图可以帮助投资者和资产管理者了解投资组合回报的概率分布，这对于评估投资策略的风险和收益特性很有帮助。

以下是函数的定义和使用方法：

```python 

distribution(returns, fontname='Arial', grayscale=False, ylabel=True, figsize=(10, 6), subtitle=True, compounded=True, savefig=None, show=True, title=None, prepare_returns=True)


```
- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- fontname：这是一个字符串，代表图表中使用的字体。
- grayscale：这是一个布尔值，决定是否以灰度模式显示图表。
- ylabel：这是一个布尔值，决定是否在图表中显示y轴的标签。
- figsize：这是一个元组，代表图表的大小。
- subtitle：这是一个布尔值，决定是否显示副标题。
- compounded：这是一个布尔值，决定是否需要复合收益率。如果为True，函数将使用复合收益率来计算分布。
- savefig：这是一个字符串，代表保存图表的文件路径。
- show：这是一个布尔值，决定是否显示图表。
- title：这是一个字符串，代表图表的标题。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

### 3. drawdown
drawdown是quantstats.plots库中的一个函数，它用于计算和绘制投资组合的最大回撤。最大回撤是一种评估投资风险的重要指标，它表示投资组合从最高点到最低点的最大跌幅，可以反映出投资组合在极端不利市场条件下可能损失的价值。

以下是函数的定义和使用方法：
```python

drawdown(returns, grayscale=False, figsize=(10, 5), fontname='Arial', lw=1, log_scale=False, match_volatility=False, compound=False, ylabel='Drawdown', resample=None, subtitle=True, savefig=None, show=True)

```

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- grayscale：这是一个布尔值，决定是否以灰度模式显示图表。
- figsize：这是一个元组，代表图表的大小。
- fontname：这是一个字符串，代表图表中使用的字体。
- lw：这是一个数值，代表线条的宽度。
- log_scale：这是一个布尔值，决定是否以对数尺度显示图表。
- match_volatility：这是一个布尔值，如果为True，会调整投资组合的波动率以匹配基准的波动率。
- compound：这是一个布尔值，决定是否需要复合收益率。如果为True，函数将使用复合收益率来计算回撤。
- ylabel：这是一个字符串，代表y轴的标签。
- resample：这是一个字符串，用于指定重采样的频率。例如，你可以设置为'Q'表示按季度重采样，'M'表示按月重采样。
- subtitle：这是一个布尔值，决定是否显示副标题。
- savefig：这是一个字符串，代表保存图表的文件路径。
- show：这是一个布尔值，决定是否显示图表。

（未完待续）

