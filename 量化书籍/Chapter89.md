# 从零学量化89—均线类指标详解：SMA / EMA / WMA / ALMA / DEMA / FWMA / HiLo 

本文介绍以下几个技术指标：SMA、EMA、WMA、ALMA、DEMA、FWMA、HiLo。这几个指标都属于均线类型的指标。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。

## 1. SMA（Simple Moving Average，简单移动平均线）

简单移动平均线（SMA）的计算很简单，它通过计算一定时间内的平均收盘价来实现平滑价格数据、展现价格趋势的目标。

SMA的计算公式为：

```python 

SMA = SUM(close, length) / length

```

该指标在 Pandas TA 库中的函数是：

```python 

sma(close, length=None, talib=None, offset=None, **kwargs)

```

需要注意的是，这里的 SMA 跟国内多数行情软件（如通达信，同花顺等）中的 SMA 并不一致。这些国内行情软件中的 SMA 并不是简单移动平均，而是一种加权移动平均。

## 2. EMA（Exponential Moving Average，指数移动平均线）

EMA是一种更为敏感的移动平均线，相比于简单移动平均线（SMA），它对近期的价格变动赋予了更大的权重（通过参数alpha确定），因此能更敏感地反应价格变动。

EMA的计算公式为：

```python 

EMA_today = (Close_today * α) + (EMA_yesterday * (1 - α))

```

其中，Close_today 是今日的收盘价，EMA_yesterday 是昨日的EMA，α是平滑因子，通常计算为 2 / (N + 1)，其中N是你想要跟踪的天数。

该指标在 Pandas TA 库中的函数是：

```python 

ema(close, length=None, talib=None, offset=None, **kwargs)

```

## 3. WMA（Weighted Moving Average，加权移动平均线）

WMA是一种加权移动平均线，WMA的权重分配是线性的，即最近的价格数据被赋予最大的权重，然后依次递减。

WMA通常用于更敏感地跟踪价格趋势。由于WMA赋予了近期价格更大的权重，因此它能更快地反应价格变动，相比于简单移动平均线（SMA）更为敏感。

WMA的计算公式如下：

```Python 

WMA = (P_n * n + P_(n-1) * (n-1) + ... + P_1 * 1) / (n + (n-1) + ... + 1)
```

其中：
P_n 是最近一天的价格，P_(n-1) 是前一天的价格，以此类推，P_1 是 n 天前的价格。

n 是所选的周期，例如，如果你选择了5日WMA，那么 n 就是5。

这个公式的意思是，最近一天的价格被赋予了 n 的权重，前一天的价格被赋予了 n-1 的权重，以此类推，直到 n 天前的价格，它被赋予了1的权重。然后，这些权重化的价格被相加，最后除以权重的总和。

该指标在 Pandas TA 库中的函数是：

```python 
wma(close, length=None, asc=None, talib=None, offset=None, **kwargs)
```

## 4. ALMA（Arnaud Legoux Moving Average，AL移动平均线）
ALMA是一种使用正态分布曲线（高斯分布）的移动平均线，能够调整平滑度和敏感度，降低数据的滞后性，并在降噪的同时进行平滑处理。

ALMA的特点是：

1）减少滞后：ALMA的设计目标是减少滞后，这是许多其他移动平均线（如SMA、EMA等）的常见问题。

2）显示清晰的趋势：ALMA通过消除价格的噪音，并强调重要的价格点，提供了一个更清晰的市场趋势线。

3）灵活性：ALMA的计算过程包含几个可调整的参数，使投资者可以根据自己的交易策略和市场条件来定制ALMA，允许用户根据具体情况调整平滑度和敏感度。

ALMA的计算公式如下：

```python 

ALMA = Sum[(Wi * Pi) / Sum(Wi)]

```

其中：

Wi 是第i个价格的权重，计算公式为：Wi = e^[-(i - m)^2 / (2d^2)]，其中 e 是自然对数的底，i 是索引，m 和 d 是两个参数。
Pi 是第i个价格。

m 是偏移（offset），表示权重最大的价格离移动平均线结束的距离。通常，m 的值被设置为 (1 - offset) * (N - 1)，其中 offset 是一个介于0和1之间的数，N 是计算平均线的时期。

d 是标准偏差（sigma），通常被设置为 N / 6。

该指标在 Pandas TA 库中的函数是：

```python 

alma(close, length=None, sigma=None, distribution_offset=None, offset=None, **kwargs)

```

## 5. DEMA（Double Exponential Moving Average，双指数移动平均线）

DEMA 是一种试图得到比普通指数移动平均线（ EMA）更平滑且滞后更少的平均线。

DEMA的特点是：

1）减少滞后：DEMA通过对价格数据进行两次指数平滑，减小了移动平均线的滞后。这使得DEMA能更及时地反映价格的变动。

2）更准确的趋势信息：由于DEMA的计算方法，它能提供更准确的趋势信息，帮助投资者更好地识别和跟踪市场的趋势。

DEMA的计算公式如下：

```python

DEMA = 2 * EMA(n) - EMA(EMA(n))

```

其中：EMA是指数移动平均线。

该指标在 Pandas TA 库中的函数是：

```python 
dema(close, length=None, talib=None, offset=None, **kwargs)
```

## 6. FWMA（Fibonacci's Weighted Moving Average，斐波那契加权移动平均线）

FWMA是一种利用斐波那契数列作为权重的移动平均线。斐波那契数列是一个以0和1开始，之后每个数字都是它前两个数字之和的数列，例如：0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

FWMA的最大特点是，它使用斐波那契数列作为权重，这使得FWMA在计算过程中更加重视近期的价格。

FWMA的计算公式如下：

```python 
FWMA = (P_n * F_n + P_(n-1) * F_(n-1) + ... + P_1 * F_1) / (F_n + F_(n-1) + ... + F_1)
```

其中：

P_n 是最近一天的价格，P_(n-1) 是前一天的价格，以此类推，P_1 是 n 天前的价格。

F_n 是斐波那契数列中的第 n 个数，F_(n-1) 是第 (n-1) 个数，以此类推，F_1 是第1个数。

该指标在 Pandas TA 库中的函数是：

```python 

fwma(close, length=None, asc=None, offset=None, **kwargs)

```

## 7. HiLo（Gann High Low Activator，甘恩高低激活线）

HiLo是一个基于移动平均线的趋势指标，其计算方法是根据收盘价的位置选择高价移动平均线或低价移动平均线。如果收盘价高于前一天的高价移动平均线（处于上升趋势），则选择低价移动平均线作为HiLo值；如果收盘价低于前一天的低价移动平均线（处于下降趋势），则选择高价移动平均线作为HiLo值；否则，HiLo值等于前一天的HiLo值。这样的设计使得HiLo指标能够更快速地反应价格变动。

该指标在 Pandas TA 库中的函数是：

```python 

hilo(high, low, close, high_length=None, low_length=None, mamode=None, offset=None, **kwargs)

```
