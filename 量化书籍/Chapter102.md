# 量化实战入门102—动量类指标详解：MOM / PGO / PPO / PSL / PVO

本文介绍以下几个技术指标：MOM、PGO、PPO、PSL、PVO。这几个指标都属于动量类型的指标。在投资中，动量指的是价格沿着一个方向前进的持续性。

振荡器（Oscillator）是一种常见的动量指标，它可以通过衡量资产价格的动量或速度来预测未来的市场走势。称为“振荡器”的原因在于这类指标的数值通常围绕某个中心点或者区间“振荡”或波动。振荡器指标可以分为两大类：

1）界限振荡器（Bounded Oscillator）：这类振荡器的值通常被限制在一个固定的范围内，比如0到100。当读数接近上限时，市场可能处于过度买入状态，可能会出现价格回落；当读数接近下限时，市场可能处于过度卖出状态，可能会出现价格反弹。

2）非界限振荡器（Unbounded Oscillator）：这类振荡器没有固定的最大值和最小值，但它的数值仍然会围绕某个值上下波动，反映出价格动量的变化。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. MOM（Momentum，动量）
MOM（Momentum）指标是一种简单但非常实用的技术分析工具，主要用于衡量资产价格变动的速度或动量。它通过比较当前价格和过去某一特定期间的价格来计算动量。

MOM 的计算：

MOM 指标的计算方法非常直接，它是当前价格与 n 期前的价格之差。计算公式如下：

       Momentum = Current Price - Price(n periods ago)


例如，如果我们计算10日MOM，那么就是当前价格减去10天前的价格。
MOM 的使用方法：

1）交叉零线：如果 MOM 从下方穿过零线向上，可能是一个买入信号。反之，如果 MOM 从上方穿过零线向下，可能是一个卖出信号。

2）过度买入或过度卖出：如果 MOM 达到极高或极低的水平，可能表示市场过度买入或过度卖出，即市场可能会出现反转。

3）背离信号：如果价格创新高，但 MOM 没有创新高（形成“顶部背离”），可能预示着市场可能会转向下跌。反之，如果价格创新低，但 MOM 没有创新低（形成“底部背离”），可能预示着市场可能会转向上涨。

该指标在 Pandas TA 库中的函数是：

```python 

mom(close, length=None, talib=None, offset=None, **kwargs)

```
## 2. PGO（Pretty Good Oscillator，相当好的振荡器）
PGO指标用于衡量当前收盘价与其 N 天简单移动平均线（Simple Moving Average，SMA）的距离，通过类似时期的平均真实范围（Average True Range，ATR）来表达。

PGO 指标的计算公式如下：

```python

PGO = (close - SMA(close, length)) / EMA(ATR(high, low, close, length), length)

```

PGO 的使用方法：

1）价格突破：当 PGO 超过 3.0，可能是买入信号，表示价格超过其平均水平；当 PGO 低于 -3.0，可能是卖出信号，表示价格低于其平均水平。

2）过度买入或过度卖出：PGO 可以帮助识别市场的过度买入或过度卖出状态。当 PGO 达到极高的水平时，可能预示着市场过度买入，可能会出现反转。反之，当 PGO 达到极低的水平时，可能预示着市场过度卖出，可能会出现反转。

3）背离信号：如果价格创新高，但 PGO 没有创新高（形成“顶部背离”），可能预示着市场可能会转向下跌。反之，如果价格创新低，但 PGO 没有创新低（形成“底部背离”），可能预示着市场可能会转向上涨。

该指标在 Pandas TA 库中的函数是：

```python 
pgo(high, low, close, length=None, offset=None, **kwargs)

```

## 3. PPO（Percentage Price Oscillator，百分比价格振荡器）

PPO（Percentage Price Oscillator，百分比价格振荡器）是一种动量技术指标，用于显示两个移动平均线的差异的百分比。PPO 的计算与 MACD（移动平均收敛/发散）相似，但是 PPO 是以百分比来表示的，这使得不同资产的 PPO 指标可以进行比较。

PPO 指标的计算公式如下：

