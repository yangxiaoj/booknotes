# 从零学量化94—动量类指标详解：CCI / CFO / CG / CMO / Coppock 

本文介绍以下几个技术指标：CCI、CFO、CG、CMO、Coppock。这几个指标都属于动量类型的指标。在投资中，动量指的是价格沿着一个方向前进的持续性。

振荡器（Oscillator）是一种常见的动量指标，它可以通过衡量资产价格的动量或速度来预测未来的市场走势。称为“振荡器”的原因在于这类指标的数值通常围绕某个中心点或者区间“振荡”或波动。振荡器指标可以分为两大类：

1）界限振荡器（Bounded Oscillator）：这类振荡器的值通常被限制在一个固定的范围内，比如0到100。当读数接近上限时，市场可能处于过度买入状态，可能会出现价格回落；当读数接近下限时，市场可能处于过度卖出状态，可能会出现价格反弹。

2）非界限振荡器（Unbounded Oscillator）：这类振荡器没有固定的最大值和最小值，但它的数值仍然会围绕某个值上下波动，反映出价格动量的变化。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。

## 1. CCI（Commodity Channel Index，商品频道指数）

CCI是一个动量振荡器，主要用于识别相对于平均值的超买和超卖水平。CCI最初是为了分析商品市场，但现在已经被广泛用于分析各种金融市场。
CCI的计算公式如下：

```python

tp = typical_price = hlc3 = (high + low + close) / 3
mean_tp = SMA(tp, length)
mad_tp = MAD(tp, length)
CCI = (tp - mean_tp) / (c * mad_tp)

```

其中，SMA是简单移动平均函数，MAD是平均绝对偏差函数。

CCI通常在+100到-100的范围内波动，但并无上下限。CCI的使用方法是：

1）过度买入或过度卖出：当CCI超过+100时，可能表示市场过度买入，可能会有价格回落；当CCI低于-100时，可能表示市场过度卖出，可能会有价格反弹。

2）发现背离：如果价格走势与CCI走势出现背离，可能预示着市场即将发生转折。例如，如果价格创新高，但CCI没有创新高，可能预示着上涨趋势即将结束。

3）趋势确认：CCI也可以用来确认价格趋势。如果CCI和价格都在上升，那么可能确认上涨趋势；如果CCI和价格都在下降，那么可能确认下跌趋势。

该指标在 Pandas TA 库中的函数是：

```python 

cci(high, low, close, length=None, c=None, talib=None, offset=None, **kwargs)

```
## 
2. CFO（Chande Forcast Oscillator，Chande预测震荡器）

CFO是一个振荡器，它比较了实际价格和通过线性回归预测的价格。

CFO的计算公式如下：

```python

CFO = scalar * (close - LINERREG(length)) / close

```

其中，LINERREG(length) 是 length 期的线性回归预测值，"scalar" 是用于调整 CFO 的比例尺。默认的参数设置是 length=9，scalar=100。

CFO 的使用方法：

1）预测价格变动：由于 CFO 计算的是实际价格与预测价格之间的百分比差异，因此，它可以用来预测价格的变动。如果 CFO 为正，可能表示价格将上涨；如果 CFO 为负，可能表示价格将下跌。

2）信号线：当 CFO 上穿 0 线，可能是一个买入信号；当 CFO 下穿 0 线，可能是一个卖出信号。

3）过度买入或过度卖出：当 CFO 达到极度高或低的水平时，可能表示市场过度买入或过度卖出。这可能是一个反转信号，提示价格可能会向反方向移动。

4）发现背离：如果价格走势与 CFO 走势出现背离，可能预示着市场即将发生转折。例如，如果价格创新高，但 CFO 没有创新高，可能预示着上涨趋势即将结束。

该指标在 Pandas TA 库中的函数是：

```python

cfo(close, length=None, scalar=None, drift=None, offset=None, **kwargs)

```

## 3. CG（Center of Gravity，重心指标）

