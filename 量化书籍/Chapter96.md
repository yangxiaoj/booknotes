# 量化实战入门96—动量类指标详解：CTI / DM / ER / ERI / FISHT 

本文介绍以下几个技术指标：CTI、DM、ER、ERI、FISHT。这几个指标都属于动量类型的指标。在投资中，动量指的是价格沿着一个方向前进的持续性。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. CTI（Correlation Trend Indicator，相关性趋势指标）

相关性趋势指标 CTI 是计算价格时间序列与[1, 2, ..., n]的相关系数，值的范围从-1到1。CTI可以用作市场趋势的一个指标。
CTI 的使用方法：

1）判断趋势强度：CTI的值可以帮助投资者判断市场的趋势强度。当CTI的值接近1时，表示价格走势与正向直线非常接近，可能说明市场存在强烈的上升趋势。当CTI的值接近-1时，表示价格走势与负向直线非常接近，可能说明市场存在强烈的下降趋势。

2）发现趋势变化：CTI的值的变化可以帮助投资者发现市场趋势的变化。当CTI的值从正数转为负数时，可能表示市场的上升趋势正在减弱，可能是一个卖出信号。当CTI的值从负数转为正数时，可能表示市场的下降趋势正在减弱，可能是一个买入信号。

3）制定交易策略：投资者可以根据CTI的值来制定交易策略。例如，如果CTI的值接近1，投资者可能会选择买入，预期价格会继续上涨。如果CTI的值接近-1，投资者可能会选择卖出，预期价格会继续下跌。

该指标在 Pandas TA 库中的函数是：

```python 

cti(close, length=None, offset=None, **kwargs)

```

## 2. DM（Directional Movement，定向移动指标）
定向移动指标是由J. Welles Wilder开发的，试图确定资产价格的移动方向。它由三个部分组成：平均方向指数（Average Directional Index，ADX），正定向指标（Plus Directional Indicator，+DI）和负定向指标（Minus Directional Indicator，-DI）。

DMI 的计算方法：

1）+DI：衡量上升趋势的强度。当今天的最高价比昨天的最高价高时，我们称之为“正定向移动”（Positive Directional Movement，+DM）。+DI 是 +DM 除以真实范围（True Range，TR）的平均值，再乘以 100，得到百分比形式的 +DI。

2）-DI：衡量下降趋势的强度。当今天的最低价比昨天的最低价低时，我们称之为“负定向移动”（Negative Directional Movement，-DM）。-DI 是 -DM 除以 TR 的平均值，再乘以 100，得到百分比形式的 -DI。

3）ADX：衡量趋势的强度，无论这个趋势是上升还是下降。ADX 是 +DI 和 -DI 差值的绝对值除以 +DI 和 -DI 的总和，再乘以 100，得到百分比形式的 ADX。

DMI 的使用方法：

1）确定趋势存在：如果 ADX 值大于 20 或 25，通常认为存在趋势。如果 ADX 值低于这个值，可能表示市场处于无趋势或者是震荡状态。

2）判断趋势方向：当 +DI 大于 -DI，可能表示存在上升趋势。当 -DI 大于 +DI，可能表示存在下降趋势。

3）发现趋势强度：ADX 值可以帮助投资者判断趋势的强度。ADX 值越高，表示趋势越强。ADX 值越低，表示趋势越弱。

4）发现趋势可能的改变：当 +DI 和 -DI 交叉时，可能表示趋势的改变。例如，如果 +DI 上穿 -DI，可能表示上升趋势的开始。如果 -DI 上穿 +DI，可能表示下降趋势的开始。

该指标在 Pandas TA 库中的函数是：

```python 

dm(high, low, length=None, mamode=None, talib=None, drift=None, offset=None, **kwargs)

```

## 3. ER（Efficiency Ratio，效率比率）
效率比率（Efficiency Ratio，ER）是由 Perry Kaufman 提出的一种技术指标，用于衡量市场价格变动的效率。这个指标的核心思想是：价格趋势明显的市场（无论是上升还是下降）具有高效率，而在横盘或者震荡的市场效率较低。

ER 的计算公式如下：

