# 量化实战入门121—成交量指标详解：能量潮OBV / AOBV 

本文介绍以下几个技术指标：能量潮OBV，AOBV。这几个指标都是跟成交量相关的指标，成交量是衡量市场活跃程度和价格变动有效性的关键因素，它们提供了市场参与者情绪和潜在市场动向的重要线索。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见前文《量化宝藏工具箱：技术指标库 Pandas TA 教程》。

## 1. On-Balance Volume（能量潮，OBV）
On Balance Volume (OBV) 是一种累积的技术分析指标，用于衡量买卖压力。通过将每个交易日的成交量与价格涨跌情况结合起来，累积计算出来的 OBV 可以反映出市场中的资金流向。

在 OBV（On Balance Volume）指标的计算过程中，首先需要计算 signed_volume，然后基于 signed_volume 计算出 obv。具体过程如下：

1）计算 signed_volume：

首先，根据收盘价的涨跌情况，生成一个新的序列，其元素值为1（涨）、-1（跌）或0（平）。

然后，将这个序列值与成交量 volume 相乘，得到 signed_volume。

2）计算 obv：

obv 是 signed_volume 的累积和，即将 signed_volume 中从第一个元素开始到当前元素的所有元素值相加。

所以，obv 表示的是从第一个交易日开始到当前交易日的累积买卖压力。如果 signed_volume 的值为正，说明当日的买压大于卖压，资金流入市场，OBV 值增加；如果 signed_volume 的值为负，说明当日的卖压大于买压，资金流出市场，OBV 值减少。

以下是一些常见的OBV指标用法：

1）趋势确认：OBV指标可以用于确认股票的总体趋势。如果OBV线与股票价格同步上升，这可能表明存在一个上升趋势。相反，如果OBV线与股票价格同步下降，则可能表明存在一个下降趋势。

2）发现背离：如果OBV线与股票价格的走势出现不一致（也称为背离），这可能是市场反转的一个信号。例如，如果股票价格创新高，但OBV没有创新高，这可能预示着上涨趋势即将结束。反之，如果股票价格创新低，但OBV没有创新低，这可能预示着下跌趋势即将结束。

3）量价关系：OBV指标还可以用来分析量价关系。在价格上涨的过程中，如果OBV也同步上涨，这可能表明上涨趋势得到了交易量的支持，趋势可能会继续。相反，如果价格下跌，而OBV则上升，那么这可能表明下跌趋势可能即将结束，市场可能会反转上涨。

4）交易信号：一些投资者还会使用OBV的移动平均线来生成交易信号。例如，当OBV线上穿其移动平均线时，可能是一个买入信号；当OBV线下穿其移动平均线时，可能是一个卖出信号。

该指标在 Pandas TA 库中的函数是：

```python 

obv(close, volume, talib=None, offset=None, **kwargs)

```

## 2. Archer On-Balance Volume（AOBV）
Archer On Balance Volume（AOBV）是一种改进的On Balance Volume（OBV）指标，由于OBV指标可能受大额交易影响，AOBV增加了一些平滑处理和参数调整，使其更灵活。AOBV结合了价量关系和移动平均线，用于评估市场的买卖压力和可能的价格变动。

计算方法：

AOBV首先计算OBV值，然后对其进行快速（默认值为4）和慢速（默认值为12）移动平均（默认为指数移动平均，EMA）。接着，它计算了两个移动平均线之间的长短趋势。最后，所有这些数据都在一个DataFrame中返回。

AOBV返回的DataFrame中包含了多个序列，每个序列的含义如下：

- obv：这是On Balance Volume（OBV）的基本计算结果。OBV是一种常用的技术分析指标，用于通过将交易量信息与价格趋势相结合，来衡量买卖压力的变化。

- OBV_min_{min_lookback}：这个序列表示在最小回看期内，OBV的最小值。它可以帮助投资者了解资金流向在近期的最低点，以便于评估市场情绪的低点。

- OBV_max_{max_lookback}：这个序列表示在最大回看期内，OBV的最大值。它可以帮助投资者了解资金流向在近期的最高点，以便于评估市场情绪的高点。

- OBV{_ma}_{fast}：这是快速移动平均的OBV值。移动平均是一种常用的技术分析工具，用于平滑数据并识别价格趋势。快速移动平均线反应了OBV的短期变化。

- OBV{_ma}_{slow}：这是慢速移动平均的OBV值。慢速移动平均线反应了OBV的长期变化。

- AOBV_LR_{run_length}：这个序列表示多头趋势的OBV值。如果快速移动平均线在过去的run_length期中一直高于慢速移动平均线，那么就认为存在多头趋势。

- AOBV_SR_{run_length}：这个序列表示空头趋势的OBV值。如果快速移动平均线在过去的run_length期中一直低于慢速移动平均线，那么就认为存在空头趋势。

以下是一些使用AOBV指标的常见方法：

1）趋势确认：通过比较快速移动平均（OBV{_ma}_{fast}）和慢速移动平均（OBV{_ma}_{slow}），可以判断股票的短期和长期趋势。如果快速移动平均线上穿慢速移动平均线，可能预示着上涨趋势；相反，如果快速移动平均线下穿慢速移动平均线，可能预示着下跌趋势。

2）买卖信号：AOBV_LR_{run_length} 和 AOBV_SR_{run_length} 可以用来生成买卖信号。如果 AOBV_LR_{run_length} 为正，说明快速移动平均线在过去的 run_length 期内一直高于慢速移动平均线，这可能是一个买入信号；相反，如果 AOBV_SR_{run_length} 为正，说明快速移动平均线在过去的 run_length 期内一直低于慢速移动平均线，这可能是一个卖出信号。

3）市场极值的识别：OBV_min_{min_lookback} 和 OBV_max_{max_lookback} 可以帮助识别市场的极值。如果 OBV 值接近 OBV_min_{min_lookback}，可能预示着市场过度卖空，存在反弹的可能；相反，如果 OBV 值接近 OBV_max_{max_lookback}，可能预示着市场过度买入，存在回调的可能。

4）背离分析：如果股票价格的走势与 OBV 的走势出现背离，可能预示着价格趋势即将反转。例如，如果股票价格创新高，但 OBV 没有创新高，这可能预示着上涨趋势即将结束。

该指标在 Pandas TA 库中的函数是：

```python 

aobv(close, volume, fast=None, slow=None, max_lookback=None, min_lookback=None, mamode=None, offset=None, **kwargs)

```

未完待续……