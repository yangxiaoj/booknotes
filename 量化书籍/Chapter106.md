# 量化实战入门106—动量类指标详解：SQZ / SQZPRO 

本文介绍两个技术指标：SQZ 和 SQZPRO。这两个指标都属于动量类型的指标。在投资中，动量指的是价格沿着一个方向前进的持续性。

本系列中的各项指标都可以通过调用 Pandas TA 库来实现，Pandas TA 库的使用详见前文《量化宝藏工具箱：技术指标库 Pandas TA 教程》。
## 1. SQZ (Squeeze，挤压指标)
Squeeze 指标试图捕捉 Bollinger Bands（布林带）和 Keltner's Channels（凯尔特纳通道）两种研究之间的关系。当波动性增加时，带间的距离也会增加；反之，当波动性下降时，距离也会减少。Squeeze 指标寻找布林带研究中落入凯尔特纳通道的部分。

Squeeze包括四个主要指标：
    
       SQZ
    
       SQZ_ON
    
       SQZ_OFF
    
       NO_SQZ

它们各自的含义和用法如下：

1）SQZ：SQZ 是动量（MOM）的移动平均值。这个指标可以用来衡量价格走势的强度和方向。

2）SQZ_ON：SQZ_ON 是一个布尔值，表示当前是否处在 "挤压"（Squeeze）状态。当布林带在凯尔特纳通道内部时，SQZ_ON 的值为 True，表示市场处于挤压状态，这通常预示着市场波动性较低。

3）SQZ_OFF：SQZ_OFF 也是一个布尔值，表示当前是否处于 "非挤压"（Non-Squeeze）状态。当布林带在凯尔特纳通道外部时，SQZ_OFF 的值为 True，表示市场处于非挤压状态，这通常预示着市场波动性较高。

4）NO_SQZ：NO_SQZ 是一个布尔值，表示当前既不处于挤压状态也不处于非挤压状态。当 SQZ_ON 和 SQZ_OFF 都为 False 时，NO_SQZ 的值为 True。

在实际应用中，SQZ、SQZ_ON、SQZ_OFF、NO_SQZ 可以联合使用来生成交易信号：

1）当市场从挤压状态（SQZ_ON）转变为非挤压状态（SQZ_OFF），并且 SQZ 指标上升，这可能是一个买入信号，因为这可能预示着价格将继续上涨。

2）相反，如果市场从挤压状态转变为非挤压状态，并且 SQZ 指标下降，这可能是一个卖出信号，因为这可能预示着价格将继续下跌。

该指标在 Pandas TA 库中的函数是：

```python 

squeeze(high, low, close, bb_length=None, bb_std=None, kc_length=None, kc_scalar=None, mom_length=None, mom_smooth=None, use_tr=None, mamode=None, offset=None, **kwargs)
```

## 2. SQZPRO（Squeeze Pro）
Squeeze Pro 是 Squeeze 指标的扩展版本。该指标试图捕捉布林带（Bollinger Bands）和肯特纳通道（Keltner Channels）之间的关系。当市场波动性增加时，这两个带之间的距离也会增加；反之，当市场波动性减少时，距离也会减少。"Squeeze Pro"寻找布林带在肯特纳通道内部的区间，这被认为是市场的“压缩”状态，可能预示着未来的大幅价格变动。

Squeeze Pro 和 Squeeze 之间的主要区别在于它们如何定义和计算压缩（Squeeze）状态：

Squeeze是基础的版本，仅仅检查布林带是否在肯特纳通道之内。如果是，那么市场被认为是在“压缩”状态，预示着可能的大的价格变动。

Squeeze Pro 是 Squeeze 指标的扩展版本，它进一步增加了三种不同宽度的肯特纳通道（宽带、正常带和窄带），并对每种通道都检查布林带是否在其内。这样，Squeeze Pro 能够提供更多关于市场压缩阶段的信息，使投资者可以根据不同的市场条件计算出不同的压缩状态。

Squeeze Pro 包括以下指标：

        SQZPRO
    
        SQZPRO_ON_WIDE
    
        SQZPRO_ON_NORMAL
    
        SQZPRO_ON_NARROW
    
        SQZPRO_OFF_WIDE
    
        SQZPRO_NO

各个指标的含义和使用方法如下：

1）SQZPRO：SQZPRO是基于动量（Momentum）的移动平均。这个指标可以用来衡量价格走势的强度和方向。

2）SQZPRO_ON_WIDE：SQZPRO_ON_WIDE是一个布尔值，表示当前布林带是否在宽的凯尔特纳通道内部。如果是，那么SQZPRO_ON_WIDE的值为True，表示市场处于宽的挤压状态，这通常预示着市场波动性较低。

3）SQZPRO_ON_NORMAL：SQZPRO_ON_NORMAL是一个布尔值，表示当前布林带是否在标准的凯尔特纳通道内部。如果是，那么SQZPRO_ON_NORMAL的值为True，表示市场处于标准的挤压状态。

4）SQZPRO_ON_NARROW：SQZPRO_ON_NARROW是一个布尔值，表示当前布林带是否在窄的凯尔特纳通道内部。如果是，那么SQZPRO_ON_NARROW的值为True，表示市场处于窄的挤压状态。

5）SQZPRO_OFF_WIDE：SQZPRO_OFF_WIDE是一个布尔值，表示当前布林带是否在宽的凯尔特纳通道外部。如果是，那么SQZPRO_OFF_WIDE的值为True，表示市场处于非挤压状态，这通常预示着市场波动性较高。

6）SQZPRO_NO：SQZPRO_NO是一个布尔值，表示当前既不处于宽的挤压状态，也不处于非挤压状态。当SQZPRO_ON_WIDE和SQZPRO_OFF_WIDE都为False时，SQZPRO_NO的值为True。

在实际应用中，这些指标可以联合使用来生成交易信号：

1）当市场从挤压状态（例如：SQZPRO_ON_WIDE、SQZPRO_ON_NORMAL、SQZPRO_ON_NARROW）转变为非挤压状态（例如：SQZPRO_OFF_WIDE），并且SQZPRO指标上升，这可能是一个买入信号，因为这可能预示着价格将继续上涨。

2）相反，如果市场从挤压状态转变为非挤压状态，并且SQZPRO指标下降，这可能是一个卖出信号，因为这可能预示着价格将继续下跌。

该指标在 Pandas TA 库中的函数是：

```python 

squeeze_pro(high, low, close, bb_length=None, bb_std=None, kc_length=None, kc_scalar_wide=None, kc_scalar_normal=None, kc_scalar_narrow=None, mom_length=None, mom_smooth=None, use_tr=None, mamode=None, offset=None, **kwargs)
```

未完待续……