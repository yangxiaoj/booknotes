# 从零学量化56：QuantStats库之可视化分析中文指南（三）
### 8. monthly_heatmap
monthly_heatmap函数是quantstats.plots库中的一个函数，它用于生成投资组合的月度收益热图。这个热图可以帮助投资者和资产管理者了解投资策略在不同月份的收益情况，从而更好地理解投资策略的季节性变化。

以下是函数的参数解释：

```python 

monthly_heatmap(returns, benchmark=None, annot_size=10, figsize=(10, 5), cbar=True, square=False, returns_label='Strategy', compounded=True, eoy=False, grayscale=False, fontname='Arial', ylabel=True, savefig=None, show=True, active=False)

```

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- benchmark：这是一个可选参数，可以是一个数组或序列，代表基准资产或投资组合的回报率。
- annot_size：这是一个整数，代表注释的字体大小。
- figsize：这是一个元组，代表图表的大小。
- cbar：这是一个布尔值，决定是否在图表中显示颜色条。
- square：这是一个布尔值，决定是否以正方形的形式显示热图。
- returns_label：这是一个字符串，代表在图表中显示的回报率标签。
- compounded：这是一个布尔值，决定是否需要复合收益率。如果为True，函数将使用复合收益率来计算回撤。
- eoy：这是一个布尔值，决定是否在每年的最后一个月显示总收益。
- grayscale：这是一个布尔值，决定是否以灰度模式显示图表。
- fontname：这是一个字符串，代表图表中使用的字体。
- ylabel：这是一个布尔值，决定是否在图表中显示y轴的标签。
- savefig：这是一个字符串，代表保存图表的文件路径。
- show：这是一个布尔值，决定是否显示图表。
- active：这是一个布尔值，决定是否只显示投资期间的月份。

### 9. monthly_returns

monthly_returns是quantstats.plots库中的一个函数，它用于计算和绘制每个月的投资回报率。这个函数可以帮助投资者和资产管理者了解投资策略在每个月的表现。

以下是函数的参数解释：

```python 

monthly_returns(returns, annot_size=10, figsize=(10, 5), cbar=True, square=False, compounded=True, eoy=False, grayscale=False, fontname='Arial', ylabel=True, savefig=None, show=True)

```

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。
- annot_size：这是一个整数，代表注释的字体大小。
- figsize：这是一个元组，代表图表的大小。
- cbar：这是一个布尔值，决定是否在图表中显示颜色条。
- square：这是一个布尔值，决定是否以正方形的形式显示热图。
- compounded：这是一个布尔值，决定是否计算复合收益。
- eoy：这是一个布尔值，决定是否在每年的最后一个月显示总收益。
- grayscale：这是一个布尔值，决定是否以灰度模式显示图表。
- fontname：这是一个字符串，代表图表中使用的字体。
- ylabel：这是一个布尔值，决定是否在图表中显示y轴的标签。
- savefig：这是一个字符串，代表保存图表的文件路径。
- show：这是一个布尔值，决定是否显示图表。

### 10. returns
returns是quantstats.plots库中的一个函数，用于绘制给定投资策略的累积回报，还可以选择与基准进行比较。

以下是函数的参数解释：

```python 

returns(returns, benchmark=None, grayscale=False, figsize=(10, 6), fontname='Arial', lw=1.5, match_volatility=False, compound=True, cumulative=True, resample=None, ylabel='Cumulative Returns', subtitle=True, savefig=None, show=True, prepare_returns=True)

```

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- benchmark：这是一个可选参数，可以是一个数组或序列，代表基准资产或投资组合的回报率。
- grayscale：一个布尔值，用于确定是否以灰度模式绘图。
- figsize：一个元组，设置图形的大小。
- fontname：一个字符串，设置图中使用的字体。
- lw：一个浮点数，设置图的线宽。
- match_volatility：一个布尔值，用于确定是否将策略的波动性匹配到基准的波动性。
- compound：一个布尔值，确定是否计算复合回报。
- cumulative：一个布尔值，确定是否计算累积回报。
- resample：一个字符串，设置重新采样回报的频率。它使用 pandas 的偏移别名。
- ylabel：一个字符串，设置图的 y 轴标签。
- subtitle：一个布尔值，确定是否在图中包含副标题。
- savefig：一个字符串，表示保存图形的文件路径。如果为 None，则不保存图形。
- show：一个布尔值，确定是否显示图形。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

### 11. rolling_beta
rolling_beta是quantstats.plots库中的一个函数，用于计算并可视化投资策略相对于基准的滚动贝塔值。

以下是函数的参数解释：

```python 

rolling_beta(returns, benchmark, window1=126, window1_label='6-Months', window2=252, window2_label='12-Months', lw=1.5, fontname='Arial', grayscale=False, figsize=(10, 3), ylabel=True, subtitle=True, savefig=None, show=True, prepare_returns=True)

```
- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- benchmark：可以是一个数组或序列，代表基准资产或投资组合的回报率。
- window1：第一个滚动窗口的大小（以交易日计）。
- window1_label：用于绘图的第一个滚动窗口的标签。
- window2：第二个滚动窗口的大小（以交易日计）。
- window2_label：用于绘图的第二个滚动窗口的标签。
- lw：设置图线的线宽。
- fontname：设置图中的字体。
- grayscale：布尔值，确定图是否以灰度模式绘制。
- figsize：设置图形的大小。
- ylabel：布尔值，确定是否在图中显示y轴的标签。
- subtitle：布尔值，确定是否在图中包含副标题。
- savefig：字符串，指定保存图形的文件路径。如果为 None，则不保存图形。
- show：布尔值，确定是否显示图形。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

这个函数计算并绘制了投资策略相对于基准的滚动贝塔值，这是在两个不同的滚动窗口（由 window1 和 window2 定义）期间进行的。贝塔值是投资组合对市场波动的敏感度的度量，一个高贝塔值的投资组合在市场上涨时表现良好，但在市场下跌时可能表现较差。

（未完待续）