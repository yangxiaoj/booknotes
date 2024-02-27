# 量化实战入门113—趋势类指标详解：Decreasing /DPO/Increasing/Long_Run/Short_Run 

本文介绍以下几个技术指标：Decreasing、DPO、Increasing、Long_Run、Short_Run。这几个指标都属于趋势（ Trend）类型的指标，这类主要用于识别和跟踪市场的主要趋势。这些指标可以帮助投资者确定市场的方向（上升、下降或者横盘），从而帮助投资者决定何时进入或退出市场。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. Decreasing
Decreasing是一个技术分析函数，用于判断一系列数据在一段时间内是否呈现下降趋势。

根据 strict 参数的值，Decreasing存在两种不同的计算方式：

1）如果 strict 为 True，则检查序列是否在整个周期内持续下降：

```python 

decreasing = all(i > j for i, j in zip(close[-length:], close[1:]))

```

2）否则，只检查序列在周期内的总体变化是否为下降：

```python 

decreasing = close.diff(length) < 0

```

Decreasing指标是一个用于判断股票价格或其他数据序列是否在特定时间段内下降的工具。以下是Decreasing指标的一些常见用法：

1）趋势分析：decreasing 指标可以用于判断股票价格是否在一定时间段内下降。例如，如果你想知道某股票在过去的 5 天内是否价格持续下降，你可以设置 length 参数为 5，并将 strict 参数设置为 True。如果返回值为 True，则说明该股票在过去的 5 天内价格持续下降。

2）交易策略：当 decreasing 指标显示出一定的下降趋势时，投资者可能会选择卖出该股票，以防止进一步的损失。相反，如果投资者认为该股票的下跌是短暂的，并且有反弹的可能，他们可能会选择在价格较低时买入。

3）风险管理：decreasing 指标也可以用于风险管理。例如，投资者可以将 decreasing 指标用作一个信号，当它显示出价格下降趋势时，投资者可以减少对该股票的投资，以降低潜在的风险。

4）趋势反转：对于一些逆向投资者，他们可能会在 decreasing 指标显示出强烈下降趋势时，选择买入，寻求在价格反弹时获益。

该指标在 Pandas TA 库中的函数是：

```python 

decreasing(close, length=None, strict=None, asint=None, percent=None, drift=None, offset=None, **kwargs)

```

## 2. DPO（Detrend Price Oscillator，去趋势价格振荡器）
Detrend Price Oscillator (DPO) 是一个设计用来从价格中去除趋势，使得更容易识别周期的指标。DPO 指标的目的是去除价格的趋势影响，使得交易者可以更明显地看到价格的周期性波动。

DPO的计算公式为：

```python 

DPO = close.shift(t) - SMA(close, length)

```

这是通过将位移后的收盘价减去简单移动平均来实现的。

以下是一些DPO指标的常见用法：

1）周期性识别：DPO的主要用途是分析和识别周期性模式。通过观察DPO的峰值和谷值，交易者可以确定价格的周期长度，然后预测未来的价格波动。

2）超买超卖判断：DPO的另一个用途是帮助判断市场的超买或超卖状态。当DPO达到极高水平时，可能表示市场已经超买，价格可能会下跌。相反，如果DPO达到极低水平，可能表示市场已经超卖，价格可能会上涨。

3）交叉信号：一些交易者使用DPO和它的移动平均线产生交易信号。例如，当DPO从下方穿过它的移动平均线时，可能是一个买入信号。当DPO从上方穿过它的移动平均线时，可能是一个卖出信号。

4）背离信号：如果价格新高而DPO未能形成新高（即产生负背离），可能预示着下跌。反之，如果价格新低而DPO未能形成新低（即产生正背离），可能预示着上涨。

该指标在 Pandas TA 库中的函数是：

```python 

dpo(close, length=None, centered=True, offset=None, **kwargs)

```

## 3. Increasing
Increasing是一个用于判断给定序列是否在一定周期内上升的函数。
以下是一些 increasing 指标的常见用法：

1）趋势识别：increasing 指标可以帮助交易者识别价格趋势。如果某个资产的价格在指定的周期内上升，这可能表示该资产正在处于上升趋势中，交易者可能会考虑买入。反之，如果价格在指定的周期内没有上升，这可能表示该资产正在处于下降趋势或者横盘整理中，交易者可能会考虑卖出或者观望。

