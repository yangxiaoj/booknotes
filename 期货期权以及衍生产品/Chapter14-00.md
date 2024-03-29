# 第14章　维纳过程和伊藤引理

如果一个变量的值以某种不确定的形式随时间变化，我们称这个变量服从某种随机过程(stochastic process)。随机过程可以分为离散时间(discrete time)和连续时间(continuous time)两类：一个离散时间随机过程是指变量值只能在某些确定的时间点上变化，而一个连续时间随机过程(continuous-time stochastic process)是指变量值可以在任何时刻上变化。随机过程也可以分为连续变量(continuous variable)和离散变量(discrete variable)两类。在连续变量过程中，标的变量可以取某一范围内的任何值，而在离散变量过程中，标的变量只能取某些离散值。

在这一章里，我们将建立关于股票价格的连续变量、连续时间的随机过程。其他资产的价格通常也被假设为类似的随机过程。理解这种过程是学习与理解期权和其他更加复杂衍生产品定价的第一步。在这里应当指出的是，在实际中，我们所观察到的股票价格并不服从连续变量、连续时间过程，股票价格的变动为离散形式（例如，价格为美分的倍数），而且我们只有在交易所开盘交易的时间内才能够看到股票价格的变化。但即使如此，在大多数情况下，连续变量、连续时间过程仍是一个有用的模型。

许多人认为连续时间随机过程太复杂，应当把它们统统交给“火箭专家”处理。但事实并非如此。理解这些过程的最大障碍是符号，在这里我们将提供一种循序渐进的方式来帮助读者克服这个障碍，同时我们也将解释一个重要结论，即伊藤引理(Itô's lemma)，对衍生产品定价时这一结果是至关重要的。