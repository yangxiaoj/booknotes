# 量化实战入门111—趋势类指标详解：ADX / AMAT / AROON 

本文介绍以下几个技术指标：ADX、AMAT、AROON。这几个指标都属于趋势（ Trend）类型的指标，这类主要用于识别和跟踪市场的主要趋势。这些指标可以帮助投资者确定市场的方向（上升、下降或者横盘）以及趋势的强度，从而帮助投资者决定何时进入或退出市场。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见前文《量化宝藏工具箱：技术指标库 Pandas TA 教程》。
## 1. ADX (Average Directional Movement Index，平均方向性指标)
平均方向性指标 (ADX) 是用于量化趋势强度的一个指标，它衡量的是单一方向上的移动量。

ADX 的计算涉及到几个步骤。以下是步骤和公式：

1）计算每日的方向性移动 (+DM 和 -DM)。+DM 是今日最高价和昨日最高价之间的差额，如果今日最高价小于昨日最高价，则+DM为0。-DM是昨日最低价和今日最低价之间的差额，如果今日最低价大于昨日最低价，则-DM为0。

2）计算真实范围 (TR)。TR是以下三者中的最大值：今日最高价和最低价之间的差额，今日最高价和昨日收盘价之间的差额，昨日收盘价和今日最低价之间的差额。

3）计算平滑的+DM，-DM和TR。这通常是通过将昨日的值乘以n-1，然后加上今日的值，最后除以n来实现的。这里的n是用户指定的期间长度。

4）计算+DI和-DI。+DI = (平滑的+DM / 平滑的TR) * 100， -DI = (平滑的-DM / 平滑的TR) * 100。

5）计算DX。DX = (|+DI - -DI| / (+DI + -DI)) * 100。

6）计算ADX。ADX是过去n期的DX的平均值。

ADX 的用法：

1）ADX 是一个无方向的指标，它只衡量市场趋势的强度，而不考虑趋势的方向。ADX 的值的范围是0到100，通常，ADX 值大于25被认为是强趋势的证据，而值小于20被认为是弱趋势或无趋势。ADX可以用来鉴别是否处于趋势市或震荡市，为趋势跟踪策略或反转策略提供决策依据。

2）DMP（+DM）和 DMN（-DM）是用来量化上升和下降趋势强度的指标。DMP 的值表示上升趋势的强度，DMN 的值表示下降趋势的强度。它们的值也是在0到100之间。

3）DMP（+DM）和 DMN（-DM）可以用于判断趋势的方向。当DMP的值大于DMN的值，表示上升趋势较强，可能是一个上涨市。相反，如果DMN的值大于DMP的值，表示下降趋势较强，可能是一个下跌市。

4）DMP 和 DMN 也可以和 ADX 一起使用来判断趋势的强度和方向。例如，如果ADX值大于25，表示市场存在明显趋势，此时如果DMP大于DMN，则表示强势的上升趋势；如果DMN大于DMP，则表示强势的下降趋势。
该指标在 Pandas TA 库中的函数是：

```python 

adx(high, low, close, length=None, lensig=None, scalar=None, mamode=None, drift=None, offset=None, **kwargs)

```
## 2.  AMAT（Archer Moving Averages Trends）
Archer Moving Averages Trends (AMAT) 是一种趋势判断指标，它通过比较两种不同速度的移动平均线来确定趋势，用于识别市场的上升或下降趋势。

计算方法和公式：

AMAT 的计算方法主要是基于两条移动平均线的交叉点。当快速移动平均线从下方穿过慢速移动平均线时，这通常被认为是开始上升趋势的信号。反之，当快速移动平均线从上方穿过慢速移动平均线时，这通常被认为是开始下降趋势的信号。

以下是 AMAT 指标的基本用法：

1）判断市场趋势：当 AMAT 的值大于0，表示快速移动平均线在慢速移动平均线上方，市场处于上升趋势。反之，当 AMAT 的值小于0，表示快速移动平均线在慢速移动平均线下方，市场处于下降趋势。

2）生成交易信号：当 AMAT 从负值变为正值，即快速移动平均线从下方穿过慢速移动平均线，这通常被视为买入信号，因为这可能预示着一个新的上升趋势的开始。相反，当 AMAT 从正值变为负值，即快速移动平均线从上方穿过慢速移动平均线，这通常被视为卖出信号，因为这可能预示着一个新的下降趋势的开始。

3）确定市场动力：AMAT 的绝对值可以视为市场动力的一种度量。如果 AMAT 的值远离0，无论是正向还是负向，都可能表示市场趋势较强。相反，如果 AMAT 的值接近0，可能表示市场趋势不明显或市场正在震荡。

该指标在 Pandas TA 库中的函数是：

```python 

amat(close=None, fast=None, slow=None, lookback=None, mamode=None, offset=None, **kwargs)

```
## 3. AROON（Aroon & Aroon Oscillator）
Aroon 是一种趋势指标，旨在通过测量自价格达到最近的高点或低点以来的时间来确定是否存在趋势以及趋势的强度。Aroon Oscillator 则是 Aroon Up 和 Aroon Down 的差值，用于表示市场的总体趋势。

Aroon指标的计算方法如下：

1）计算 Aroon Up：这个指标考虑在过去的 length 天里，最高价出现在哪一天。如果最高价出现在今天，那么 Aroon Up 就是100。如果最高价出现在 length 天前，那么 Aroon Up 就是0。在两者之间的值将按比例计算。具体的计算公式为：

```python 

AROON_UP = ((length - 最高价出现的天数) / length) * 100

```

2）计算 Aroon Down：这个指标考虑在过去的 length 天里，最低价出现在哪一天。如果最低价出现在今天，那么 Aroon Down 就是100。如果最低价出现在 length 天前，那么 Aroon Down 就是0。在两者之间的值将按比例计算。具体的计算公式为：

```python 

AROON_DN = ((length - 最低价出现的天数) / length) * 100

```
3）计算 Aroon Oscillator：Aroon Oscillator 是 Aroon Up 和 Aroon Down 的差值，Aroon Oscillator 的值介于 -100 和 100 之间，用于度量市场的总体趋势。

```python 

AROON_OSC = AROON_UP - AROON_DN

```
Aroon 指标的用法如下：

1）确定趋势的存在与强度：当 Aroon Up 接近 100 时，这可能表示一个强烈的上升趋势，而当 Aroon Down 接近 100 时，这可能表示一个强烈的下降趋势。

另外，当 Aroon Oscillator 为正时，表示上升趋势可能较强，反之则表示下降趋势可能较强。

2）发现趋势的改变：当 Aroon Up 或 Aroon Down 跨过 50 线，这可能表示趋势的改变。例如，如果 Aroon Up 从下方穿过 50 线，这可能表示上升趋势的开始；相反，如果 Aroon Down 从上方穿过 50 线，这可能表示下降趋势的开始。

另外，当 Aroon Oscillator 从负转正，这可能表示上升趋势的开始；当 Aroon Oscillator 从正转负，这可能表示下降趋势的开始。

该指标在 Pandas TA 库中的函数是：

```python 

aroon(high, low, length=None, scalar=None, talib=None, offset=None, **kwargs)

```