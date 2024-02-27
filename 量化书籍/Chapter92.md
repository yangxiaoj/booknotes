# 从零学量化92—均线类指标详解：TEMA / TRIMA / VIDYA / VWMA / ZLMA 

本文介绍以下几个技术指标：TEMA、TRIMA、VIDYA、VWMA、ZLMA。这几个指标都属于均线类型的指标。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。

## 1. TEMA（Triple Exponential Moving Average，三重指数移动平均线）

三重指数移动平均线 TEMA 是普通的指数移动平均线 EMA 的变体，是一种比 EMA 更低延迟的移动平均线。它通过三次指数平滑以减少滞后并更准确地跟踪价格趋势。

TEMA的特点有：

1）减少滞后：TEMA是为了尽量减少指标滞后而设计的。通过对价格进行三次指数平滑，TEMA可以更快地反应价格的变动。

2）精确跟踪趋势：由于其计算方式，TEMA可以更准确地跟踪价格趋势，特别是在价格剧烈波动的市场环境中。

3）过滤噪音：TEMA通过平滑计算可以有效地过滤市场的噪音，使得投资者可以更清晰地看到市场的真实趋势。

TEMA的计算方法如下：

```python 

ema1 = EMA(close, length)
ema2 = EMA(ema1, length)
ema3 = EMA(ema2, length)
TEMA = 3 * (ema1 - ema2) + ema3

```

该指标在 Pandas TA 库中的函数是：

```python 

tema(close, length=None, talib=None, offset=None, **kwargs)

```
## 2. TRIMA（Triangular Moving Average，三角形移动平均线）

三角形移动平均线 TRIMA 是一种特殊类型的移动平均线，它通过对简单移动平均线（SMA）进行再平均来实现。由于其权重设置，TRIMA在中心数据点上赋予更多的权重，因此，其形状类似于一个三角形。

TRIMA的特点：

1）平滑性：TRIMA通过两次平均计算，可以更有效地平滑价格数据，从而过滤掉短期的价格噪音和波动。

2）中心权重：不同于其他类型的移动平均线，TRIMA在计算过程中对中心点的数据赋予了更多的权重。这种权重分配方式使得TRIMA更能反映价格的中期趋势。

3）滞后性：虽然TRIMA提供了更平滑的价格趋势，但是由于其计算方法，它有更大的滞后性。这意味着TRIMA可能不适合用于寻找短期的交易机会。由于TRIMA的滞后性，它通常与其他更敏感的技术指标（如MACD、RSI等）结合使用，以确定最佳的交易点。

TRIMA的计算方法如下：
```python

# 1. 计算半长度：
half_length = round(0.5 * (length + 1))
# 2. 计算第一次简单移动平均：
SMA1 = SMA(close, half_length)
# 3. 对SMA1进行SMA运算得到TRIMA：
TRIMA = SMA(SMA1, half_length)
```

该指标在 Pandas TA 库中的函数是：

```python 
trima(close, length=None, talib=None, offset=None, **kwargs)
```

## 3. VIDYA（Variable Index Dynamic Average，可变指数动态平均线）

可变指数动态平均线 VIDYA 是一种自适应的移动平均线。VIDYA的平滑系数可以根据市场波动率动态调整，因此，它能够在不同市场环境中灵活应用。

VIDYA的特点：

1）自适应性：VIDYA的关键特点是它能够自动调整其敏感性以适应当前市场的波动性。当市场波动性增加时，VIDYA会变得更敏感，以便更快地反应价格变动。当市场波动性减小时，VIDYA会变得更稳定，以减少误报信号。

2）灵活性：VIDYA的自适应性使其在各种不同的市场环境中都能有效地工作。无论市场是趋势市场还是震荡市场，VIDYA都能提供有用的信息。

该指标在 Pandas TA 库中的函数是：

```python 

vidya(close, length=None, drift=None, offset=None, **kwargs)
```


## 4. VWMA（Volume Weighted Moving Average，成交量加权移动平均线）

VWMA是一种考虑了交易量的移动平均线，比传统的移动平均线（如简单移动平均线或指数移动平均线）提供了更多信息，因为它更加重视交易量大的时段。

VWMA最主要特点是它考虑了交易量，将每个价格变动的权重与相应的成交量关联起来。这意味着在成交量较大的时候，价格变动会对VWMA产生更大的影响，VWMA会更接近那些交易量大的价格。由于VWMA考虑了成交量，因此它可以更好地反映市场的交易活动。

VWMA的计算方法如下：

```python 

pv = close * volume
VWMA = SMA(pv, length) / SMA(volume, length)

```

该指标在 Pandas TA 库中的函数是：

```python 

vwma(close, volume, length=None, offset=None, **kwargs)

```

## 5. ZLMA（Zero Lag Moving Average，零延迟移动平均线）

零延迟移动平均线 ZLMA 是一种尝试减少移动平均线延迟的技术指标。传统的移动平均线，如简单移动平均线（SMA）和指数移动平均线（EMA），都会有一定的延迟，因为它们基于过去的价格数据。ZLMA试图通过预先调整数据来消除这种延迟。

ZLMA的主要目标是减少移动平均线的延迟，它通过预先调整数据来达到减少延迟的目标。具体来说，它先预估了数据，然后使用这些预估的数据来计算移动平均线。

ZLMA的计算公式如下：

```python

ZLMA = MA(2 * Price - Price[length], length)

```

在这个公式中，“Price”代表当前的价格，“Price[length]”代表length时间段前的价格，“length”是移动平均线的长度，“MA”是移动平均线的计算函数。

上述公式中 2 * Price - Price[length] 是一个预处理步骤，尝试通过当前价格数据和过去价格数据的差值，来预测未来价格的走势。然后，这个预测的价格数据被用来计算移动平均线。这样，ZLMA能够更快地反应价格的变动，从而减少了延迟。

投资者在使用ZLMA时应注意，因为它是基于预先调整的数据，所以可能会有一些不准确。

该指标在 Pandas TA 库中的函数是：

```python 

zlma(close, length=None, mamode=None, offset=None, **kwargs)

```