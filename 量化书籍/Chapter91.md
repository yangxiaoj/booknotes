# 从零学量化91—均线类指标详解：MCGD / PWMA / RMA / SINWMA / SSF / SWMA/ T3 

本文介绍以下几个技术指标：MCGD、PWMA、RMA、SINWMA、SSF、SWMA、T3。这几个指标都属于均线类型的指标。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见《量化宝藏工具箱：技术指标库 Pandas TA 教程》一文。

## 1. MCGD（McGinley Dynamic Indicator，McGinley动态指标）

McGinley动态指标看起来像一条移动平均线，但它实际上是一种趋势跟随指标，它更紧密地跟随价格变动，因此可以更快地反应市场的变化。

McGinley动态指标的特点是：

1）更快反应价格变化：McGinley动态指标的一个主要优点是它能更快地反应市场价格的变化，这是因为它通过一个动态调整的除数来进行计算，而不是像普通的移动平均线那样直接使用固定的时间周期。

2）减少波动误差：McGinley动态指标被设计成能尽可能减少由于市场波动造成的误差，因此它在波动较大的市场环境中可能会表现得更好。

3）市场适应性：McGinley动态指标在下跌市场中会更快地反应价格的变化，而在上涨市场中则会更慢地移动。这使得它能更好地适应市场的变化。

该指标在 Pandas TA 库中的函数是：

```python 

mcgd(close, length=None, offset=None, c=None, **kwargs)
```

## 2. PWMA（Pascal's Weighted Moving Average，帕斯卡加权移动平均）

PWMA基于帕斯卡三角形的权重来计算给定周期内收盘价的加权平均值，PWMA在计算过程中，将更多的权重分配给了最近的价格数据，而非最早的数据，因此能更快地反应最新的市场变化。

PWMA的特点是：

1）反应速度快：由于PWMA给最近的价格数据分配了更多的权重，因此它能更快地反应最新的市场变化。相对于简单移动平均线，PWMA能更准确地捕捉到价格的变动，减少了滞后效应。

2）平滑性好：PWMA能有效地平滑价格数据，减少了价格的噪音，使得投资者能更清晰地看到市场的真实趋势。

PWMA的计算公式为：

```python 

PWMA = (P1 * W1 + P2 * W2 + ... + Pn * Wn) / (W1 + W2 + ... + Wn)

```


其中：

- P1, P2, ..., Pn 分别是过去n期的价格。
  
- W1, W2, ..., Wn 分别是过去n期的权重，通常取自帕斯卡三角形的对应行。
  
该指标在 Pandas TA 库中的函数是：

```python 

pwma(close, length=None, asc=None, offset=None, **kwargs)

```

### 3. RMA（WildeR's Moving Average，WildeR移动平均线）

RMA实际上就是一个修改了α值的指数移动平均（EMA），其中α = 1 / length。

RMA常用于计算其他的技术指标。例如：在计算RSI时，RMA被用于平滑上涨和下跌日的平均变化；在计算ATR时，RMA被用于平滑每日真实范围。

RMA的特点是：

1）滞后性小：与简单移动平均线相比，RMA由于是一种指数移动平均线，更加重视近期的数据，因此滞后性较小。

2）平滑性强：RMA能有效地平滑价格数据，减少了价格的噪音，能更清晰地看到市场的真实趋势。

该指标在 Pandas TA 库中的函数是：

```python 

rma(close, length=None, offset=None, **kwargs)
```

## 4. SINWMA（Sine Weighted Moving Average，正弦加权移动平均）
SINWMA是一个使用正弦周期作为权重的加权平均，平均值的中间项具有最大的权重。

SINWMA的计算公式为：

```python 

SINWMA = (P1 * W1 + P2 * W2 + ... + Pn * Wn) / (W1 + W2 + ... + Wn)

```

其中：

- P1, P2, ..., Pn 分别是过去n期的价格。

- W1, W2, ..., Wn 分别是过去n期的权重，它们的计算方法是：Wi = sin((i * pi) / N)。这里的i是第i期的数据（i从1到N），N是移动平均期数，pi是圆周率。

该指标在 Pandas TA 库中的函数是：

