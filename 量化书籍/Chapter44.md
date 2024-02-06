# 从零学量化44：用Empyrical库计算金融指标的中文指南（五）
Empyrical是一个由Quantopian开发的开源的Python库，专门用于计算常用的金融风险和性能指标。它包含了许多用于策略回测分析的工具，能够帮助投资者对投资策略的性能进行定量分析。本文详细介绍Empyrical库的用法，由于内容较多，分为五篇阐述。

本篇为第五篇，继续介绍Empyrical库的金融指标函数（按字母排序）：
### 35. roll_up_down_capture(returns, factor_returns, window=10, **kwargs)
该函数 roll_up_down_capture 用于计算滚动窗口期间的上行/下行捕获率。

函数的参数如下：

- returns：策略的日收益，非累计。具体细节请参考 empyrical.stats.cum_returns 函数的解释。
- factor_returns：用于计算贝塔的因子的非累计回报，通常是一个基准，如市场。其格式应与 returns 相同。
- window：以数据的周期性来计算的滚动窗口大小。例如，如果 window = 60，并且周期性为每日，那么代表的是一个滚动的60天窗口。
- **kwargs：转发给 empyrical.stats.up_down_capture 函数的参数。

函数的返回值是滚动上行/下行捕捉率。

上行/下行捕获率（Up/Down Capture）是一个用于评估投资策略在市场上涨和下跌时的表现的指标。它计算的是当参考市场指数上涨或下跌时，策略的平均收益与市场指数的平均收益之间的比率。上行/下行捕获率大于100%表示策略在市场上涨或下跌时的表现优于市场，而小于100%则表示策略在市场上涨或下跌时的表现劣于市场。

滚动上行/下行捕获率就是在一个滚动窗口期间计算的上行/下行捕获率。这可以让投资者看到投资策略在市场上涨和下跌时的表现如何随时间变化，从而更好地理解其性能和风险的稳定性和可持续性。例如，如果一个投资策略的滚动上行/下行捕获率一直较高并且稳定，那么这可能表明该策略在市场上涨或下跌时的表现较好。
### 36.  sharpe_ratio(returns, risk_free=0, period='daily', annualization=None, out=None)
该函数 sharpe_ratio 用于计算策略的夏普比率。

函数的参数如下：

- returns：策略的日收益，非累计。具体细节请参考 empyrical.stats.cum_returns 函数的解释。
- risk_free：在整个期间内的常数日无风险回报。
- period：定义 'returns' 数据的周期性，用于年化。如果指定了 annualization 参数，则忽略此值。默认值如下：

  'monthly':12

  'weekly': 52

  'daily': 252

- annualization：用于抑制 period 中的默认值，将回报转换为年回报。该值应为 returns 的年频率。
- out：用作输出缓冲区的数组，可选。如果不传递此参数，将会创建一个新的数组。

函数的返回值是夏普比率（float类型）。如果回报的长度不足，或者调整后的回报为0，则返回 nan。

夏普比率（Sharpe Ratio）是一个用于评估投资策略的风险调整后表现的指标。它是策略超过无风险回报的平均回报与策略的标准差（代表风险）之比。夏普比率越高，投资策略的风险调整后表现就越好。
### 37. simple_returns(prices)
该函数 simple_returns 用于从价格的时间序列中计算简单收益。
函数的参数如下：

- prices：资产价格，格式：列为资产，索引为日期时间的 pd.Series，pd.DataFrame 或 np.ndarray。

函数的返回值是简单收益（array-like类型）：资产收益，格式：列为资产，索引强制为 tz-aware 格式的日期时间。

简单收益（Simple Returns）是一种最基本的投资回报计算方法，它计算的是连续两期之间价格的变化率。它的计算公式为：(P1 - P0) / P0，其中 P1 是后一期的价格，P0 是前一期的价格。简单收益的优点在于计算简单。
### 38. sortino_ratio(returns, required_return=0, period='daily', annualization=None, out=None, _downside_risk=None)
该函数 sortino_ratio 用于计算策略的索提诺比率。

函数的参数如下：

- returns：策略的日收益，非累计，类型可以为 pd.Series，np.ndarray 或 pd.DataFrame。具体细节请参考 empyrical.stats.cum_returns 函数的解释。
- required_return：最小可接受回报，类型为 float 或 series。
- period：定义 'returns' 数据的周期性，用于年化。如果指定了 annualization 参数，则忽略此值。默认值如下：

  'monthly':12

  'weekly': 52

  'daily': 252

- annualization：用于抑制 period 中的默认值，将回报转换为年回报。该值应为 returns 的年频率。
- _downside_risk：已知的给定输入的下行风险，可选。如果未提供，将会计算。
- out：用作输出缓冲区的数组，可选。如果不传递此参数，将会创建一个新的数组。

函数的返回值是索提诺比率（Sortino Ratio），类型为 float 或 pd.Series，具体取决于输入类型。如果输入类型为 series，返回的索提诺比率为 float；如果输入类型为 DataFrame，返回的索提诺比率为 pd.Series。

索提诺比率（Sortino Ratio）是一个评估投资策略的风险调整后表现的指标，类似于夏普比率，但是索提诺比率在计算风险时只考虑下行风险，即那些低于最小可接受回报的收益。这是因为投资者通常只关心损失，而不关心收益的波动。索提诺比率越高，表示投资策略的风险调整后表现越好。
### 39. stability_of_timeseries(returns)
该函数 stability_of_timeseries 用于确定累积对数收益的线性拟合的 R 平方。
函数的参数如下：

