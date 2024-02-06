# 从零学量化57：QuantStats库之可视化分析中文指南（四）

### 12. rolling_sharpe
rolling_sharpe 函数是quantstats.plots库中的一个函数，它用于计算并可视化投资策略的滚动夏普比率。

以下是 rolling_sharpe 函数的参数定义：
```python 

rolling_sharpe(returns, benchmark=None, rf=0.0, period=126, period_label='6-Months', periods_per_year=252, lw=1.25, fontname='Arial', grayscale=False, figsize=(10, 3), ylabel='Sharpe', subtitle=True, savefig=None, show=True)

```
- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。
- benchmark：这是一个可选参数，可以是一个数组或序列，代表基准资产或投资组合的回报率。如果为 None，则不使用基准进行比较。
- rf：表示无风险利率的数字。默认为 0.0。
- period：表示滚动窗口的大小，单位为交易日。
- period_label：表示滚动窗口的标签，用于绘图。
- periods_per_year：表示每年的交易日数量。默认为 252，适用于大多数股票市场。
- lw：一个浮点数，表示图的线宽。
- fontname：一个字符串，表示图的字体。
- grayscale：一个布尔值，表示是否以灰度模式绘制图形。
- figsize：一个元组，表示图形的大小。
- ylabel：一个字符串，表示 y 轴的标签。
- subtitle：一个布尔值，表示是否在图中包含副标题。
- savefig：一个字符串，表示保存图形的文件路径。如果为 None，则不保存图形。
- show：一个布尔值，表示是否显示图形。

在内部，这个函数会计算投资策略在滚动窗口期间的夏普比率，然后绘制滚动夏普比率图。如果 show 参数为 False，则函数会返回图形对象，以便在函数外部进行进一步操作。
### 13. rolling_sortino
quantstats.plots中的 rolling_sortino 函数是用于计算并可视化投资策略的滚动索提诺比率。

索提诺比率是类似于夏普比率的风险调整回报度量，但它只考虑下行风险（负收益）。索提诺比率越高，表明投资策略在承受下行风险的同时实现了更高的回报。

以下是 rolling_sortino 函数的参数定义：

```python 

rolling_sortino(returns, benchmark=None, rf=0.0, period=126, period_label='6-Months', periods_per_year=252, lw=1.25, fontname='Arial', grayscale=False, figsize=(10, 3), ylabel='Sortino', subtitle=True, savefig=None, show=True)

```
- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。
- benchmark：这是一个可选参数，可以是一个数组或序列，代表基准资产或投资组合的回报率。如果为 None，则不使用基准进行比较。
- rf：表示无风险利率的数字。默认为 0.0。
- period：表示滚动窗口的大小，单位为交易日。
- period_label：表示滚动窗口的标签，用于绘图。
- periods_per_year：表示每年的交易日数量。默认为 252，适用于大多数股票市场。
- lw：一个浮点数，表示图的线宽。
- fontname：一个字符串，表示图的字体。
- grayscale：一个布尔值，表示是否以灰度模式绘制图形。
- figsize：一个元组，表示图形的大小。
- ylabel：一个字符串，表示 y 轴的标签。
- subtitle：一个布尔值，表示是否在图中包含副标题。
- savefig：一个字符串，表示保存图形的文件路径。如果为 None，则不保存图形。
- show：一个布尔值，表示是否显示图形。

这个函数会计算投资策略在滚动窗口期间的索提诺比率，然后绘制滚动索提诺比率图。如果 show 参数为 False，则函数会返回图形对象，以便在函数外部进行进一步操作。
### 14. rolling_volatility
quantstats.stats库中的quantstats.plots函数用于计算并可视化投资策略的滚动波动率。

波动率是衡量投资回报变化或分散程度的统计指标，通常用于评估投资风险。高波动率可能意味着投资的不确定性较大。

以下是rolling_volatility函数的参数定义：

