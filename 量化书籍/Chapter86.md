# 从零学量化86—量化必备工具：常用的技术指标库简介 

在上一节《技术指标还有效吗》中我们介绍了技术因子的概念和应用，技术因子种类繁多，经验丰富的投资者可以根据自己对市场的理解来构建技术因子，而对于初学者，使用已有的技术因子无疑是更好的选择。在Python中使用使用技术因子非常方便，Python有很多技术因子库，在这些库中有海量的技术因子，使用时只需简单调用即可。而且，借助Python库，很容易就能将通达信等传统分析软件的技术指标转化为Python代码，对老股民非常方便。下面就介绍一些常用的技术因子库：

## 一、TA-Lib 库

TA-Lib 是最著名的技术分析库之一，它提供了超过150种常见的技术分析指标和K线形态识别。

### 1. 安装

在Python环境下，你可以使用pip进行安装。在终端或命令行中运行以下命令：

```python 

pip install TA-Lib

```

注意，TA-Lib的Python接口需要预先安装一个C库，在某些操作系统（如Windows）上会有些复杂，如果安装发生错误，请搜索相关教程。

### 2. 使用
   
安装完毕后，你可以在Python中导入TA-Lib并使用它。以下是一些基本的使用示例：

```python 

# 导入需要的库
import talib
import numpy as np

# 创建一个随机数列
close = np.random.random(100)

# 计算简单移动平均
output = talib.SMA(close)

# 计算指数移动平均
output = talib.EMA(close, timeperiod=25)

# 计算MACD
macd, macdsignal, macdhist = talib.MACD(close, fastperiod=12, slowperiod=26, signalperiod=9)

# 计算RSI
output = talib.RSI(close, timeperiod=14)

```

### 3. TA-Lib的功能

你可以使用talib.get_functions()获取TA-Lib提供的所有函数的列表，或使用talib.get_function_groups()获取按类别分组的函数列表。

TA-Lib的功能组有：

Overlap Studies 重叠研究

Momentum Indicators 动量指标

Volume Indicators 成交量指标

Volatility Indicators 波动性指标

Price Transform 价格指标

Cycle Indicators 周期指标

Pattern Recognition K线形态识别

Statistic Functions 统计函数

Math Transform 数学变换

Math Operators 数学运算符

## 二、Pandas TA库

Pandas TA是一个基于Python的技术分析库，专为与pandas数据分析库配合使用而设计。Pandas TA提供了超过130种技术分析指标，包括各种类型的移动平均线、振荡器、趋势线、动量指标等。所有的技术分析指标都可以直接在pandas DataFrame上进行计算，无需转换数据格式。Pandas TA的API设计得直观且易于使用。你可以通过调用DataFrame对象的ta属性来访问所有的技术分析指标。

### 1. 安装

在Python环境下，你可以使用pip进行安装。在终端或命令行中运行以下命令：

```python 

pip install pandas_ta

````

### 2. 使用
   
安装完毕后，你可以在Python中导入pandas_ta并使用它。以下是一些基本的使用示例：

```python 

# 导入需要的库
import pandas as pd
import numpy as np
import pandas_ta as ta

# 创建一个DataFrame
df = pd.DataFrame({
    'close': np.random.random(100),
    'volume': np.random.random(100)
    })

# 计算SMA
df.ta.sma(close='close', length=10, append=True)

# 计算EMA
df.ta.ema(close='close', length=10, append=True)

# 计算RSI
df.ta.rsi(close='close', length=14, append=True)

# 计算MACD
df.ta.macd(close='close', fast=12, slow=26, signal=9, append=True)

# 计算OBV (On Balance Volume)
df.ta.obv(close='close', volume='volume', append=True)

# 输出计算结果
print(df)

```


在上面的例子中，我们使用了append=True参数，这会将计算结果添加到原始的DataFrame中。

你可以使用dir(ta)列出pandas_ta提供的所有函数和指标。每个指标函数都有详细的文档，你可以使用Python的help()函数查看，例如help(ta.sma)。

在后续文章我们还会对pandas_ta库作详细介绍。

## 三、MyTT 库

MyTT库可以将通达信、同花顺、文华麦语言等指标公式移植到Python中，全部基于numpy和pandas的函数封装，和通达信，同花顺等指标写法完全兼容，一个指标基本不用做修改，直接拿来即可使用。

此外，MyTT库也内置了各种常见指标，可以直接调用。

### 1. 安装

在Python环境下，你可以使用pip进行安装。在终端或命令行中运行以下命令：

```python 

pip install MyTT

```

### 2. 使用

安装完毕后，你可以在Python中导入MyTT并使用它。以下是使用MyTT库将通达信公式转换为Python代码的示例：

我们以RSI（Relative Strength Index，相对强弱指标）为例，RSI的通达信公式为：

```python

LC:=REF(CLOSE,1);
RSI:=SMA(MAX(CLOSE-LC,0),N,1)/SMA(ABS(CLOSE-LC),N,1)*100;

```


这个公式在Python中是不能直接使用的，下面我们用MyTT来转换为Python可以识别的代码：

```python 

# 导入需要的库
import pandas as pd
import numpy as np
from MyTT import *

# 创建一个DataFrame
df = pd.DataFrame({
    'close': np.random.random(100),
    })

# 将通达信公式转换为Python代码
CLOSE = df['close']
N = 14
LC = REF(CLOSE,1)
RSI = SMA(MAX(CLOSE-LC,0),N,1)/SMA(ABS(CLOSE-LC),N,1)*100

# 输出RSI
print(RSI)

```

从上述示例可以看到，在导入了MyTT库之后，我们只需将原来的通达信公式做少量的改动，就能将其转换为Python可以识别的代码。通达信公式需要做的改动具体有以下几方面：

1. 指定通达信中的量价数据（CLOSE、OPEN、HIGH、LOW、VOLUME等），在通达信软件中可以直接对这些量价数据取数，但在Python环境中我们需要指定这些数据。在上面的例子中，我们通过 “CLOSE = df['close']” 指定了 CLOSE 数据。
   
2. 指定通达信公式中的参数。例如上面的公式中有一个参数 ”N“，我们通过 ”N = 14“ 来指定这个参数。
   
3. 将通达信中的赋值语句 “:=” 以及 “:”，统一改为 “=”。
   
4. 将通达信中的 ”AND“ 改为 ”&“。

5.  将通达信中的 ”OR“ 改为 ”|“。

6.  通达信中的等号 ”=“ 是逻辑判断符号，需要改为 ”==“。

7. 如果通达信的语句过长，需要适当拆分一下，并适当加上括号，这样有助于正确识别。

在本节中，我们介绍了TA-Lib 库、Pandas TA库、MyTT 库这几个常用的技术因子库，实际上Python的技术因子库还有很多，使用方法都大同小异。从下一节开始，我们将以 Pandas TA 库为例，介绍常见的技术因子的含义和用法。