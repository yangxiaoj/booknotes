# 量化实战入门114—趋势类指标详解：PSAR / Q_Stick / Trend_Signals / TTM_Trend 

本文介绍以下几个技术指标：PSAR、Q_Stick、Trend_Signals、TTM_Trend。这几个指标都属于趋势（ Trend）类型的指标，这类主要用于识别和跟踪市场的主要趋势。这些指标可以帮助投资者确定市场的方向（上升、下降或者横盘），从而帮助投资者决定何时进入或退出市场。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. PSAR（Parabolic Stop and Reverse，抛物线止损和反转）
Parabolic Stop and Reverse（PSAR）是由 J. Wells Wilder 开发的一种用于确定趋势方向及其可能的价格反转的指标。PSAR使用一种称为 "SAR" 或 "stop and reverse" 的追踪停止和反转方法来识别可能的入场和出场点。它也被称为 SAR。

PSAR 包括四个指标：PSAR_long，PSAR_short，PSAR_af 和 PSAR_reversal，它们的含义和使用方法如下：

1）PSAR_long：在上升趋势中的 PSAR 值，用于生成买入信号。当市场从下跌趋势反转为上升趋势时，PSAR_long 的值会发生变化，交易者可以考虑买入。

2）PSAR_short：在下跌趋势中的 PSAR 值，用于生成卖出信号。当市场从上升趋势反转为下跌趋势时，PSAR_short 的值会发生变化，交易者可以考虑卖出。

3）PSAR_af：加速因子的值。加速因子决定了 PSAR 对价格变动的敏感度。当市场价格变动幅度加大时，加速因子会增大，反之则会减小。交易者可以根据加速因子的变化来判断市场的动能。

4）PSAR_reversal：趋势反转的信号。当 PSAR_reversal 的值从 0 变为 1，表示市场趋势发生了反转。交易者可以根据趋势反转信号来确定买入或卖出的时机。

该指标在 Pandas TA 库中的函数是：

```python 

psar(high, low, close=None, af0=None, af=None, max_af=None, offset=None, **kwargs)

```

## 2. Q_Stick
Q Stick 是由 Tushar Chande 开发的一种技术分析指标，用于量化和识别蜡烛图中的趋势。

Q Stick 指标的计算涉及到两个步骤：计算涨跌幅，然后对其进行移动平均。计算公式如下：

```python 

qstick = MA(close - open, length)

```

其中：

- MA 是对应的移动平均函数，移动平均的类型可以是简单移动平均（SMA）、指数移动平均（EMA）、双指数移动平均（DEMA）、霍尔特移动平均（HMA）或重心移动平均（RMA）。

- length 是移动平均的周期长度。

以下是使用 Q Stick 指标的一些基本用法：

1）识别市场趋势：Q Stick 指标的值可以帮助交易者识别市场的整体趋势。当 Q Stick 的值为正时，表示在指定的期数内，上涨多于下跌，市场趋势可能为上升；反之，当 Q Stick 的值为负时，表示下跌多于上涨，市场趋势可能为下跌。

2）生成交易信号：Q Stick 指标的值也可以用于生成交易信号。例如，当 Q Stick 从负值变为正值时，这可能是一个买入信号，因为这可能表示市场趋势从下跌转为上升；反之，当 Q Stick 从正值变为负值时，这可能是一个卖出信号，因为这可能表示市场趋势从上升转为下跌。

3）结合其他技术分析工具：虽然 Q Stick 指标可以单独使用，但为了提高交易决策的准确性，通常建议将其与其他技术分析工具（如趋势线、支撑和阻力线、其他指标等）结合使用。

该指标在 Pandas TA 库中的函数是：

```python 

qstick(open_, close, length=None, offset=None, **kwargs)

```

## 3. Trend_Signals (趋势信号)
Trend Signals (趋势信号) 是一个技术分析函数，用于根据给定的趋势trend生成交易信号，包括趋势、交易、进场和出场信号。这些信号可以表示为布尔值或整数（0 或 1）。

趋势trend可以简单地定义为价格与移动平均线的关系（例如，'close' > 'moving average'），也可以是更复杂的表达式。

该指标在 Pandas TA 库中的函数是：

```python 

tsignals(trend, asbool=None, trend_reset=0, trade_offset=None, drift=None, offset=None, **kwargs)

```
返回结果的说明如下：

1）趋势信号（Trend）：这是函数的输入，可以是布尔值或整数（0 或 1）的序列，例如close > sma(close, 50)，表示收盘价是否高于过去50天的简单移动平均价。

2）交易信号（Trades）：交易信号是通过对趋势序列进行差分和位移来计算的。差分表示趋势的变化，位移代表在趋势改变后的下一期进行交易。

计算代码如下：

```python 

trades = trends.diff().shift(trade_offset)

```

3）进场信号（Entries）：进场信号是交易信号中的正数部分，计算代码如下：

```python 

entries = (trades > 0)

```

4）出场信号（Exits）：出场信号是交易信号中的负数部分的绝对值，计算代码如下：

```python 

exits = (trades < 0).abs()

```

tsignals函数的调用方法：

tsignals函数根据给定的趋势trend生成交易信号。趋势trend可以简单地被定义为“收盘价”大于“移动平均线”，或者更复杂的布尔表达式，其值为布尔值或整数（0或1）。

以下是如何调用tsignals函数的示例：

1）使用简单移动平均线（SMA）生成交易信号

```python 

ta.tsignals(close > ta.sma(close, 50), asbool=False)

```

在此示例中，我们使用“收盘价是否大于50天的简单移动平均线”这个trend来生成一个趋势信号。asbool=False表示我们希望结果保持为整数类型。

2）使用指数移动平均线（EMA）生成交易信号

```python 

ta.tsignals(ta.ema(close, 8) > ta.ema(close, 21), asbool=True)

```

在此示例中，我们使用“8天的EMA是否大于21天的EMA”这个trend来生成一个趋势信号。asbool=True表示我们希望结果被转换为布尔值。
## 4. TTM_Trend
TTM Trend 是一个趋势跟踪指标，基于价格与其过去一段时间的平均价格的关系来判断市场的趋势。它可以用来帮助投资者确定市场的方向，并据此做出买卖决定。

TTM Trend 指标的基本用法有：

1）确定市场趋势：TTM Trend 指标的值为1或-1。当指标值为1时，表示当前收盘价高于过去几个周期的平均价格，这通常被视为市场处于上升趋势。反之，当指标值为-1时，表示当前收盘价低于过去几个周期的平均价格，这通常被视为市场处于下降趋势。

2）发现买卖信号：TTM Trend 指标的值可以用来发现买卖信号。当指标值从-1变为1，这可能是一个买入信号，因为这可能表示市场趋势从下降转为上升。反之，当指标值从1变为-1，这可能是一个卖出信号，因为这可能表示市场趋势从上升转为下降。

3）过滤噪声信号：TTM Trend 指标还可以用来过滤噪声信号。因为它是基于过去几个周期的平均价格，所以对于一些小的价格波动，TTM Trend 可能不会反应过来，这可以帮助投资者避免因为市场的小波动而做出过早的买卖决定。

该指标在 Pandas TA 库中的函数是：

```python 

ttm_trend(high, low, close, length=None, offset=None, **kwargs)

```

未完待续……