```python
ER = Change / Volatility

```

其中，"Change" 是一定时间内（例如10天或14天）价格的绝对变动，"Volatility" 是这个时间内每天价格变动（无论上升还是下降）的总和。

ER 的值范围在 0 到 1 之间：

- 当 ER 接近 1 时，表示市场的变动效率高，可能存在明显的上涨或下跌趋势。

- 当 ER 接近 0 时，表示市场的变动效率低，可能处于横盘或者震荡状态。

ER 的使用方法：

1）判断市场状态：根据 ER 的值，投资者可以判断市场是处于趋势市场还是震荡市场。如果 ER 的值接近 1，可能表示市场处于趋势市场；如果 ER 的值接近 0，可能表示市场处于震荡市场。

2）调整交易策略：在趋势市场，投资者可能会选择跟随趋势的交易策略，例如使用均线系统。在震荡市场，投资者可能会选择反转交易策略，例如使用震荡指标。

3）结合其他指标：ER 通常与适应性移动平均（Adaptive Moving Average，AMA）等其他指标一起使用，以创建适应市场变化的交易系统。

该指标在 Pandas TA 库中的函数是：

```python 

er(close, length=None, drift=None, offset=None, **kwargs)

```
## 4. ERI（Elder Ray Index，艾尔德雷指数）

艾尔德雷指数包含牛市力量指数（Bull Power）和熊市力量指数（Bear Power）。

牛市力量和熊市力量的计算基于高、低和收盘价。牛市力量是由最高价减去收盘价的指数移动平均（EMA）得出的。熊市力量是由最低价减去收盘价的EMA得出的。

具体计算如下：

```python 

BULLPOWER = high - EMA(close, length)
BEARPOWER = low - EMA(close, length)

```

ERI 的使用方法：

1）确定买卖点：当熊市力量在下降的过程中首次变为正数，可以作为买入信号；当牛市力量在上升的过程中首次变为负数，可以作为卖出信号。

2）发现背离：如果价格创新高，但牛市力量未能创新高，预示着价格可能会下跌。反之，如果价格创新低，但熊市力量未能创新低，预示着价格可能会上涨。

3）判断市场状态：如果牛市力量和熊市力量都在增大，可能预示市场处于强势；如果牛市力量和熊市力量都在减小，可能预示市场处于弱势。

该指标在 Pandas TA 库中的函数是：

```python

eri(high, low, close, length=None, offset=None, **kwargs)

```

## 5. FISHT（Fisher Transform，Fisher变换指标）

Fisher变换能将任何概率分布转换为正态分布，在金融分析中，它使价格分布更接近正态分布，从而提高其他技术指标的预测准确性。

Fisher变换指标的具体计算步骤比较多，可以在 Pandas TA 中通过 help(ta.fisher) 命令查询。

Fisher 变换的使用方法：

1）趋势确认：Fisher 变换的值可以帮助确认价格趋势。当 Fisher 变换的值上升时，可能表示价格处于上升趋势。当 Fisher 变换的值下降时，可能表示价格处于下降趋势。

2）识别重要的价格反转：当 Fisher 变换的两条线（FISHER 和 SIGNAL）交叉时，可能表示一个重要的价格反转。如果 FISHER 线从下向上穿过 SIGNAL 线，可能表示一个上涨的价格反转。如果 FISHER 线从上向下穿过 SIGNAL 线，可能表示一个下跌的价格反转。

3）判断市场过度买入或过度卖出：由于 Fisher 变换的目标是使价格分布更接近正态分布，极值（即高于或低于大部分值的值）在 Fisher 变换中更容易识别。Fisher 变换的值通常在 -1 和 1 之间。如果 Fisher 变换的值接近 1，可能表示市场过度买入。如果 Fisher 变换的值接近 -1，可能表示市场过度卖出。

4）预测市场转折点：Fisher 变换的值在达到极大值或极小值后往往会反转。因此，当 Fisher 变换的值达到极大值或极小值，可能预示市场即将反转。

该指标在 Pandas TA 库中的函数是：
```python

fisher(high, low, length=None, signal=None, offset=None, **kwargs)

```