# 量化实战入门104—动量类指标详解：RVGI / STC / Slope / SMI

本文介绍以下几个技术指标：RVGI、STC、Slope、SMI。这几个指标都属于动量类型的指标。在投资中，动量指的是价格沿着一个方向前进的持续性。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. RVGI (Relative Vigor Index, 相对活力指数)

RVGI 是一种尝试通过比较其交易范围内的收盘价来衡量趋势强度的技术指标。RVGI 基于一个观点，即在上升趋势中，价格通常会比开盘价高收盘，而在下降趋势中，价格通常会比开盘价低收盘。

RVGI 指标的计算公式如下：

```python 

#1 计算收盘价和开盘价的差值，并计算其 SWMA（对称加权移动平均）
numerator = SUM(SWMA(close - open, swma_length), length)
#2 计算最高价和最低价的差值，并计算其 SWMA
denominator = SUM(SWMA(high - low, swma_length), length)
#3 计算 RVGI
RVGI = numerator / denominator

```

RVGI 的用法是：

1）交叉信号：由于 RVGI 是一个振荡器，它的值通常在一个固定的范围内波动。当 RVGI 线从下方穿过其信号线（通常是 RVGI 的移动平均线）时，这可能是一个买入信号。反之，当 RVGI 线从上方穿过其信号线时，这可能是一个卖出信号。

2）背离：如果价格创新高，但 RVGI 没有创新高，这可能是一个顶部反转的信号。相反，如果价格创新低，但 RVGI 没有创新低，这可能是一个底部反转的信号。

3）趋势确认：RVGI 也可以用来确认当前的趋势。在上升趋势中，RVGI 的值通常会保持在正数范围内。反之，在下降趋势中，RVGI 的值通常会保持在负数范围内。

4）趋势反转：当 RVGI 指标的值从高位下降或从低位上升时，可能表示趋势即将发生反转。

该指标在 Pandas TA 库中的函数是：

```python 

rvgi(open_, high, low, close, length=None, swma_length=None, offset=None, **kwargs)

```

## 2. STC（Schaff Trend Cycle，沙夫趋势周期）

STC 是MACD指标的进化版，结合了两个级联的随机计算和额外的平滑处理。STC不仅返回MACD最初的结果，还返回第一个随机处理及其平滑处理后的结果。

STC 的计算方法是：

1）计算 MACD：两个指数移动平均（EMA）之间的差异。；

2）计算 STC MACD：基于前一步计算出的 MACD，计算其随机值。这通常涉及到两步：首先，找到 MACD 在一个给定周期内（例如10天）的最高高和最低低；然后，计算当前 MACD 与最低低的差异，然后将这个差异除以最高高和最低低的差值。得到的结果乘以100。

3）计算 STC：对上一步计算出的 STC MACD 进行另一个随机计算。这个过程与第二步类似，但现在使用的是 STC MACD 的值，而不是原始的 MACD。

STC 指标的用法有：

1）趋势识别：STC 可以帮助你识别市场的主要趋势。当 STC 上升时，可能表示市场处于上升趋势。反之，当 STC 下降时，可能表示市场处于下降趋势。

2）买卖信号：当 STC 从低点上升并穿过一个特定阈值（例如，从下方穿过 25 线）时，这可能是一个买入信号。相反，当 STC 从高点下降并穿过一个特定阈值（例如，从上方穿过 75 线）时，这可能是一个卖出信号。

3）超买超卖：STC 也可以用来识别可能的超买或超卖条件。当 STC 的值超过 75，市场可能过于买入，可能会有一波下跌。相反，当 STC 的值低于 25，市场可能过于卖出，可能会有一波上涨。

4）背离：如果价格创新高，但 STC 没有创新高，这可能是一个顶部反转的信号。相反，如果价格创新低，但 STC 没有创新低，这可能是一个底部反转的信号。

该指标在 Pandas TA 库中的函数是：

```python 

stc(close, tclength=None, fast=None, slow=None, factor=None, offset=None, **kwargs)

```

## 3. Slope（斜率）

Slope 指标返回一个系列的斜率。

Slope 指标的用法主要包括：

1）趋势确认：Slope 值的正负可以帮助我们确认市场的大致趋势。如果 Slope 值为正，表明价格在增加，市场可能处于上涨趋势中；反之，如果 Slope 值为负，表明价格在下降，市场可能处于下跌趋势中。

2）趋势强度：Slope 值的绝对大小可以反映趋势的强度。Slope 值越大，表明价格变化越快，趋势可能越强；反之，Slope 值越小，表明价格变化越慢，趋势可能越弱。

3）趋势转变：Slope 值的变化可以帮助我们捕捉到可能的趋势转变。如果 Slope 值从正变为负，可能预示着上涨趋势的结束和下跌趋势的开始；反之，如果 Slope 值从负变为正，可能预示着下跌趋势的结束和上涨趋势的开始。

该指标在 Pandas TA 库中的函数是：

```python 

slope(close, length=None, as_angle=None, to_degrees=None, vertical=None, offset=None, **kwargs)

```

## 4. SMI (SMI Ergodic Indicator)

SMI Ergodic 指标（或者称为 Stochastic Momentum Index）是一种动量指标，用来衡量价格的变动速度。SMI Ergodic 指标的计算包括一个主要的 SMI 值，一个信号线，以及一个振荡器值。

SMI Ergodic 指标的计算方法如下：

```python 

# 计算 SMI 指标值。它是使用 True Strength Index 方法计算的，其中 fast 是短期的时间长度（默认为 5），slow 是长期的时间长度（默认为 20）
ERG = TSI(close, fast, slow)
# 计算信号线。它是 SMI 指标值的指数移动平均线，其中 signal 是信号线的时间长度（默认为 5）
Signal = EMA(ERG, signal)
# 计算振荡器值。它是 SMI 指标值和信号线的差
OSC = ERG - Signal

```

SMI Ergodic 指标的用法主要包括：

1）趋势确认：当 SMI 值（ERG）上升并且在 0 以上时，通常表示市场处于上升趋势；当它下降并且在 0 以下时，通常表示市场处于下降趋势。

2）交易信号：当 SMI 值（ERG）从下方穿过信号线（Signal），可能是一个买入信号；当它从上方穿过信号线，可能是一个卖出信号。

3）过度买入或过度卖出：振荡器值（OSC）可以用来识别可能的过度买入或过度卖出的情况。如果 OSC 值达到极高或极低的水平，可能表示市场已经过度买入或过度卖出，存在反转的可能。

该指标在 Pandas TA 库中的函数是：

```python 

smi(close, fast=None, slow=None, signal=None, scalar=None, offset=None, **kwargs)

```