重心指标 CG 是由 John Ehlers 开发的一种技术指标，用于预测价格趋势的反转点。CG 是基于物理学中的重心概念，可以帮助投资者找出市场的不均衡点，从而预测趋势的改变。

CG的计算公式较为复杂，其主要思想是将价格（或其他指标）视为一个物理系统，计算该系统的重心。具体的计算过程涉及到复杂的滤波和数学计算。

CG的使用方法：

1）发现趋势反转：CG的主要用途是预测趋势反转。当CG指标从高位下降，或者从低位上升，可能预示着价格趋势的反转。重心指标的一个主要特点是其低延迟特性，这意味着它可以迅速响应价格的变化，因此可能更早地识别出市场的转折点。

2）生成交易信号：当CG线穿过零线时，可能产生买卖信号。当CG线从下方穿过零线，可能是一个买入信号；当CG线从上方穿过零线，可能是一个卖出信号。

3）预测价格波动：CG还可以用来预测价格的波动。CG指标的高低通常与价格的波动程度有关。当CG值较高时，可能预示着价格的高波动，当CG值较低时，可能预示着价格的低波动。

该指标在 Pandas TA 库中的函数是：

```python

cg(close, length=None, offset=None, **kwargs)

```

## 4. CMO（Chande Momentum Oscillator，Chande动量振荡器）

CMO指标是一种动量振荡器，它比较了资产在过去一段时间内上涨和下跌的幅度，用于衡量资产价格的动量。

CMO的计算公式如下：

```python 

CMO = scalar * (PSUM - NSUM) / (PSUM + NSUM)

```

其中：

- PSUM 代表在给定周期内上涨的天数的和，

- NSUM 代表在给定周期内下跌的天数的和，

- scalar 是一个浮点数，表示放大的程度，默认值是100。

CMO 的使用方法：

1）过度买入或过度卖出：CMO 的值范围是 -100 到 +100。当 CMO 超过 +50，可能表示市场过度买入，可能会有价格回落；当 CMO 低于 -50，可能表示市场过度卖出，可能会有价格反弹。

2）信号线：CMO 可以和其自身的移动平均线一起使用来生成交易信号。当 CMO 线上穿其移动平均线，可能是一个买入信号；当 CMO 线下穿其移动平均线，可能是一个卖出信号。

3）发现背离：如果价格走势与 CMO 走势出现背离，可能预示着市场即将发生转折。例如，如果价格创新高，但 CMO 没有创新高，可能预示着上涨趋势即将结束。

该指标在 Pandas TA 库中的函数是：

```python

cmo(close, length=None, scalar=None, talib=None, drift=None, offset=None, **kwargs)

```
## 5. Coppock曲线（Coppock Curve）

Coppock曲线（最初称为 "Trendex Model"）是一个动量指标，用以识别股票市场的长期价格底部。Coppock曲线基于的主要理念是，市场底部通常伴随着价格的下跌速度放缓。

Coppock曲线的计算公式如下：

```python

Coppock Curve = WMA[10] of (ROC[14] + ROC[11])

```
在这个公式中，"ROC" 代表变动率 (Rate of Change)，"WMA" 代表加权移动平均数 (Weighted Moving Average)。ROC[14] 和 ROC[11] 分别计算过去14期和11期的价格变动率，然后将两者相加并计算其10期的加权移动平均数。

Coppock曲线设计用于月度时间尺度。尽管设计为月度使用，但也可以进行每日计算，比如将周期转换为294天和231天的变化率，以及210天的加权移动平均。

Coppock曲线的使用方法：

1）识别市场底部：Coppock曲线的主要用途是识别市场底部。当Coppock曲线从负值转向正值时，这可能预示着市场已经触底，是一个买入信号。

2）趋势确认：Coppock曲线也可以用作趋势确认工具。当Coppock曲线保持正值并上升时，这可能表示市场处于牛市状态。相反，如果Coppock曲线保持负值并下降，这可能表示市场处于熊市状态。

该指标在 Pandas TA 库中的函数是：

```python

coppock(close, length=None, fast=None, slow=None, offset=None, **kwargs)

```
