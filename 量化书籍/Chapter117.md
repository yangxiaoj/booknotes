# 量化实战入门117—波动性指标详解：布林带 / 唐奇安通道 / Holt-Winter Channel 

本文介绍以下几个技术指标：Acceleration Bands（加速带）、Elder's Thermometer、 Ulcer Index（溃疡指数）。这几个指标都属于波动性（Volatility）指标，波动性指标主要用于衡量金融证券的价格变动幅度和速度，可以帮助投资者理解市场的稳定性和可能的风险。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. Acceleration Bands（加速带，accbands）
Acceleration Bands（加速带指标）用于测量价格趋势的加速度。

Acceleration Bands 指标的核心思想是，当价格以加速的趋势向上或向下运动时，价格会趋向于触及其对应的上线或下线。

Acceleration Bands 的计算方法：

Acceleration Bands 指标包含上线UPPER、中线MID和下线LOWER三条线，它们分别由以下公式计算：


```python 

HL_RATIO = c * (high - low) / (high + low)
LOW = low * (1 - HL_RATIO)
HIGH = high * (1 + HL_RATIO)
# 计算下线LOWER
LOWER = MA(LOW, length)
# 计算中线MID
MID = MA(close, length)
# 计算上线UPPER
UPPER = MA(HIGH, length)
```


以下是Acceleration Bands主要的用法：

1）趋势判断：当股价在上线（UPPER）和下线（LOWER）之间波动时，一般被认为市场处于无明显趋势的盘整阶段。当股价突破上线或下线，可能表示市场开始形成新的上升或下降趋势。

2）买卖信号：在某些策略中，股价突破上线（UPPER）可能被视作买入信号，因为这可能表示价格开始加速上升。相反，股价跌破下线（LOWER）可能被视作卖出信号，因为这可能表示价格开始加速下跌。

3）过度买卖判断：如果股价长时间在上线（UPPER）之上或下线（LOWER）之下运行，可能表示市场已经过度买入或过度卖出，市场可能会发生反转，这就需要投资者密切关注后续的价格走势。

该指标在 Pandas TA 库中的函数是：

```python 

accbands(high, low, close, length=None, c=None, drift=None, mamode=None, offset=None, **kwargs)

```

## 2. Elder's Thermometer（thermo）

Elder's Thermometer 是一种测量价格波动性的技术指标，由四个数据组成：thermo、thermo_ma、thermo_long、thermo_short

Elder's Thermometer 的计算过程如下：

1）计算 thermoL，即前一期的最低价与当前最低价的差值的绝对值。

2）计算 thermoH，即当前最高价与前一期最高价的差值的绝对值。

3）thermo 为 thermoH 和 thermoL 中的较大者。

4）对 thermo 序列进行指数移动平均（EMA），得到 thermo_ma。

5）thermo_long 为 thermo 小于 thermo_ma 乘以长期因子时的情况，返回布尔值序列。

6）thermo_short 为 thermo 大于 thermo_ma 乘以短期因子时的情况，返回布尔值序列。

Elder's Thermometer 指标的含义是：

1）thermo：这是 Elder's Thermometer 的原始计算值，它反映的是价格波动性的原始度量。

2）thermo_ma：这是对 thermo 序列进行指数移动平均（EMA）后的结果，它可以被视为价格波动性的平滑度量。

3）thermo_long：这是一个二值序列，当 thermo 小于 thermo_ma 乘以买入因子时，对应的值为 1，否则为 0。这可以被视为一个买入信号，当它为 1 时，表示价格波动性较低，可能是买入的好时机。

4）thermo_short：这也是一个二值序列，当 thermo 大于 thermo_ma 乘以卖出因子时，对应的值为 1，否则为 0。这可以被视为一个卖出信号，当它为 1 时，表示价格波动性较高，可能是卖出的好时机。

Elder's Thermometer 的用法有：

1）确定市场波动性：thermo 的值反映了市场的波动程度。更高的 thermo 值通常表示更大的市场波动性，而更低的 thermo 值表示较低的市场波动性。

2）产生交易信号：当 thermo_long 会为真，这可能是一个买入信号，因为这表示当前的市场波动性较低。相反，当 thermo_short 会为真，这可能是一个卖出信号，因为这表示当前的市场波动性较高。

3）结合其他指标使用：thermo 指标通常和其他技术分析指标如趋势线、移动平均线、相对强弱指数 (RSI) 等一起使用，以提高交易的准确性。例如，当 thermo_long 为真，且价格突破了一个重要的趋势线或移动平均线时，这可能是一个强烈的买入信号。

该指标在 Pandas TA 库中的函数是：

```python 

thermo(high, low, length=None, long=None, short=None, mamode=None, drift=None, offset=None, **kwargs)

```

## 3. Ulcer Index（溃疡指数，ui）
Ulcer Index（UI，或称溃疡指数）是一种衡量价格下行波动性或者说市场风险的指标。这是一种重点强调大幅度回撤的衡量方法，因为它使用的计算方式使得大的回撤对最终结果的影响更大。

Ulcer Index 的计算方法如下：

1）计算过去 length 期的最高收盘价（Highest Close，简称 HC）。

2）计算每个交易日的收盘价 (close) 与其过去 length 期的最高收盘价 (HCN) 的差值的比例，然后乘以 scalar。这个值被称为 DOWNSIDE。

3）如果 everget 参数为 True，则计算 DOWNSIDE 的平方的 length 期简单移动平均（SMA），然后除以 length，最后取平方根。这个值就是 Ulcer Index。

4）如果 everget 参数为 False，则计算 DOWNSIDE 的平方的 length 期求和，然后除以 length，最后取平方根。这个值就是 Ulcer Index。

以下是 Ulcer Index 的一些主要用途：

1）衡量风险：Ulcer Index 的主要用途是作为风险度量。较高的 Ulcer Index 值表示投资组合或者资产的下行风险较大，也就是说，投资组合或者资产的价格下跌的幅度和频率较大。相反，较低的 Ulcer Index 值则表示下行风险较小。

2）比较投资组合：Ulcer Index 可以用来比较不同投资组合的风险性。例如，如果两个投资组合的收益率相同，那么 Ulcer Index 较低的投资组合风险就较小。

3）调整投资策略：投资者可以根据 Ulcer Index 的值来调整他们的投资策略。例如，如果 Ulcer Index 的值较高，投资者可能会选择减小投资仓位或者增加对冲，以降低风险。

4.）止损点的确定：Ulcer Index 可以用来帮助确定止损点。如果 Ulcer Index 的值超过了投资者的风险承受能力，那么投资者可能需要考虑止损。

该指标在 Pandas TA 库中的函数是：

```python 

ui(close, length=None, scalar=None, offset=None, **kwargs)

```