- returns：策略的日收益，非累计。可以为 pd.Series 或 np.ndarray。具体细节请参考 empyrical.stats.cum_returns 函数的解释。

函数的返回值是 R 平方（float类型）。

在统计学中，R 平方（R-squared，也称确定系数）是一个表示模型对数据拟合程度的指标。它的值介于 0 和 1 之间，值越接近 1，表示模型对数据的拟合程度越好。

在这个函数中，我们对策略的累积对数收益进行最小二乘线性拟合，然后计算并返回 R 平方。这个指标可以帮助我们评估策略收益的稳定性，R 平方越高，表示策略收益的稳定性越好。
### 40. tail_ratio(returns)
该函数 tail_ratio 用于确定右尾部（95%）和左尾部（5%）之间的比率。

函数的参数如下：

- returns：策略的日收益，非累计。可以为 pd.Series 或 np.ndarray。具体细节请参考 empyrical.stats.cum_returns 函数的解释。

函数的返回值是尾部比率（Tail Ratio，float类型）。

尾部比率（Tail Ratio）是一个衡量投资策略收益分布偏度的指标。它的计算方法是将收益的右尾部（即最大的 5% 的收益）与收益的左尾部（即最小的 5% 的收益）的绝对值进行比较。

例如，如果尾部比率为 0.25，那么意味着损失是收益的四倍之多。这个指标可以帮助我们理解投资策略的风险特性，尤其是极端情况下的风险。
### 41. up_alpha_beta(returns, factor_returns, **kwargs)
该函数 up_alpha_beta 用于计算基准收益为正时期的 alpha 和 beta。
函数的参数如下：

- returns：策略的收益。
- factor_returns：基准（或因子）的收益。
- **kwargs：其他参数。

这些参数的具体定义和解释，请参见 empyrical.alpha_beta 函数的文档。

函数的返回值是 alpha 和 beta，两者都是 float 类型。
在资本资产定价模型（CAPM）中，alpha 和 beta 是两个关键的参数：

- Alpha（阿尔法）：表示投资策略相对于基准的超额收益。正 alpha 表示策略在调整风险后超过了基准，负 alpha 则表示策略在调整风险后落后于基准。
- Beta（贝塔）：表示投资策略与基准收益的相关性。beta 大于 1 表示策略的波动性超过基准，beta 小于 1 则表示策略的波动性低于基准。

up_alpha_beta 函数只计算基准收益为正时期的 alpha 和 beta，这可以帮助我们理解投资策略在市场上涨时的表现。
### 42. up_capture(returns, factor_returns, **kwargs)
该函数 up_capture 用于计算基准收益为正时期的捕获比率。
函数的参数如下：

- returns：策略的收益，非累计。可以为 pd.Series 或 np.ndarray。具体细节请参考 empyrical.stats.cum_returns 函数的解释。
- factor_returns：用于计算 beta 的因子（通常为基准，如市场）的非累计收益。与 returns 的类型和风格相同。
- period：定义 'returns' 数据的周期性，用于年化。如果指定了 annualization 参数，则忽略此值。默认值如下：

  'monthly':12

  'weekly': 52

  'daily': 252

- **kwargs：其他参数，请参见 empyrical.capture 函数的文档。

函数的返回值是上行捕获比率（Up Capture，float类型）。

上行捕获比率（Up Capture）是一个衡量投资策略在基准收益为正（市场上涨）时期的表现的指标。如果上行捕获比率大于 1，表示策略在市场上涨时超过了基准；如果上行捕获比率小于 1，表示策略在市场上涨时落后于基准。
### 43. up_down_capture(returns, factor_returns, **kwargs)
该函数 up_down_capture(returns, factor_returns, **kwargs) 用于计算上行捕获比率与下行捕获比率的比值。
函数的参数如下：

- returns：策略的收益，非累计。可以为 pd.Series 或 np.ndarray。具体细节请参考 empyrical.stats.cum_returns 函数的解释。
- factor_returns：用于计算 beta 的因子（通常为基准，如市场）的非累计收益。与 returns 的类型和风格相同。
- period：定义 'returns' 数据的周期性，用于年化。如果指定了 annualization 参数，则忽略此值。默认值如下：

  'monthly':12

  'weekly': 52

  'daily': 252

- **kwargs：其他参数，请参见 empyrical.capture 函数的文档。

函数的返回值是上下行捕获比率（Up Down Capture，float类型）。

上下行捕获比率（Up Down Capture）是一个衡量投资策略在市场上涨（基准收益为正）和市场下跌（基准收益为负）时期的表现的指标。它是上行捕获比率与下行捕获比率的比值。这个比率可以帮助我们理解投资策略在不同市场环境（上涨或下跌）下的相对表现。
### 44. value_at_risk(returns, cutoff=0.05)
该函数 value_at_risk 用于计算收益流的风险价值（VaR，Value at Risk）。

函数的参数如下：

- returns：非累计的日收益，可以为 pd.Series 或 np.ndarray。
- cutoff：表示收益底部百分位的截止百分比，为 float 类型，可选。默认为 0.05。

函数的返回值是 VaR（风险价值，float类型）。

风险价值（VaR）是一个用于风险管理的统计技术，用于量化投资组合在正常市场条件下可能的最大损失。例如，如果 VaR 为 -1%，那么在 95% 的情况下（如果 cutoff 为 0.05），投资组合的一日损失不会超过 1%。

需要注意的是，VaR 只考虑了正常市场条件下的风险，并没有考虑极端市场事件的影响。因此，VaR 应当与其他风险度量一起使用，以全面评估投资组合的风险。