```python

#1 先计算两个周期的简单移动平均（SMA）
fast_sma = SMA(close, fast) 
slow_sma = SMA(close, slow)
#2 然后计算 PPO
PPO = 100 * (fast_sma - slow_sma) / slow_sma
# 3 计算 PPO 的信号线
Signal = EMA(PPO, signal)
#4 最后计算 PPO 的直方图
Histogram = PPO - Signal

```

PPO 的使用方法：

1）交叉信号：当 PPO 线从下方穿过信号线（形成“金叉”），可能是买入的信号。反之，如果 PPO 线从上方穿过信号线（形成“死叉”），可能是卖出的信号。

2）零线交叉：当 PPO 线从下方穿过零线，可能是一个买入信号。反之，如果 PPO 线从上方穿过零线，可能是一个卖出信号。

3）背离信号：如果价格创新高，但 PPO 没有创新高（形成“顶部背离”），可能预示着市场可能会转向下跌。反之，如果价格创新低，但 PPO 没有创新低（形成“底部背离”），可能预示着市场可能会转向上涨。

4）直方图（Histogram）：直方图可以被用来衡量价格的动量和趋势。

该指标在 Pandas TA 库中的函数是：

```python 

ppo(close, fast=None, slow=None, signal=None, scalar=None, mamode=None, talib=None, offset=None, **kwargs)

```

## 4. PSL（Psychological Line，心理线）

PSL（Psychological Line，心理线）是一种振荡器类型的指标，主要用于测量市场的情绪或心理状态。它以一定期间内涨势日数占比来衡量市场的牛市或熊市情绪。

PSL 的计算公式如下：

```python

PSL = (Number of Up Days / n) * 100

```

其中，"Number of Up Days" 是过去 n 天内收盘价高于开盘价的天数。常见的 n 取值为 10 或 20。

PSL 的使用方法：

1）超买或超卖：如果 PSL 高于 80，市场可能过度乐观，可能达到超买状态，可能会出现价格反转向下的风险。反之，如果 PSL 低于 20，市场可能过度悲观，可能达到超卖状态，可能会出现价格反转向上的机会。

2）趋势变化：PSL 的变化趋势也可以提供信息。如果 PSL 从下方向上突破 50，可能预示市场情绪从悲观转向乐观，可能是买入信号。反之，如果 PSL 从上方向下突破 50，可能预示市场情绪从乐观转向悲观，可能是卖出信号。

该指标在 Pandas TA 库中的函数是：

```python 

psl(close, open_=None, length=None, scalar=None, drift=None, offset=None, **kwargs)

```

## 5. PVO（Percentage Volume Oscillator，百分比成交量振荡器）

PVO（Percentage Volume Oscillator，百分比成交量振荡器）是一种基于成交量的动量指标，它通过测量两个不同周期的成交量移动平均线之间的差异来衡量成交量的趋势。该指标的计算方式与PPO（百分比价格振荡器）类似，但PPO是基于价格而非成交量。

PVO 指标的计算公式如下：

```python 

#1 计算两个周期的指数移动平均（EMA）
fast_ema = EMA(volume, fast) 
slow_ema = EMA(volume, slow)
#2 然后计算 PVO
PVO = (fast_ema - slow_ema) / slow_ema
#3 计算 PVO 的信号线
Signal = EMA(PVO, signal)
#4 最后计算 PVO 的直方图
Histogram = PVO - Signal

```

PVO 的使用方法：

1）交叉信号：当 PVO 线从下方穿过信号线（形成“金叉”），可能表明成交量有上升趋势，这可能是买入的信号。反之，如果 PVO 线从上方穿过信号线（形成“死叉”），可能表明成交量有下降趋势，这可能是卖出的信号。

2）零线交叉：当 PVO 线从下方穿过零线，可能是一个买入信号，因为这可能表明短期成交量正在超过长期成交量。反之，如果 PVO 线从上方穿过零线，可能是一个卖出信号，因为这可能表明短期成交量正在低于长期成交量。

3）PVO 指标的直方图（Histogram）也可以被用来衡量成交量的变化速度和趋势。

该指标在 Pandas TA 库中的函数是：

```python 

pvo(volume, fast=None, slow=None, signal=None, scalar=None, offset=None, **kwargs)

```