```python 

rolling_volatility(returns, benchmark=None, period=126, period_label='6-Months', periods_per_year=252, lw=1.5, fontname='Arial', grayscale=False, figsize=(10, 3), ylabel='Volatility', subtitle=True, savefig=None, show=True)

```
- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。
- benchmark：这是一个可选参数，可以是一个数组或序列，代表基准资产或投资组合的回报率。如果为 None，则不使用基准进行比较。
- period：表示滚动窗口的大小，单位为交易日。
- period_label：表示滚动窗口的标签，用于绘图。
- periods_per_year：表示每年的交易日数量。默认为 252，适用于大多数股票市场。
- lw：一个浮点数，表示图的线宽。
- fontname：一个字符串，表示图的字体。
- grayscale：一个布尔值，表示是否以灰度模式绘制图形。
- figsize：一个元组，表示图形的大小。
- ylabel：一个字符串，表示 y 轴的标签。
- subtitle：一个布尔值，表示是否在图中包含副标题。
- savefig：一个字符串，表示保存图形的文件路径。如果为 None，则不保存图形。
- show：一个布尔值，表示是否显示图形。

这个函数会计算投资策略在滚动窗口期间的波动率，然后绘制滚动波动率图。如果 show 参数为 False，则函数会返回图形对象，以便在函数外部进行进一步操作。
### 15. snapshot
snapshot 是quantstats.plots库中的一个函数，用于创建投资组合摘要可视化图的函数。它接收一系列参数后，会根据这些参数生成包含三个子图的图形，这三个子图分别是累积收益、最大回撤和日收益。

函数定义中的参数如下：
```python 

snapshot(returns, grayscale=False, figsize=(10, 8), title='Portfolio Summary', fontname='Arial', lw=1.5, mode='comp', subtitle=True, savefig=None, show=True, log_scale=False, **kwargs)

```
- returns: pandas Series 或 DataFrame，代表投资组合的历史收益。
- grayscale: 布尔值，决定图表是否为灰度模式。
- figsize: 元组，表示图形的大小，格式为 (宽度, 高度)。
- title: 字符串，图形的标题。
- fontname: 字符串，用于标题和子标题的字体名称。
- lw: 浮点数，线的宽度。
- mode: 字符串，计算投资组合收益的模式。
- subtitle: 布尔值，决定是否在图形上显示子标题。
- savefig: 字符串或字典，表示保存图形的路径或参数。
- show: 布尔值，决定是否显示图形。
- log_scale: 布尔值，决定是否在对数尺度上显示图形。
- **kwargs: 其他参数，如 strategy_col，用于指定在 DataFrame 中表示策略的列名。

### 16. yearly_returns
quantstats.plots库中的yearly_returns函数用于计算并可视化投资策略的年度收益。

以下是yearly_returns函数的参数定义：
```python 

yearly_returns(returns, benchmark=None, fontname='Arial', grayscale=False, hlw=1.5, hlcolor='red', hllabel='', match_volatility=False, log_scale=False, figsize=(10, 5), ylabel=True, subtitle=True, compounded=True, savefig=None, show=True, prepare_returns=True)

```

- returns：一个 pandas Series 或 DataFrame，表示投资策略的收益。
- benchmark：一个 pandas Series 或 DataFrame，表示基准的收益，或者一个字符串，用于获取基准数据。如果为 None，则不使用基准进行比较。
- fontname：一个字符串，表示图的字体。
- grayscale：一个布尔值，表示是否以灰度模式绘制图形。
- hlw：一个浮点数，表示高亮线的线宽。
- hlcolor：一个字符串，表示高亮线的颜色。
- hllabel：一个字符串，表示高亮线的标签。
- match_volatility：一个布尔值，表示是否将投资策略的波动率匹配到基准的波动率。
- log_scale：一个布尔值，表示是否在对数尺度上绘制图形。
- figsize：一个元组，表示图形的大小。
- ylabel：一个布尔值，表示是否在图中包含 y 轴的标签。
- subtitle：一个布尔值，表示是否在图中包含副标题。
- compounded：一个布尔值，表示是否计算复合回报。
- savefig：一个字符串，表示保存图形的文件路径。如果为 None，则不保存图形。
- show：一个布尔值，表示是否显示图形。
- prepare_returns：一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

这个函数会计算投资策略每年的回报，然后绘制年度收益图。如果 show 参数为 False，则函数会返回图形对象，以便在函数外部进行进一步操作。

（未完待续）