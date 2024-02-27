# 量化实战入门107—动量类指标详解：STOCH / STOCHRSI / TD_SEQ 


本文介绍以下几个技术指标：STOCH、STOCHRSI、TD_SEQ。这几个指标都属于动量类型的指标。在投资中，动量指的是价格沿着一个方向前进的持续性。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见前文《量化宝藏工具箱：技术指标库 Pandas TA 教程》。
## 1. STOCH（Stochastic Oscillator，随机指标振荡器）

振荡器（Oscillator）是一种常见的动量指标，它可以通过衡量资产价格的动量或速度来预测未来的市场走势。称为“振荡器”的原因在于这类指标的数值通常围绕某个中心点或者区间“振荡”或波动。振荡器指标可以分为两大类：

1）界限振荡器（Bounded Oscillator）：这类振荡器的值通常被限制在一个固定的范围内，比如0到100。当读数接近上限时，市场可能处于过度买入状态，可能会出现价格回落；当读数接近下限时，市场可能处于过度卖出状态，可能会出现价格反弹。

2）非界限振荡器（Unbounded Oscillator）：这类振荡器没有固定的最大值和最小值，但它的数值仍然会围绕某个值上下波动，反映出价格动量的变化。

STOCH 是一种界限振荡器，由两条线组成，这两条线在0和100之间移动。快线（%K）显示当前收盘价相对于周期高/低范围的位置。慢线（%D）是%K线的简单移动平均。最常见的选择是14期的%K和3期的%D的简单移动平均。

STOCH的计算公式如下：

```python 

STOCH = 100 * (close - LL) / (HH - LL)
STOCHk = SMA(STOCH, smooth_k)
STOCHd = SMA(STOCHk, d)

```

其中：LL是过去k个周期的最低价，HH是过去k个周期的最高价，SMA是简单移动平均。

随机指标的主要用法包括：

1）超买超卖：当STOCH指标超过80时，市场可能过度买入，当指标低于20时，市场可能过度卖出。这些情况可能预示着即将来临的价格反转。

2）交叉信号：当%K线（快线）从下方穿过%D线（慢线）产生上穿时，这可能是一个买入信号；相反，如果%K线从上方穿过%D线产生下穿时，这可能是一个卖出信号。

3）背离：如果价格形成新的高点（或低点），而STOCH指标没有形成相应的新的高点（或低点），这可能是一个反转信号。例如，如果价格形成新的高点，但STOCH指标没有形成新的高点，这可能预示着上涨趋势正在减弱，反转可能即将到来。

该指标在 Pandas TA 库中的函数是：

```python 

stoch(high, low, close, k=None, d=None, smooth_k=None, mamode=None, offset=None, **kwargs)

```

## 2. STOCHRSI（Stochastic RSI，随机相对强弱指数）

STOCHRSI结合了随机振荡器（Stochastic Oscillator）和相对强弱指数（Relative Strength Index，RSI）的特性。它由两条线组成，这两条线在0和100之间移动。快线（RSI %K）显示当前的RSI相对于周期高/低范围的位置。慢线（RSI %D）是%K线的简单移动平均。最常见的选择是14期的%K和3期的%D的简单移动平均。

STOCHRSI的计算公式如下：

```python 

RSI = RSI(high, low, close, rsi_length)
STOCHRSI = 100 * (RSI - LL) / (HH - LL)
STOCHRSIk = SMA(STOCHRSI, k)
STOCHRSId = SMA(STOCHRSIk, d)

```

其中：LL是过去rsi_length个周期的RSI最低值，HH是过去rsi_length个周期的RSI最高值，SMA是简单移动平均。

STOCHRSI的主要用法包括：

1）超买超卖：当STOCHRSI超过80时，市场可能过度买入，可能存在卖出机会；当STOCHRSI低于20时，市场可能过度卖出，可能存在买入机会。

2）交叉信号：当STOCHRSI的K线（快线）从下方穿过D线（慢线）时，这可能被认为是买入信号；相反，如果K线从上方穿过D线，这可能被认为是卖出信号。

3）背离：如果价格形成新的高点（或低点），但STOCHRSI没有形成相应的新的高点（或低点），这可能是一个反转信号。例如，如果价格形成新的高点，但STOCHRSI没有形成新的高点，这可能预示着上涨趋势正在减弱，反转可能即将到来。

该指标在 Pandas TA 库中的函数是：

```python 

stochrsi(close, length=None, rsi_length=None, k=None, d=None, mamode=None, offset=None, **kwargs)

```
## 3. TD_SEQ (TD Sequential，TD序列)
TD Sequential（TD序列）是一种由Tom DeMark发明的技术分析指标，用于识别可能的价格反转点。它的主要理念源于市场的疲劳或饱和，即在完成一定的连续升降阶段后，市场可能会出现反转。

TD序列包含两个部分：TD Setup和TD Countdown。

TD Setup：是TD序列的第一部分，需要满足九个连续的K线，其中每一个都比四个单位之前的K线的关闭价格高（对于上涨趋势）或者低（对于下跌趋势）。一旦满足了这九个连续的K线，就完成了TD Setup。

TD Countdown：是TD序列的第二部分，它开始于TD Setup的完成。在一个完整的TD Countdown中，需要有13个特定的K线，其中每一个的关闭价格都比两个单位之前的K线的最低价（对于上涨趋势）或者最高价（对于下跌趋势）更高或者更低。

在TD序列中，通常认为完成TD Setup的点是潜在的反转点，而完成TD Countdown的点是更强烈的反转信号。

以下是如何使用TD序列：

1）识别潜在的反转点：如果市场完成了TD Setup，那么可能会在接下来的一段时间内出现价格反转。如果市场进一步完成了TD Countdown，那么这个反转信号就更加强烈。

2）确定入场和出场点：TD序列可以帮助投资者确定入场和出场点。当完成TD Setup时，可能是进入市场的好时机，因为价格可能会反转。同样，当完成TD Countdown时，可能是离开市场的好时机，因为价格可能会有更大的反转。

该指标在 Pandas TA 库中的函数是：

```python 

td_seq(close, asint=None, offset=None, **kwargs)

```

未完待续