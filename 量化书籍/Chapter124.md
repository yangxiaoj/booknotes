# 量化实战入门124—成交量指标详解：资金流量指数MFI / 正成交量指数PVI / 负成交量指数NVI 

本文介绍以下几个技术指标：资金流量指数MFI、正成交量指数PVI、负成交量指数NVI。这几个指标都是跟成交量相关的指标，成交量是衡量市场活跃程度和价格变动有效性的关键因素，它们提供了市场参与者情绪和潜在市场动向的重要线索。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见前文《量化宝藏工具箱：技术指标库 Pandas TA 教程》。
## 1. Money Flow Index（资金流量指数，MFI）

Money Flow Index (MFI) 是一种震荡器指标，用于通过结合价格和交易量来测量买入和卖出压力。

指标的计算方法：

```python 

#1. 计算典型价格 (tp)，等于（最高价 + 最低价 + 收盘价）/ 3
tp = typical_price = hlc3 = (high + low + close) / 3
#2. 计算原始资金流动 (rmf)，等于典型价格乘以交易量
rmf = raw_money_flow = tp * volume
#3. 计算正向资金流动 (pmf)，如果典型价格上升，则等于 rmf 的长度周期和，否则为 0
pmf = pos_money_flow = SUM(rmf, length) if tp.diff(drift) > 0 else 0
#4. 计算负向资金流动 (nmf)，如果典型价格下降，则等于 rmf 的长度周期和，否则为 0
nmf = neg_money_flow = SUM(rmf, length) if tp.diff(drift) < 0 else 0
#5. 计算资金流动比率 (MFR)，等于 pmf 除以 nmf
MFR = money_flow_ratio = pmf / nmf
#6. 计算资金流动指数 (MFI)
MFI = 100 * pmf / (pmf + nmf)

```

以下是使用 MFI 指标的一些常见方法：

1）过买过卖指示：MFI 的值范围在 0 到 100 之间。通常，当 MFI 超过 80 时，市场被认为是过买的，这可能是卖出的信号。反之，当 MFI 低于 20 时，市场被认为是过卖的，这可能是买入的信号。

2）背离：当价格和 MFI 指标的走势出现背离时，可能预示着即将到来的价格反转。例如，如果价格创新高，但 MFI 没有创新高，这可能预示着上升趋势将结束。反之，如果价格创新低，但 MFI 没有创新低，这可能预示着下降趋势将结束。

3）趋势确认：除了作为过买过卖指标和寻找价格背离外，MFI 还可以用于确认价格趋势。如果价格在上升，并且 MFI 也在上升，那么这可能表示买压正在增加，对上升趋势是一个确认的信号。反之，如果价格在下降，并且 MFI 也在下降，那么这可能表示卖压正在增加，对下降趋势是一个确认的信号。

该指标在 Pandas TA 库中的函数是：

```python 

mfi(high, low, close, volume, length=None, talib=None, drift=None, offset=None, **kwargs)

```

## 2. Positive Volume Index（正成交量指数：PVI）
Positive Volume Index (PVI) 是一个累积指标，通过使用交易量的变化，试图识别“聪明钱”的活动。该指标通常与 Negative Volume Index（NVI）一起使用。

PVI 的计算步骤如下：

- 计算价格的变化率 (ROC)。

- 对交易量进行符号化处理，当交易量增加时，符号为1；当交易量减少时，符号为-1；当交易量不变时，符号为0。

- 在交易量增加（符号化处理后为1）的日子，用 ROC 计算 PVI；在交易量减少的日子，PVI 为 0。
- 将所有的 PVI 求累积和，得出的结果就是最终的 PVI 值。
PVI 通常与 Negative Volume Index（NVI）一起使用：

- PVI：关注交易量增加的日子，试图捕捉大众投资者的情绪和市场趋势。

- NVI：关注交易量减少的日子，试图捕捉“聪明钱”（知识丰富、经验丰富的投资者）的行为。

以下是指标的一些常见用法：

1）趋势分析：如果 PVI 和 NVI 都在上升，这可能表示一个强劲的上升趋势，因为无论交易量是增加还是减少，“智能资金”都在买入。相反，如果 PVI 和 NVI 都在下降，这可能表示一个强烈的下降趋势，因为无论交易量是增加还是减少，“智能资金”都在卖出。

2）背离分析：如果 PVI 和价格表现出背离（例如，价格创新高，但 PVI 没有），而 NVI 仍然在上升，这可能表示“智能资金”仍然看好市场，这种背离可能不会持续很长时间。反之，如果 NVI 和价格表现出背离（例如，价格创新低，但 NVI 没有），而 PVI 仍在下降，这可能表示大众投资者仍然看空市场，这种背离可能不会持续很长时间。

3）动量分析：如果 PVI 快速上升而 NVI 平稳，这可能表示市场正在经历一波由大众投资者推动的上涨。如果 NVI 快速上升而 PVI 平稳，这可能表示“智能资金”正在积极买入，可能预示着未来的上涨。

该指标在 Pandas TA 库中的函数是：

```python 

pvi(close, volume, length=None, initial=None, offset=None, **kwargs)

```

## 3. Negative Volume Index（负成交量指数，NVI）
Negative Volume Index (NVI) 是一个累积指标，通过使用交易量的变化，试图识别“聪明钱”的活动。通常与 Positive Volume Index（PVI）一起使用。

NVI 的计算步骤如下：

1. 计算价格的变化率 (ROC)。

2. 对交易量进行符号化处理，当交易量增加时，符号为1；当交易量减少时，符号为-1；当交易量不变时，符号为0。

3. 在交易量减少（符号化处理后为-1）的日子，用 ROC 计算 NVI；在交易量增加的日子，PVI 为 0。

4. 把所有的 NVI 求累积和。
NVI 通常与 Positive Volume Index（PVI）一起使用。指标的用法参见PVI。

该指标在 Pandas TA 库中的函数是：

```python 

nvi(close, volume, length=None, initial=None, offset=None, **kwargs)

```

未完待续……