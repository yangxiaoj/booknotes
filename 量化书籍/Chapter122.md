# 量化实战入门122—成交量指标详解：EFI / EOM / KVO 

本文介绍以下几个技术指标：EFI、EOM、KVO。这几个指标都是跟成交量相关的指标，成交量是衡量市场活跃程度和价格变动有效性的关键因素，它们提供了市场参与者情绪和潜在市场动向的重要线索。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见前文《量化宝藏工具箱：技术指标库 Pandas TA 教程》。
## 1. Elder's Force Index（EFI）
Elder's Force Index (EFI) 是一种结合了价格变化和交易量的动量指标，可以帮助交易者评估价格运动背后的力度。

指标的计算方法：

```python 

# 计算价格变动 pv_diff，它等于价格的差分（默认差分周期为 1）和交易量的乘积
pv_diff = close.diff(drift) * volume
# 对 pv_diff 进行平均
EFI = MA(pv_diff, length)

```

以下是一些使用 EFI 指标的方法：

1）趋势确认：EFI 可以被用来确认现有的价格趋势。例如，如果股票价格正在上升，并且 EFI 也在上升，那么这可能表示买压正在增强，上升趋势可能会继续。反之，如果股票价格正在下跌，并且 EFI 在下降，那么这可能表示卖压正在增强，下跌趋势可能会继续。

2）寻找背离：EFI 可以用来寻找价格和买卖压力之间的背离。例如，如果股票价格创出新高，但 EFI 没有创出新高，那么这可能是一个弱势背离信号，表明上升趋势可能会逆转。反之，如果股票价格创出新低，但 EFI 没有创出新低，这可能是一个强势背离信号，表明下跌趋势可能会逆转。

3）过度买卖信号：一些交易者可能会使用 EFI 的极值作为过度买入或过度卖出的信号。例如，如果 EFI 达到一个极高的正值，那么市场可能是过度买入的，价格可能会出现回调。反之，如果 EFI 达到一个极低的负值，那么市场可能是过度卖出的，价格可能会反弹。

该指标在 Pandas TA 库中的函数是：

```python 

efi(close, volume, length=None, mamode=None, drift=None, offset=None, **kwargs)

```

## 2. Ease of Movement（EOM）
Ease of Movement (EOM) 是一个基于交易量的振荡器，旨在测量价格和交易量的关系如何在零线上下波动。EOM 指标可帮助交易者评估价格变动的"容易程度"，考虑了价格变动和交易量的影响。它可用于识别可能的买卖机会。

指标的计算方法：

```python 

hl_range = high - low
distance = 0.5 * (high - high.shift(drift) + low - low.shift(drift))
box_ratio = (volume / divisor) / hl_range
eom = distance / box_ratio
EOM = SMA(eom, length)

```

以下是一些使用 EOM 指标的常见方法：

1）交易信号：当 EOM 线从下方穿过零线并向上移动时，这可能是一个买入信号，因为这可能表示价格上涨的"容易度"正在增加。相反，当 EOM 线从上方穿过零线并向下移动时，这可能是一个卖出信号，因为这可能表示价格下跌的"容易度"正在增加。

2）趋势分析：交易者可以通过观察 EOM 线的走势来评估价格趋势的强度。如果 EOM 线正在上升，那么这可能表示上升趋势正在加强。如果 EOM 线正在下降，那么这可能表示下降趋势正在加强。

3）背离分析：当价格和 EOM 指标出现背离时，可能预示着趋势反转。例如，如果价格创新高，但 EOM 未能创新高，这可能是上涨趋势即将结束的信号。反之，如果价格创新低，但 EOM 未能创新低，这可能是下跌趋势即将结束的信号。

该指标在 Pandas TA 库中的函数是：

```python 

eom(high, low, close, volume, length=None, divisor=None, drift=None, offset=None, **kwargs)

```

## 3. Klinger Volume Oscillator（克林格成交量振荡器，KVO）
Klinger Volume Oscillator (KVO) 指标通过比较交易量和价格变化，来预测市场价格反转。

指标的计算方法：

```python 

#1. 计算符号体积（SV），等于交易量乘以符号系列（HLC3 的符号，偏移为1）
SV = volume * signed_series(HLC3, 1)
#2. 计算 KVO，等于 SV 的快速指数移动平均（EMA）减去 SV 的慢速指数移动平均
KVO = EMA(SV, fast) - EMA(SV, slow)
#3. 计算信号线，等于 KVO 的指数移动平均
Signal = EMA(KVO, signal)

```

以下是一些使用 KVO 指标的常见方法：

1）交易信号：当 KVO 线从下方穿过信号线并向上移动时，这可能是一个买入信号，表示买方开始主导市场。相反，当 KVO 线从上方穿过信号线并向下移动时，这可能是一个卖出信号，表示卖方开始主导市场。

2）趋势分析：交易者可以通过观察 KVO 线相对于信号线的位置和走势来评估价格趋势的强度。如果 KVO 线在信号线之上并且正在上升，那么这可能表示上升趋势正在加强。如果 KVO 线在信号线之下并且正在下降，那么这可能表示下降趋势正在加强。

3）背离分析：当价格和 KVO 指标出现背离时，可能预示着趋势反转。例如，如果价格创新高，但 KVO 未能创新高，这可能是上涨趋势即将结束的信号。反之，如果价格创新低，但 KVO 未能创新低，这可能是下跌趋势即将结束的信号。

该指标在 Pandas TA 库中的函数是：

```python 

kvo(high, low, close, volume, fast=None, slow=None, signal=None, mamode=None, drift=None, offset=None, **kwargs)

```

未完待续…