```python 

sinwma(close, length=None, offset=None, **kwargs)

```
## 5. SSF（Ehler's Super Smoother Filter）
SSF是一种通过Ehler在航空航天模拟滤波器设计中的研究，来减少滞后并消除混叠噪声的方法。

SSF有以下特点：

1）平滑性强：SSF通过先进的滤波技术，能有效地平滑价格或指标数据，减少了价格的噪音。

2）滞后性小：相对于传统的移动平均线，SSF能更准确地捕捉到价格的变动，减少了滞后效应。

SSF 的计算过程包括两个主要步骤：

1）计算两周期的移动平均 (Close + pre_Close) / 2：这个步骤的目标是生成一个初步平滑的价格序列，即先对当前的收盘价和前一期的收盘价进行平均。

2）应用滤波器：在这个步骤中，SSF 应用了复杂的滤波器，以进一步平滑价格序列并减少滞后。滤波器的设计基于对周期性数据（如价格或指标）的特性的深入理解，特别是它们的滞后性和噪声特性。

SSF 的工作原理基于这样一个观察：在金融市场中，价格数据往往包含大量的随机噪声，这些噪声会干扰投资者对真实市场趋势的判断。通过使用高级的滤波技术，SSF 能有效地消除这些噪声，使投资者能更清晰地看到市场的真实趋势。同时，由于它的计算方法，SSF 还能减少滞后，使得价格变动能更快地反映到平滑线上，从而提高交易的准确性。

该指标在 Pandas TA 库中的函数是：

```python 

ssf(close, length=None, poles=None, offset=None, **kwargs)

```
## 6. SWMA（Symmetric Weighted Moving Average，对称加权移动平均线）

SWMA的权重基于对称三角形。例如，如果n=3，权重会是[1, 2, 1]；如果n=4，权重会是[1, 2, 2, 1]，等等。

SWMA的特点是反映中期趋势：由于权重在中心点两侧对称，SWMA更能反映价格的中期趋势，而不会过度强调最近的价格变动。

计算对称加权移动平均线的步骤如下：

1. 定义权重函数，该函数将权重和输入值进行点积运算。
   
2. 生成对称三角形权重。
   
3. 对close序列应用滚动窗口，并使用权重函数和对称三角形权重计算加权移动平均值。
   
该指标在 Pandas TA 库中的函数是：

```python 

swma(close, length=None, asc=None, offset=None, **kwargs)

```

## 7. T3（T3 Moving Average，T3移动平均线）
T3移动平均线（T3 Moving Average，T3） 是一种特殊的移动平均线，它使用一种插值的技术，在减少滞后的同时保持曲线的光滑度。

T3移动平均线的特点是：

1）减少滞后：T3移动平均线的目标是减少标准移动平均线的滞后。它通过使用三次指数平滑和插值实现。这使得T3更能反映价格的实时变动。

2）光滑曲线：尽管T3减少了滞后，但是通过插值技术，它仍然能保持曲线的光滑度。这使得T3很适合于趋势跟踪和交叉点检测。

3）灵活性：T3有一个调节参数，允许投资者调节对价格变动的敏感度。这使得T3可以适应各种不同的市场环境和交易策略。

T3移动平均线的计算方法如下：

```python 

c1 = -a^3
c2 = 3a^2 + 3a^3 = 3a^2 * (1 + a)
c3 = -6a^2 - 3a - 3a^3
c4 = a^3 + 3a^2 + 3a + 1

ema1 = EMA(close, length)
ema2 = EMA(ema1, length)
ema3 = EMA(ema2, length)
ema4 = EMA(ema3, length)
ema5 = EMA(ema4, length)
ema6 = EMA(ema5, length)
T3 = c1 * ema6 + c2 * ema5 + c3 * ema4 + c4 * ema3
```

其中：a 是一个浮点数，范围在0到1之间，用于计算T3移动平均线的权重，默认值是0.7。

相比其他移动平均线，T3移动平均线被认为更平滑且对价格变动的反应更迅速。

该指标在 Pandas TA 库中的函数是：

```python 

t3(close, length=None, a=None, talib=None, offset=None, **kwargs)

```