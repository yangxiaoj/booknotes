# 从零学量化49：QuantStats库之金融指标中文指南（五）
### 32. outliers(returns, quantile=0.95)
outliers函数是QuantStats库中的一个函数，它用于识别和返回投资组合或资产回报率的异常值。异常值通常被定义为小于第1分位数或大于第99分位数的值。在这个函数中，你可以通过quantile参数来自定义你认为的异常值的定义。

函数的定义和用法如下：

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- quantile：这是一个数值，代表你希望确定的异常值的分位数。默认值为0.95，即函数会返回大于95分位数和小于5分位数的值。你可以根据需要调整这个参数。

函数的返回值是一个序列，包含了returns中的所有异常值。这个序列的索引与returns的索引相同。

这个函数是金融统计分析中的一个常用工具，可以用来识别和处理异常值。异常值可能是由数据错误、极端事件或其他原因造成的，对这些值的识别和处理可以帮助我们更准确地理解和分析数据的分布和性质。
### 33. payoff_ratio(returns, prepare_returns=True)
payoff_ratio函数是QuantStats库中的一个函数，用于计算投资组合或资产的盈亏比率。这个比率是由平均正回报和平均负回报之间的比率计算得出。如果这个比率大于1，那么平均正回报大于平均负回报；如果这个比率小于1，那么平均负回报大于平均正回报。

函数的定义和用法如下：

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- prepare_returns：这是一个布尔值，用于决定是否需要对returns进行预处理。如果设为True，函数会将returns进行预处理，将价格数据转换为回报率，并进行一些数据清理工作。

函数的返回值是returns的收益比率，这个值描述了平均正回报与平均负回报的比例。


### 34. pct_rank(prices, window=60)
pct_rank函数是一个金融数据分析函数，它将每一个时间窗口内的价格数据转换为每个价格在该时间窗口内的百分位等级。这可以帮助投资者理解在特定时间窗口内，价格相对于过去价格的位置。

函数的定义和用法如下：

- prices：这是一个数组或序列，代表你的投资组合或资产的价格数据。
- window：这是一个整数，表示计算百分位等级的滚动窗口的大小。默认值为60，即默认每次计算是基于过去60个交易日的价格数据。

函数的返回值是一个和prices同样长度的序列，每个位置的值表示该位置的价格在过去window天的价格中的百分位等级。百分位等级的范围是0到1，0表示最低，1表示最高。
### 35. probabilistic_ratio(series, rf=0.0, base='sharpe', periods=252, annualize=False, smart=False)
probabilistic_ratio函数是用于计算一种基于概率的风险调整比率的工具。这个比率可以是Sharpe比率、Sortino比率或其他类似的风险调整比率。这个函数采用了一种基于概率的方法来计算这些比率，并对它们进行调整，以更好地处理极端值和非正态分布的情况。

函数的定义和用法如下：

- series：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- rf：这是一个数值，代表无风险利率。默认值为0.0。无风险利率通常用于计算超额回报，即投资回报与无风险回报之间的差值。
- base：这是一个字符串，用于指定基础的风险调整比率。默认值为'sharpe'，即默认计算Sharpe比率。也可以选择其他的风险调整比率：'sortino'、'adjusted_sortino'。
- periods：这是一个整数，代表一年内的交易天数。默认值为252，代表一年内的交易天数通常为252天。
- annualize：这是一个布尔值，用于决定是否需要将风险调整比率年化。如果设置为True，那么函数会将风险调整比率年化；如果设置为False，那么函数将返回原始的风险调整比率。
- smart：这是一个布尔值，用于决定是否需要使用"smart"方式来计算风险调整比率。如果设置为True，那么函数会使用一种特殊的方法来计算风险调整比率，这种方法可以更好地处理极端值和非正态分布的情况。

函数的返回值是调整后的风险调整比率，这个值可以用来评估投资组合或资产的风险调整性能。风险调整比率越大，意味着在承受同样的风险时，投资组合或资产的回报越高。


