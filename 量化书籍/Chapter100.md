# 量化实战入门100—动量类指标详解：QQE / ROC / RSI / RSX 

本文介绍以下几个技术指标：QQE、ROC、RSI、RSX。这几个指标都属于动量类型的指标。在投资中，动量指的是价格沿着一个方向前进的持续性。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. QQE（Quantitative Qualitative Estimation，定量定性估计）

QQE（Quantitative Qualitative Estimation，定量定性估计）结合了 RSI（相对强弱指数）和 ATR（平均真实范围）的元素，用于判断价格趋势的强度和方向。

QQE 的计算：

QQE 的计算步骤相对复杂，涉及到多个步骤，包括 RSI 的计算、Wilders Smoothing 方法的应用、ATR 的计算等。最终的 QQE 值包括：

QQE 指标值，基础线，Fast QQE 线和 Slow QQE 线。

QQE 的使用方法：

1）交叉信号：当 Fast QQE 线从下方穿过 Slow QQE 线，可能是一个买入信号。反之，如果 Fast QQE 线从上方穿过 Slow QQE 线，可能是一个卖出信号。

2）背离信号：如果价格创新高，但 QQE 没有创新高（形成“顶部背离”），可能预示着市场可能会转向下跌。反之，如果价格创新低，但 QQE 没有创新低（形成“底部背离”），可能预示着市场可能会转向上涨。

该指标在 Pandas TA 库中的函数是：

```python

qqe(close, length=None, smooth=None, factor=None, mamode=None, drift=None, offset=None, **kwargs)

```

## 2. ROC（Rate of Change）

ROC（Rate of Change，变化率）是一种动量型技术分析指标，用于衡量某个给定期间价格的百分比变化。

ROC 的计算公式如下：

```python

ROC = [(Current Price - Price n Periods Ago) / (Price n Periods Ago)] * 100

```

其中，Current Price 是当前价格，Price n Periods Ago 是 n 个期间前的价格。n 可以是任何期间，但常见的值为 12 或 14。

ROC 的使用方法：

1）趋势确定：当 ROC 从负值上升到正值，可能是买入信号；当 ROC 从正值下降到负值，可能是卖出信号。

2）趋势反转：ROC 的方向变化可能预示着趋势的反转。例如，如果 ROC 从上升转为下降，这可能意味着上升趋势即将结束，反之亦然。

3）背离信号：如果价格创新高(新低)，但 ROC 没有创新高(新低)，可能形成顶部(底部)背离，这可能预示着市场趋势的反转。

4）超买或超卖：ROC 指标还可以被用来发现市场的过度买入或过度卖出状态，即当 ROC 达到极大值或极小值时，可能会发生价格反转。

该指标在 Pandas TA 库中的函数是：

```python

roc(close, length=None, scalar=None, talib=None, offset=None, **kwargs)

```

## 3. RSI（Relative Strength Index, 相对强弱指数）
RSI（Relative Strength Index，相对强弱指数）是一种动量振荡器，用于评估一项资产的过度买入或过度卖出状态。RSI 的值范围为0到100，通常用14天周期计算。

SI 指标的计算公式如下：

```python

RSI = 100 * pos_avg / (pos_avg + neg_avg)

```

其中：

pos_avg是价格上升时的价格变化的滚动平均值，反映了近期的平均正向价格变化。

neg_avg是价格下降时的价格变化的滚动平均值，反映了近期的平均负向价格变化。

RSI 的使用方法：

1）超买或超卖：当 RSI 从高于70的区域下降，通常被认为是过度买入状态，可能预示着未来价格将下跌。相反，当 RSI 从低于30的区域上升，通常被认为是过度卖出状态，可能预示着未来价格将上涨。

2）背离：当价格创新高或新低，而 RSI 没有相应地创新高或新低，可能出现所谓的“背离”，此时可能预示着价格的反转。

3）中线交叉：如果 RSI 从下方向上穿过 50，可能预示着市场情绪从悲观转向乐观，可能是买入信号。反之，如果 RSI 从上方向下穿过 50，可能预示着市场情绪从乐观转向悲观，可能是卖出信号。

该指标在 Pandas TA 库中的函数是：

```python 

rsi(close, length=None, scalar=None, talib=None, drift=None, offset=None, **kwargs)

```

## 4. RSX（Relative Strength Xtra, 相对强度 Xtra）
Relative Strength Xtra (RSX) 是一种改进版的相对强弱指数（RSI）指标。其目标是减少噪音并提供更清晰的市场趋势。

由于 RSX 是对 RSI 的改进，其用法也和RSI类似：

1）超买或超卖：当 RSX 从高于70的区域下降，通常被认为是过度买入状态，可能预示着未来价格将下跌。相反，当 RSX 从低于30的区域上升，通常被认为是过度卖出状态，可能预示着未来价格将上涨。

2）背离：当价格创新高或新低，而 RSX 没有相应地创新高或新低，可能出现所谓的“背离”，此时可能预示着价格的反转。

3）中线交叉：如果 RSX 从下方向上穿过 50，可能预示着市场情绪从悲观转向乐观，可能是买入信号。反之，如果 RSX 从上方向下穿过 50，可能预示着市场情绪从乐观转向悲观，可能是卖出信号。

该指标在 Pandas TA 库中的函数是：

```python

rsx(close, length=None, drift=None, offset=None, **kwargs)

```
