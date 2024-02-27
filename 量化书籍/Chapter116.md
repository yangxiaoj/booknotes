# 量化实战入门116—波动性指标详解：Aberration / TR / ATR / NATR 

本文介绍以下几个技术指标：Aberration、TR、ATR、NATR。这几个指标都属于波动性（Volatility）指标，波动性指标主要用于衡量金融证券的价格变动幅度和速度，可以帮助投资者理解市场的稳定性和可能的风险。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. Aberration（离差）
Aberration (离差) 是一种类似 Keltner Channels 的波动率指标。它用于测量市场的波动性，帮助投资者判断市场的稳定性及可能的风险。

Aberration指标的计算方法如下：

1）计算平均真实波幅（ATR）。

2）计算HLC3值：HLC3值是高价、低价和收盘价的平均值，也被称为典型价格（TP）。

3）计算 ZG， ZG为TP的简单移动平均值：

```python 

ZG = SMA(TP, length)

```

4）计算SG和XG：

      SG = ZG + ATR
      XG = ZG - ATR

Aberration指标是由这四个值（ZG、SG、XG和ATR）共同构成，每个值都反映了市场的某种特性，共同用于分析市场的波动性。这四个值的含义和用法是：

1）ZG：这是基于典型价格（高、低、收盘价的平均值）进行计算的简单移动平均值。它代表了市场在一定周期内的平均价格水平，可以作为市场趋势的参考。如果当前价格远高于ZG，可能预示着市场处在过度买入的状态，并可能会出现价格回调；如果当前价格远低于ZG，可能预示着市场处在过度卖出的状态，并可能会出现价格反弹。

2）SG：这是ZG与平均真实波幅（ATR）的和。这个值代表了一个上界阈值，当价格超过这个阈值时，可能意味着价格处在过度买入的状态，可能会出现回落。

3）XG：这是ZG与平均真实波幅（ATR）的差。这个值代表了一个下界阈值，当价格跌破这个阈值时，可能意味着价格处在过度卖出的状态，可能会出现反弹。

4）ATR：这是平均真实波幅（ATR）。ATR是一种衡量市场波动性的指标，它的大小表明了市场价格变动的幅度。如果ATR较大，那么市场的波动性就较大，风险也相对较高；反之，如果ATR较小，那么市场的波动性就较小，风险也相对较低。

该指标在 Pandas TA 库中的函数是：

```python 

aberration(high, low, close, length=None, atr_length=None, offset=None, **kwargs)

```

## 2. True Range（真实范围，TR）

True Range (真实范围) 是一种用于测量价格波动性的方法。它不仅考虑了在一个交易周期内的最高价和最低价的差值，还包括了可能出现的跳空缺口。True Range 被广泛用于许多技术分析指标中，例如平均真实范围 (ATR)。

True Range 的计算方法如下：

1）计算三个值的绝对值：当前周期的最高价和最低价的差值 (high - low)，当前周期的最高价和前一周期的收盘价的差值 (high - prev_close)，以及当前周期的最低价和前一周期的收盘价的差值 (low - prev_close)。

2）True Range 等于以上三个值中的最大值。

True Range的使用方法有：

1）衡量波动性：True Range 的值可以直接用来衡量市场的波动性。通常，True Range 的值越大，表示市场的波动性越大；True Range 的值越小，表示市场的波动性越小。因此，它可以用来帮助投资者理解市场的稳定程度。

2）确定止损点：在某些交易策略中，True Range 的值可以用来确定止损点。例如，一种常见的方法是将止损点设置在入场价格减去一定倍数的 True Range。

3）构建其他指标：True Range 是许多其他技术分析指标的基础，例如平均真实范围 (ATR) 和动态平均趋势指标 (DMI)。通过将 True Range 与其他数据或指标相结合，可以创建更复杂的技术分析工具。

该指标在 Pandas TA 库中的函数是：

```python 

true_range(high, low, close, talib=None, drift=None, offset=None, **kwargs)

```

## 3. Average True Range（平均真实波幅，ATR）

Average True Range（平均真实波幅，简称 ATR）是一种用于衡量市场波动性的技术指标，特别是由于跳空或极限移动引起的波动性。

指标的计算方法

ATR 指标首先计算出每一个交易日的真实波幅（True Range，TR），然后对这些真实波幅值进行平均来计算 ATR：

```python 

TR = max[(high - low), abs(high - previous close), abs(low - previous close)]

ATR = EMA(TR, length)

```

以下是ATR 指标一些主要的应用方法：

1）波动性度量：ATR 的基本用途是衡量市场的波动性。较高的 ATR 值通常意味着价格在较大范围内波动，可能是由于市场新闻或事件引发的市场不确定性。相反，较低的 ATR 值可能表示市场平静，价格波动较小。

2）市场进入和退出：一些交易者使用 ATR 来帮助确定最佳的市场进入和退出点。例如，一种常见的策略是设置止损点在当前价格的一定 ATR 值之下。这样的设置可以在给市场足够的空间自然波动的同时，保护交易者免受市场极端波动的影响。

3）趋势确认：ATR 也可以用于确认市场趋势。如果价格在上升或下降，同时 ATR 也在增加，这可能意味着趋势正在加强。如果 ATR 在下降，这可能表示趋势正在减弱。

4）波动性突破：交易者有时会观察 ATR 的突破，作为市场方向变化的早期信号。例如，如果 ATR 突然从一段时间的低点上升，这可能意味着即将出现大的价格移动。

该指标在 Pandas TA 库中的函数是：

```python 

atr(high, low, close, length=None, mamode=None, talib=None, drift=None, offset=None, **kwargs)

```

## 4. Normalized Average True Range（归一化平均真实波幅，NATR）
Normalized Average True Range (NATR) 是一种衡量市场波动性的技术指标，它试图对平均真实范围（Average True Range，ATR）进行标准化，使其与价格水平无关。

NATR 的计算方法如下：

```python 

NATR = (100 / close) * ATR

```

NATR 的主要用途如下：

1）衡量市场波动性：NATR 是一种波动性指标，它可以帮助投资者衡量市场的波动性。当 NATR 较高时，表示市场波动性较大，可能存在更大的风险；反之，当 NATR 较低时，表示市场波动性较小，可能预示着市场的稳定。

2）识别市场趋势：NATR 也可以用来识别市场的趋势。当 NATR 上升时，可能表明市场在形成或维持一个趋势；反之，当 NATR 下降时，可能表明市场趋势正在减弱或可能发生反转。

3）设置止损点和止盈点：由于 NATR 可以衡量市场的波动性，因此它也可以用来设置止损点和止盈点。具体来说，投资者可以根据 NATR 的值来调整他们的止损点和止盈点，以适应市场的波动性。

该指标在 Pandas TA 库中的函数是：

```python 

natr(high, low, close, length=None, scalar=None, mamode=None, talib=None, drift=None, offset=None, **kwargs)

```
未完待续……