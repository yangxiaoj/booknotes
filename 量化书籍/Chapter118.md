# 量化实战入门118—波动性指标详解： Keltner Channel/Mass Index/Price Distance/RVI 

本文介绍以下几个技术指标： Keltner Channel、Mass Index、 Price Distance、RVI。这几个指标都属于波动性（Volatility）指标，波动性指标主要用于衡量金融证券的价格变动幅度和速度，可以帮助投资者理解市场的稳定性和可能的风险。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. Keltner Channel（凯尔特纳通道，kc）
Keltner Channels（KC）是一种流行的波动率指标，类似于Bollinger Bands 和 Donchian Channels。该指标由一个中线和两个带状线（上线和下线）组成，上下带状线是根据中线和市场波动率来确定的。

计算 Keltner Channels 的过程如下：

1）确定范围（RANGE）：范围可以是真实范围（TR，即最高价、最低价和前一收盘价的最大差距）或者是最高价和最低价的差距。

2）计算基线（BASIS）：基线是收盘价的移动平均。

3）计算带状线（BAND）：带状线是范围的移动平均。

4）计算上线和下线：上线是基线加上 scalar 倍的带状线，下线是基线减去 scalar 倍的带状线。

Keltner Channels的主要应用方式有：

1）判断趋势：中线（BASIS）可以被视为资产的平均价格或趋势线。如果资产价格上穿中线，那么可能是一个上涨趋势的信号；反之，如果资产价格下穿中线，那么可能是一个下跌趋势的信号。

2）判断波动性：通道的宽度（即上线和下线之间的距离）反映了市场的波动性。通道越宽，市场的波动性越大；通道越窄，市场的波动性越小。因此，如果通道开始扩大，那可能意味着市场波动性正在增加，投资者应该更加谨慎；反之，如果通道开始收窄，那可能意味着市场波动性正在减小，投资者可能可以考虑更积极的投资策略。

3）判断超买或超卖状态：如果资产价格接近或触及上线，那可能意味着该资产被超买，即价格可能过高，有回落的风险；反之，如果资产价格接近或触及下线，那可能意味着该资产被超卖，即价格可能过低，有反弹的可能。

4）生成交易信号：当资产价格从通道的一侧穿越到另一侧时，可能是一个交易信号。具体来说，如果资产价格从下线穿越到上线，那可能是一个买入信号；反之，如果资产价格从上线穿越到下线，那可能是一个卖出信号。

该指标在 Pandas TA 库中的函数是：

```python 

kc(high, low, close, length=None, scalar=None, mamode=None, offset=None, **kwargs)

```

## 2. Mass Index（massi）
Mass Index（MASSI）是一种没有方向的波动率指标，它利用最高价和最低价的区间（High-Low Range）来识别基于区间扩展的趋势反转。

MASSI 的计算过程如下：

1）计算高低差（hl）：hl 等于最高价与最低价的差值。

2）计算第一次指数移动平均（EMA）：hl_ema1 等于 hl 的 fast 期指数移动平均。

3）计算第二次指数移动平均（EMA）：hl_ema2 等于 hl_ema1 的 fast 期指数移动平均。

4）计算 hl 的比率（hl_ratio）：hl_ratio 等于 hl_ema1 除以 hl_ema2。

5）计算 MASSI：MASSI 等于 hl_ratio 的 slow 期求和。

Mass Index主要的应用方式有：

1）识别趋势反转：MASSI 的主要用途是识别可能的趋势反转。当 MASSI 超过一个特定的阈值（比如 27）时，这可能意味着市场正在经历一个趋势反转。具体来说，如果在一个上涨趋势中，MASSI 超过了 阈值，那么可能预示着将要发生一个下跌趋势；反之，如果在一个下跌趋势中，MASSI 超过了 阈值，那么可能预示着将要发生一个上涨趋势。

2）识别市场的波动性：MASSI 反映了市场的波动性。当 MASSI 较高时，表示市场波动性较大，这可能预示着市场的不稳定和风险；反之，当 MASSI 较低时，表示市场波动性较小，这可能预示着市场的稳定和安全。

该指标在 Pandas TA 库中的函数是：

```python 

massi(high, low, fast=None, slow=None, offset=None, **kwargs)

```

## 3. Price Distance（价格距离，pdist）
Price Distance (PDIST) 是一种测量价格运动"距离"的技术指标，它试图捕捉价格的波动情况和趋势的强度。

PDIST 的计算公式如下：

```python 

PDIST = 2*(high - low) - ABS(close - open) + ABS(open - close[drift])

```

其中，"high" 和 "low" 分别代表一定时期内的最高价和最低价，"open" 和 "close" 分别代表开盘价和收盘价，"drift" 是差异期。

以下是 PDIST 的一些主要用途：

1）衡量价格波动性：PDIST 可以帮助投资者衡量价格的波动性。PDIST 的值越大，表示价格波动性越大，可能存在更大的风险；反之，PDIST 的值越小，表示价格波动性较小，可能预示着市场的稳定。

2）识别市场趋势的强度：PDIST 也可以用来识别市场趋势的强度。PDIST 的值越大，可能表明市场趋势的强度越大，这可能预示市场可能会继续按照当前的趋势发展；反之，PDIST 的值越小，可能表明市场趋势的强度减弱，这可能预示市场可能会发生趋势反转。

3）提供交易信号：投资者也可以利用 PDIST 来提供交易信号。例如，当 PDIST 的值从较高的水平下降时，可能预示市场趋势可能会发生反转，投资者可以考虑卖出；反之，当 PDIST 的值从较低的水平上升时，可能预示市场趋势可能会继续，投资者可以考虑买入。

该指标在 Pandas TA 库中的函数是：

```python
 
pdist(open_, high, low, close, drift=None, offset=None, **kwargs)

```

## 4. Relative Volatility Index（相对波动率指数，RVI）
Relative Volatility Index（RVI）是一种测量资产价格变动的相对波动性的技术指标。与基于价格方向的 RSI 不同，RVI 是基于价格方向累计标准偏差。

RVI 的计算过程如下：

1）根据价格序列的变化来计算 UP 和 DOWN。如果价格序列的差值大于 0，则 UP 等于该时期的标准偏差，DOWN 为 0；如果价格序列的差值小于或等于 0，则 DOWN 等于该时期的标准偏差，UP 为 0。

2）计算 UP 和 DOWN 的指数移动平均值（EMA），分别得到 UPSUM 和 DOWNSUM。

3）计算RVI：

```python 

RVI = scalar * (UPSUM / (UPSUM + DOWNSUM))

```

以下是RVI的一些主要用法：

1）确定超买或超卖区域：RVI指标的取值范围通常在0至100之间。一般来说，当RVI值超过70时，资产可能被视为超买，可能存在价格下跌的风险；当RVI值低于30时，资产可能被视为超卖，可能存在价格上涨的机会。

2）发现背离信号：当资产价格与RVI指标出现背离时，可能提示市场趋势即将反转。例如，如果资产价格创新高，但RVI指标未能创新高，这可能是一种看跌的背离信号；反之，如果资产价格创新低，但RVI指标未能创新低，这可能是一种看涨的背离信号。

3）确定市场波动性：RVI指标反映了市场的波动程度。RVI值越高，表明市场波动性越大，可能存在更大的风险；反之，RVI值越低，表明市场波动性较小，可能预示着市场的稳定。

该指标在 Pandas TA 库中的函数是：

```python 

rvi(close, high=None, low=None, length=None, scalar=None, refined=None, thirds=None, mamode=None, drift=None, offset=None, **kwargs)

```

未完待续……