2）买卖信号：increasing 指标也可以用于生成买卖信号。例如，如果价格在较长的周期内上升，但在较短的周期内没有上升，这可能表示价格上涨的动力正在减弱，交易者可能会考虑卖出。反之，如果价格在较长的周期内没有上升，但在较短的周期内开始上升，这可能表示价格下跌的动力正在减弱，交易者可能会考虑买入。

3）确认其他技术指标：increasing 指标可以与其他技术指标结合使用，以确认或否定其他指标的信号。例如，如果某个振荡器指标给出了买入信号，但 increasing 指标显示价格在最近的周期内没有上升，那么交易者可能会对这个买入信号持怀疑态度。

该指标在 Pandas TA 库中的函数是：

```python 

increasing(close, length=None, strict=None, asint=None, percent=None, drift=None, offset=None, **kwargs)

```

## 4. Long_Run

Long Run 函数是一个技术分析指标，主要用于捕捉市场的长期趋势。

Long Run 的主要计算逻辑如下：

1）pb 是一个布尔型的 Series，如果在指定周期内快速线上升并且慢速线下降，那么 pb 对应的值为 True，否则为 False。这可能表示市场可能处于底部或潜在的底部。

2）bi 也是一个布尔型的 Series，如果在指定周期内快速线和慢速线都在上升，那么 bi 对应的值为 True，否则为 False。这表示市场的快速和慢速线都在上升。

3）long_run 是 pb 和 bi 的逻辑或运算结果，如果 pb 或 bi 对应的值为 True，那么 long_run 对应的值也为 True，否则为 False。

以下是 long_run 指标的一些常见用法：

1）潜在底部或底部识别：当 long_run 的值为 True，并且这是由快速线在指定周期内上升，同时慢速线在同一周期内下降引起的，那么我们可以将这视为市场可能处于底部或潜在的底部。在这种情况下，交易者可能会考虑增仓或买入，因为这可能预示着未来市场的反弹或上升。

2）上升趋势识别：当 long_run 的值为 True，并且这是由快速线和慢速线在指定周期内都上升引起的，那么我们可以将这视为市场处于上升趋势。在这种情况下，交易者可能会考虑继续持有或增加购买，因为这可能预示着未来市场可能会继续保持上升趋势。

该指标在 Pandas TA 库中的函数是：

```python 

long_run(fast, slow, length=None, offset=None, **kwargs)

```

## 5. Short_Run
short_run 函数是用于捕捉市场的短期动态，尤其是市场可能的顶部或者快速和慢速线都在下降的情况。这个指标可以帮助交易者在短期内做出买入或卖出的决策。

Short Run 的主要计算逻辑如下：

1）pt 是一个布尔型的 Series，如果在指定周期内快速线下降并且慢速线上升，那么 pt 对应的值为 True，否则为 False。这可能表示市场可能处于顶部或潜在的顶部。

2）bd 也是一个布尔型的 Series，如果在指定周期内快速线和慢速线都在下降，那么 bd 对应的值为 True，否则为 False。这表示市场的快速和慢速线都在下降。

3）short_run 是 pt 和 bd 的逻辑或运算结果，如果 pt 或 bd 对应的值为 True，那么 short_run 对应的值也为 True，否则为 False。
Short Run 的主要用法如下：

1）市场顶部识别：当 short_run 的值为 True，并且这是由快速线在指定周期内下降，同时慢速线在同一周期内上升引起的，那么我们可以将这视为市场可能处于顶部或潜在的顶部。在这种情况下，交易者可能会考虑减仓或卖出，因为这可能预示着未来市场的回落或下跌。

2）下降趋势识别：当 short_run 的值为 True，并且这是由快速线和慢速线在指定周期内都下降引起的，那么我们可以将这视为市场处于下降趋势。在这种情况下，交易者可能会考虑卖出或保持观望，因为这可能预示着未来市场可能会继续保持下降趋势。

该指标在 Pandas TA 库中的函数是：

```python 

short_run(fast, slow, length=None, offset=None, **kwargs)

```

未完待续……