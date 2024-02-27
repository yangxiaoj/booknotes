# 量化实战入门115—趋势类指标详解：VHF / Vortex / xsignals 

本文介绍以下几个技术指标：VHF、Vortex、xsignals。这几个指标都属于趋势（ Trend）类型的指标，这类主要用于识别和跟踪市场的主要趋势。这些指标可以帮助投资者确定市场的方向（上升、下降或者横盘），从而帮助投资者决定何时进入或退出市场。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。
## 1. VHF（Vertical Horizontal Filter，垂直水平过滤器）
VHF（Vertical Horizontal Filter，垂直水平过滤器）是一种用于区分趋势市场和盘整市场的技术指标。它通过比较收盘价的最高值和最低值，以及收盘价的变动总和，来衡量市场的波动程度。在趋势市场中，VHF值通常会较高；在盘整市场中，VHF值则会较低。

VHF的计算方法如下：

```python 

VHF = (HCP - LCP) / RollingSum[length] of Change

```

其中：

- HCP = 给定周期（length）内的最高收盘价

- LCP = 给定周期（length）内的最低收盘价

- Change = 每个交易周期的收盘价（Ct）与前一个交易周期的收盘价（Ct-1）之间的绝对差值abs(Ct - Ct-1)

- 用（HCP - LCP）除以Change的滚动总和，得到VHF值。

以下是如何使用VHF指标：

确定市场状态：VHF指标的值可以用来判断市场是在趋势状态还是在盘整状态。一般来说，VHF值高表示市场处于趋势状态，VHF值低表示市场处于盘整状态。

辅助交易决策：在趋势交易中，当VHF值较高时，可以考虑使用追踪趋势的策略，如移动平均线交叉等。当VHF值较低，表示市场可能处于盘整状态，此时可能需要使用震荡型指标，如RSI、随机指标等。

该指标在 Pandas TA 库中的函数是：

```python 

vhf(close, length=None, drift=None, offset=None, **kwargs)

```

## 2. Vortex（Vortex Indicator，涡旋指标）
涡旋指标（Vortex Indicator）用于确定市场趋势的开始和结束。涡旋指标由两个振荡器组成，分别是 VIP（正向涡旋指标）和 VIM（负向涡旋指标），用于捕捉正向和负向趋势的动态。

涡旋指标的计算方法如下：

```python 

VIP = vmp.rolling(length).sum() / tr_sum
VIM = vmn.rolling(length).sum() / tr_sum

```

1）计算每个交易周期的真实范围（TR），然后计算过去length个交易周期的TR的总和（tr_sum）。

2）计算每个交易周期的最高价与前一个交易周期的最低价之间的差的绝对值（vmp），以及每个交易周期的最低价与前一个交易周期的最高价之间的差的绝对值（vmn）。

3）计算vmp和vmn在过去length个交易周期的总和与tr_sum的比值，得到VIP和VIM值。

涡旋指标的使用方法如下：

1）趋势确认：当vip值超过vim值时，可能表示一个上升趋势的开始；相反，当vim值超过vip值时，可能表示一个下降趋势的开始。

2）交叉信号：当vip和vim发生交叉时，可能表示趋势的转变。例如，vip从下方穿过vim可能表示买入信号，而vim从下方穿过vip可能表示卖出信号。

该指标在 Pandas TA 库中的函数是：

```python 

vortex(high, low, close, length=None, drift=None, offset=None, **kwargs)

```

## 3. xsignals（Cross Signals，交叉信号）
Cross Signals（交叉信号）的主要功能是生成基于某个指标穿越两个阈值的交易信号。这些交易信号可以用来确定何时进入和退出交易。这个函数对于技术分析和交易策略的制定非常有用，它可以用于诸如相对强弱指数（RSI）或其他指标，来决定何时基于特定的阈值进行交易。

Cross Signals 首先计算基于某个指标（例如RSI）是否穿越了给定的两个阈值（xa和xb）的交叉信号。然后，这个交叉信号被传递给 tsignals 函数，该函数进一步处理这些信号，生成趋势信号Trends、交易信号Trades、进场信号Entries和出场信号Exits。这些信号的含义可参见 tsignals 函数。

xsignals函数和tsignals函数的关系：

两者返回值的类型相同，都用于生成趋势信号Trends、交易信号Trades、进场信号Entries和出场信号Exits。

两者的不同之处是tsignals函数更通用，它可以接受任意的趋势序列，不特定于任何指标或阈值。而xsignals函数专注于基于指定阈值的交叉信号，xsignals在内部使用tsignals来处理由交叉信号生成的趋势数据，可以看作是tsignals函数的一个特定应用。

该指标在 Pandas TA 库中的函数是：

```python 

xsignals(signal, xa, xb, above: bool = True, long: bool = True, asbool: bool = None, trend_reset: int = 0, trade_offset: int = None, offset: int = None, **kwargs)

```

xsignals函数返回一个包含以下列的pandas DataFrame：

- Trends：趋势列（趋势：1，无趋势：0）

- Trades：交易列（进入：1，退出：-1，其他：0）

- Entries：进入列（进入：1，其他：0）

- Exits：退出列（退出：1，其他：0）

这些返回值的含义可参见 tsignals 函数。

以下是xsignals函数的使用示例：

1）生成的信号将基于多头交易策略

```python 

# 假设你已经有一个包含价格数据的pandas DataFrame df
rsi = df.ta.rsi()  # 计算相对强弱指数RSI指标
# 调用xsignals函数，假设我们想要在RSI上穿20时进场，在RSI下穿80时出场
xsignals_df = xsignals(signal=rsi, xa=20, xb=80, above=True, long=True)

```
上述代码创建一个根据指定的信号（在这个示例中是RSI，即相对强弱指数）穿越两个特定阈值的交易信号系统。下面是每个参数的含义：

- signal=rsi: 这里的signal代表你用来生成交叉信号的指标，rsi是一个Pandas Series对象，它包含了计算好的RSI值。

- xa=20: xa是交叉信号的低阈值。在这个例子中，它被设定为20，这通常被认为是一个超卖水平，在许多交易策略中，当RSI低于这个水平时，会被认为是一个潜在的买入信号。

- xb=80: xb是交叉信号的高阈值。在这个例子中，它被设定为80，这通常被认为是一个超买水平，在许多交易策略中，当RSI高于这个水平时，会被认为是一个潜在的卖出信号。

- above=True: 这个参数确定了信号的穿越方向。由于above被设定为True，xsignals函数将寻找RSI首先从下方穿越20（xa值）的情况，这被视为进场（买入）信号；然后寻找RSI从上方穿越80（xb值）的情况，这被视为出场（卖出）信号。

- long=True: 这个参数确定了交易信号的方向性。由于long被设定为True，生成的信号将基于多头交易策略。这意味着进场信号（当RSI从下方穿越20时生成的信号）将被解读为买入信号，出场信号（当RSI从上方穿越80时生成的信号）将被解读为卖出信号。

2）生成的信号将基于空头交易策略

```python 

xsignals_df = xsignals(signal=rsi, xa=80, xb=30, above=True, long=False)

```

在这个例子中，xa=80和xb=30分别设定了RSI的超买和超卖阈值，long=False则说明我们在生成空头（做空）的交易信号。当RSI首次上升超过80，我们会收到一个卖空（进场）的信号，并在RSI下降至30以下时收到一个买回（出场）的信号，这样一来，我们就构建了一个基于RSI指标的空头交易策略。