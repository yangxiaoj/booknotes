# 量化实战入门98—动量类指标详解：MACD / KDJ / KST / Inertia

本文介绍以下几个技术指标：MACD、KDJ、KST、Inertia。这几个指标都属于动量类型的指标。在投资中，动量指的是价格沿着一个方向前进的持续性。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. MACD（Moving Average Convergence Divergence，移动平均收敛/发散）
MACD用于识别证券的趋势。虽然前面介绍过的APO和MACD的计算相同，但MACD还返回了另外两个系列，称为信号（Signal）和直方图（Histogram）。信号是MACD的EMA（指数移动平均），而直方图是MACD和信号的差。

MACD的计算方法如下：

```python 

MACD = EMA(close, fast) - EMA(close, slow)
Signal = EMA(MACD, signal)
Histogram = MACD - Signal

```

MACD 的使用方法：

1）交叉信号：当 MACD 线从下方穿过信号线（形成“金叉”），可能是买入的信号。反之，如果 MACD 线从上方穿过信号线（形成“死叉”），可能是卖出的信号。

2）背离信号：如果价格创新高，但 MACD 没有创新高（形成“顶部背离”），可能预示着市场可能会转向下跌。反之，如果价格创新低，但 MACD 没有创新低（形成“底部背离”），可能预示着市场可能会转向上涨。

3）柱状图：当柱状图从负值转为正值，可能是一个买入信号。反之，如果柱状图从正值转为负值，可能是一个卖出信号。

该指标在 Pandas TA 库中的函数是：

```python 

macd(close, fast=None, slow=None, signal=None, talib=None, offset=None, **kwargs)

```

## 2. KDJ（随机指标）
KDJ（随机指标）是一种衍生自 Slow Stochastic（慢速随机线）的指标，额外增加了一个被称为 J 线的线条。J 线代表的是 %D 值与 %K 值之间的偏离程度。J 线的值可以超出 %K 和 %D 线在图表上的 [0,100] 范围。

KDJ 指标主要用于判断股票的超买超卖状态以及可能的反转信号：

- 当 K 线与 D 线在低位交叉并向上突破时，可能是买入信号；

- 当 K 线与 D 线在高位交叉并向下突破时，可能是卖出信号；

- 当 J 线超过 100，市场可能过热，出现超买现象，可能有下跌的风险；

- 当 J 线低于 0，市场可能过冷，出现超卖现象，可能有上涨的机会。
KDJ 指标的计算公式如下：

```python 

# 计算过去 length 个周期的最低价 LL 和最高价 HH
LL = low for last length periods
HH = high for last length periods
# 计算 FAST_K
FAST_K = 100 * (close - LL) / (HH - LL)
# 计算 K、D 和 J
K = RMA(FAST_K, signal)
D = RMA(K, signal)
J = 3 * K - 2 * D

```

KDJ 的使用方法：

1）金叉和死叉：如果 K 线从下向上穿过 D 线（即形成“金叉”），尤其是在低位金叉并向上突破时，可能是买入的信号；如果 K 线从上向下穿过 D 线（即形成“死叉”），尤其是在高位死叉并向下突破时，可能是卖出的信号。

2）超买超卖：如果 KDJ 的值超过 80，可能表示市场处于超买状态，即价格可能会下跌。反之，如果 KDJ 的值低于 20，可能表示市场处于超卖状态，即价格可能会上涨。

3）J线的警示：J 线可以作为预警信号。如果 J 线的值大于 100，可能表示市场过热，价格可能会回落。反之，如果 J 线的值小于 0，可能表示市场过冷，价格可能会反弹。

该指标在 Pandas TA 库中的函数是：

```python 

kdj(high=None, low=None, close=None, length=None, signal=None, offset=None, **kwargs)

```

## 3. KST（Know Sure Thing）
KST（Know Sure Thing）是一种动量振荡器，它结合了不同长度的 ROC（Rate of Change）指标，以捕捉市场的长期、中期和短期趋势。

KST 的计算：

KST 是四个不同长度的 ROC 的加权和，ROC 的长度通常为 10、15、20 和 30 天。每个 ROC 会先被平滑，然后再乘以一个权重因子。通常来说，短期的 ROC 会有较小的权重，长期的 ROC 会有较大的权重。
以下是一个简单的 KST 的计算公式：

```python 

KST = SMA(ROC(10),10) * 1 + SMA(ROC(15),10) * 2 + SMA(ROC(20),10) * 3 + SMA(ROC(30),15) * 4

```

此外，还会有一个信号线（KST_Signal）与 KST 线一起使用，信号线通常是 KST 线的移动平均线。

KST 的使用方法：

1）交叉信号：当 KST 线从下方穿过信号线，可能是一个买入信号。反之，当 KST 线从上方穿过信号线，可能是一个卖出信号。

2）背离信号：如果价格创新高，但 KST 没有创新高，可能预示着顶部背离，即市场可能会转向下跌。反之，如果价格创新低，但 KST 没有创新低，可能预示着底部背离，即市场可能会转向上涨。

）过度买入或过度卖出：虽然 KST 没有固定的超买或超卖阈值，但当 KST 达到极高或极低的水平时，市场可能处于过度买入或过度卖出的状态。

该指标在 Pandas TA 库中的函数是：

```python 

kst(close, roc1=None, roc2=None, roc3=None, roc4=None, sma1=None, sma2=None, sma3=None, sma4=None, signal=None, drift=None, offset=None, **kwargs)

```

## 4. Inertia（惯性指标）
Inertia用于测量股票价格的内在动力或惯性。该指标是通过将最小二乘移动平均（Least Squares Moving Average，LSQRMA）应用于 Relative Vigor Index（RVI，相对活力指数）来计算的。

Inertia 的计算步骤如下：

```python 

# 首先，计算 Relative Vigor Index（RVI）。RVI 的计算公式如下
RVI = (Close - Open) / (High - Low)
# 然后，使用最小二乘移动平均（Least Squares Moving Average, LSQRMA）对 RVI 进行平滑处理，得到 Inertia。
INERTIA = LSQRMA(RVI(length), ma_length)

```

Inertia 的使用方法：

1）确定趋势方向：如果 Inertia 的值大于50，表示正向惯性，市场可能处于上升趋势。如果 Inertia 的值小于等于50，表示负向惯性，市场可能处于下降趋势。

2）衡量市场活跃度：Inertia 实际上是 RVI 的平滑版本，因此它也可以用来衡量市场的活跃度。值越高，表示市场活跃度越大，反之则表示市场活跃度较小。

该指标在 Pandas TA 库中的函数是：

```python 

inertia(close=None, high=None, low=None, length=None, rvi_length=None, scalar=None, refined=None, thirds=None, mamode=None, drift=None, offset=None, **kwargs)

```