### 36. probabilistic_sharpe_ratio(series, rf=0.0, periods=252, annualize=False, smart=False)
probabilistic_sharpe_ratio函数是一种基于概率的Sharpe比率计算方法。Sharpe比率是一种衡量投资组合风险调整回报的工具，计算的是投资组合超额回报（投资组合回报减去无风险回报率）和投资组合的风险（标准差）之间的比例。用于评估投资组合每承担一单位风险所获得的超额回报。

函数的定义和用法如下：

- series：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- rf：这是一个数值，代表无风险利率。默认值为0.0。无风险利率通常用于计算超额回报，即投资回报与无风险回报之间的差值。
- periods：这是一个整数，代表一年内的交易天数。默认值为252，代表一年内的交易天数通常为252天。
- annualize：这是一个布尔值，用于决定是否需要将Sharpe比率年化。如果设置为True，那么函数会将Sharpe比率年化；如果设置为False，那么函数将返回原始的Sharpe比率。
- smart：这是一个布尔值，用于决定是否需要使用"smart"方式来计算Sharpe比率。如果设置为True，那么函数会使用一种特殊的方法来计算Sharpe比率，这种方法可以更好地处理极端值和非正态分布的情况。

函数的返回值是一个基于概率的Sharpe比率，这个比率可以用来评估投资组合或资产的风险调整性能。Sharpe比率越大，意味着在承受同样的风险时，投资组合或资产的回报越高。
### 37. probabilistic_sortino_ratio(series, rf=0.0, periods=252, annualize=False, smart=False)
probabilistic_sortino_ratio函数是一种基于概率的Sortino比率计算方法。Sortino比率是一种衡量投资组合风险调整回报的工具，类似于Sharpe比率，但是它只考虑下行风险（负回报）。这使得Sortino比率成为一种更为严格的风险调整性能度量工具。

函数的定义和用法如下：

- series：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- rf：这是一个数值，代表无风险利率。默认值为0.0。无风险利率通常用于计算超额回报，即投资回报与无风险回报之间的差值。
- periods：这是一个整数，代表一年内的交易天数。默认值为252，代表一年内的交易天数通常为252天。
- annualize：这是一个布尔值，用于决定是否需要将Sortino比率年化。如果设置为True，那么函数会将Sortino比率年化；如果设置为False，那么函数将返回原始的Sortino比率。
- smart：这是一个布尔值，用于决定是否需要使用"smart"方式来计算Sortino比率。如果设置为True，那么函数会使用一种特殊的方法来计算Sortino比率，这种方法可以更好地处理极端值和非正态分布的情况。

函数的返回值是一个基于概率的Sortino比率，这个比率可以用来评估投资组合或资产的风险调整性能。Sortino比率越大，意味着在承受同样的下行风险时，投资组合或资产的回报越高。
### 38. probabilistic_adjusted_sortino_ratio(series, rf=0.0, periods=252, annualize=False, smart=False)
probabilistic_adjusted_sortino_ratio是一个用于计算调整Sortino比率的函数，它采用概率性的方法来计算Sortino比率，并对其进行调整。Sortino比率是一种风险调整性能度量，它与夏普比率类似，但是Sortino比率只考虑下行风险，也就是负回报。

函数的定义和用法如下：

- series：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- rf：这是一个数值，代表无风险利率。默认值为0.0。无风险利率通常用于计算超额回报，即投资回报与无风险回报之间的差值。
- periods：这是一个整数，代表一年内的交易天数。默认值为252，代表一年内的交易天数通常为252天。
- annualize：这是一个布尔值，用于决定是否需要将Sortino比率年化。如果设置为True，那么函数会将Sortino比率年化；如果设置为False，那么函数将返回原始的Sortino比率。
- smart：这是一个布尔值，用于决定是否需要使用"smart"方式来计算Sortino比率。如果设置为True，那么函数会使用一种特殊的方法来计算Sortino比率，这种方法可以更好地处理极端值和非正态分布的情况。

函数的返回值是调整后的Sortino比率，这个值可以用来评估投资组合或资产的风险调整性能。Sortino比率越大，意味着在承受同样的下行风险时，投资组合或资产的回报越高。

（未完待续）