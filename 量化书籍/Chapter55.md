# 从零学量化55：QuantStats库之可视化分析中文指南（二）
### 4. drawdowns_periods
drawdowns_periods函数是quantstats.plots库中的一个函数，用于计算和绘制投资组合最大的回撤期间。这个函数可以帮助投资者和资产管理者了解投资组合在特定时间段内的可能损失。

以下是函数的参数解释：

```python 

drawdowns_periods(returns, periods=5, lw=1.5, log_scale=False, fontname='Arial', grayscale=False, title=None, figsize=(10, 5), ylabel=True, subtitle=True, compounded=True, savefig=None, show=True, prepare_returns=True)

```

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- periods：这是一个整数，指定要计算最大回撤的时间段数量。默认值为5，代表计算最大的五个回撤时期。
- lw：这是一个数值，代表线条的宽度。
- log_scale：这是一个布尔值，决定是否以对数尺度显示图表。
- fontname：这是一个字符串，代表图表中使用的字体。
- grayscale：这是一个布尔值，决定是否以灰度模式显示图表。
- title：这是一个字符串，代表图表的标题。
- figsize：这是一个元组，代表图表的大小。
- ylabel：这是一个布尔值，决定是否在图表中显示y轴的标签。
- subtitle：这是一个布尔值，决定是否显示副标题。
- compounded：这是一个布尔值，决定是否需要复合收益率。如果为True，函数将使用复合收益率来计算回撤。
- savefig：这是一个字符串，代表保存图表的文件路径。
- show：这是一个布尔值，决定是否显示图表。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

### 5. earnings
earnings函数是quantstats.plots库中的一个函数，它用于计算和绘制投资组合的收益。这个函数可以帮助投资者和资产管理者了解投资策略的收益表现。

以下是函数的参数解释：

```python 

earnings(returns, start_balance=100000.0, mode='comp', grayscale=False, figsize=(10, 6), title='Portfolio Earnings', fontname='Arial', lw=1.5, subtitle=True, savefig=None, show=True)

```
- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- start_balance：这是一个浮点数，代表初始投资额。默认为100000.0。
- mode：这是一个字符串，代表计算收益的模式。'comp'代表复合收益，'sum'代表算术收益。
- grayscale：这是一个布尔值，决定是否以灰度模式显示图表。
- figsize：这是一个元组，代表图表的大小。
- title：这是一个字符串，代表图表的标题。默认为'Portfolio Earnings'。
- fontname：这是一个字符串，代表图表中使用的字体。
- lw：这是一个数值，代表线条的宽度。
- subtitle：这是一个布尔值，决定是否显示副标题。
- savefig：这是一个字符串，代表保存图表的文件路径。
- show：这是一个布尔值，决定是否显示图表。

这个函数是投资分析和策略优化中的一个重要工具，可以帮助投资者和资产管理者更准确地评估投资策略的收益性能并进行可视化展示。
### 6. histogram
histogram函数是quantstats.plots库中的一个函数，它用于绘制投资组合回报率的直方图。这个函数可以帮助投资者和资产管理者了解投资策略的回报率分布情况。

以下是函数的参数解释：

```python 

histogram(returns, benchmark=None, resample='M', fontname='Arial', grayscale=False, figsize=(10, 5), ylabel=True, subtitle=True, compounded=True, savefig=None, show=True, prepare_returns=True)

```

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- benchmark：这是一个可选参数，可以是一个数组或序列，代表基准资产或投资组合的回报率。如果提供了这个参数，函数会同时绘制投资组合和基准的回报率直方图，以便进行比较。
- resample：这是一个字符串，用于指定重采样的频率。例如，你可以设置为'Q'表示按季度重采样，'M'表示按月重采样。
- fontname：这是一个字符串，代表图表中使用的字体。
- rayscale：这是一个布尔值，决定是否以灰度模式显示图表。
- figsize：这是一个元组，代表图表的大小。
- ylabel：这是一个布尔值，决定是否在图表中显示y轴的标签。
- subtitle：这是一个布尔值，决定是否显示副标题。
- compounded：这是一个布尔值，决定是否需要复合收益率。如果为True，函数将使用复合收益率来计算回撤。
- savefig：这是一个字符串，代表保存图表的文件路径。
- show：这是一个布尔值，决定是否显示图表。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

### 7. log_returns
log_returns函数是quantstats.plots库中的一个函数，它用于计算和绘制投资组合的对数收益。对数收益的计算方法是取投资收益的自然对数。这种方法的优点在于，它能够更好地处理投资收益的波动性，并且在数学处理上更为方便。

以下是函数的参数解释：

```python 

log_returns(returns, benchmark=None, grayscale=False, figsize=(10, 5), fontname='Arial', lw=1.5, match_volatility=False, compound=True, cumulative=True, resample=None, ylabel='Cumulative Returns', subtitle=True, savefig=None, show=True, prepare_returns=True)

```
- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。
- benchmark：这是一个可选参数，可以是一个数组或序列，代表基准资产或投资组合的回报率。
- grayscale：这是一个布尔值，决定是否以灰度模式显示图表。
- figsize：这是一个元组，代表图表的大小。
- fontname：这是一个字符串，代表图表中使用的字体。
- lw：这是一个浮点数，代表线条的宽度。
- match_volatility：这是一个布尔值，决定是否要调整投资组合和基准的波动性，使其相同。如果为True，函数会调整投资组合和基准的标准差，使其相同。
- compound：这是一个布尔值，决定是否计算复合对数收益。
- cumulative：这是一个布尔值，决定是否计算累积对数收益。
- resample：这是一个字符串或None，用于指定重采样的频率。例如，你可以设置为'Q'表示按季度重采样，'M'表示按月重采样。
- ylabel：这是一个字符串，代表y轴的标签。
- subtitle：这是一个布尔值，决定是否显示副标题。
- savefig：这是一个字符串，代表保存图表的文件路径。
- show：这是一个布尔值，决定是否显示图表。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

（未完待续）
