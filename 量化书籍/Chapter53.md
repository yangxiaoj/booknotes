# 从零学量化53：QuantStats库之金融指标中文指南（九）
### 62. ulcer_performance_index(returns, rf=0)
ulcer_performance_index函数用于计算溃疡性能指数（Ulcer Performance Index，UPI）。此指数是风险调整后的投资组合绩效度量，将投资组合的超额回报（相对于无风险利率）与其溃疡指数（下行风险）相结合。计算公式为：（投资组合年化回报率 - 无风险利率） / 溃疡指数。

以下是函数的定义和使用方法：

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- rf：这是一个数值，代表无风险利率。无风险利率通常用于计算超额回报，即投资回报与无风险回报之间的差值。

函数的返回值是一个数值，代表投资组合的溃疡性能指数。这个指数可以用来评估投资组合在考虑下行风险的情况下的风险调整后的表现。
### 63. upi(returns, rf=0)
同ulcer_performance_index(returns, rf=0)
### 64. value_at_risk(returns, sigma=1, confidence=0.95, prepare_returns=True)
value_at_risk函数用于计算风险价值（Value at Risk，VaR）。VaR是一种风险度量方法，用来评估在一定置信水平下，一段时间内可能遭受的最大损失。这是金融领域广泛接受的风险管理工具。

以下是函数的定义和使用方法：

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- sigma：这是一个数值，代表投资组合的标准差。默认值为1。标准差是一个常见的风险度量，它衡量的是投资组合回报的波动性。
- confidence：这是一个数值，代表置信水平。默认值为0.95，表示我们有95%的信心，投资组合的损失不会超过计算出的风险价值。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

函数的返回值是一个数值，代表在给定置信水平下的风险价值。这个数值可以被解释为，在最糟糕的5%的情况下，预期的最大损失。
### 65.  var(returns, sigma=1, confidence=0.95, prepare_returns=True)
同value_at_risk(returns, sigma=1, confidence=0.95, prepare_returns=True)
### 66. volatility(returns, periods=252, annualize=True, prepare_returns=True)
volatility函数用于计算投资回报的波动性，也就是标准差。在金融分析中，投资的波动性通常被视为风险的一种度量。

以下是函数的定义和使用方法：

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- periods：这是一个数值，代表回报频率。对于日收益率，该值为252或365；对于月收益率，该值为12。
- annualize：这是一个布尔值，决定是否需要将波动性年化。如果为True，函数将将计算出的波动性转换为年化波动性。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

函数的返回值是一个数值，代表投资组合的波动性。这个数值可以帮助投资者和资产管理者评估投资组合的风险。
### 67. win_loss_ratio(returns, prepare_returns=True)
win_loss_ratio函数用于计算胜率/损率比（Win/Loss Ratio），这是一种评估投资组合绩效的指标。它是投资组合中获胜交易（即，产生正回报的交易）的平均回报和损失交易（即，产生负回报的交易）的平均损失之间的比率。

以下是函数的定义和使用方法：

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

函数的返回值是一个数值，代表投资组合的胜率/损率比。这个数值可以帮助投资者和资产管理者评估投资策略的有效性，尤其是在考虑交易频率和交易成本的情况下。
### 68. win_rate(returns, aggregate=None, compounded=True, prepare_returns=True)
win_rate函数用于计算投资组合的胜率（Win Rate），这是一种评估投资组合绩效的指标。它是投资组合中获胜交易（即，产生正回报的交易）的数量占所有交易数量的比例。
以下是函数的定义和使用方法：

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- aggregate：这是一个可选参数，用于指定聚合方法。例如，你可以选择按月或按年来计算胜率。
- compounded：这是一个布尔值，决定是否需要复合收益率。如果为True，函数将使用复合收益率来计算胜率。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

函数的返回值是一个数值，代表投资组合的胜率。这个数值可以帮助投资者和资产管理者评估投资策略的有效性。
### 69. worst(returns, aggregate=None, compounded=True, prepare_returns=True)
worst 函数用于计算投资组合在指定时间段内的最糟糕回报。这是一种评估投资组合性能的指标，它可以帮助投资者和资产管理者了解投资组合在最不利的情况下可能遭受的损失。

以下是函数的定义和使用方法：

- returns：这是一个数组或序列，代表你的投资组合或资产的回报率。这个数据可以是价格数据，也可以是已经计算好的回报率数据。
- aggregate：这是一个可选参数，用于指定聚合方法。例如，你可以选择按日、月、季度或年来计算最糟糕的回报。
- compounded：这是一个布尔值，决定是否需要复合收益率。如果为True，函数将使用复合收益率来计算最糟糕的回报。
- prepare_returns：这是一个布尔值，用于决定是否需要对回报率数据进行预处理。预处理包括将回报率数据转换为适合计算的格式，例如将价格数据转换为回报率数据。如果设置为True，那么函数会进行预处理；如果设置为False，那么函数将直接使用输入的回报率数据。

函数的返回值是一个数值，代表投资组合在指定时间段内的最糟糕回报。这个数值可以帮助投资者和资产管理者评估投资组合的风险。
（完）