# 1.9 套利者

套利者是期货、远期以及期权市场的第3种重要参与者。套利包括同时进行两种或更多的交易来锁定无风险收益。在后面的章节中，我们将会论述当某一个资产的期货价格与其即期市场价格不协调时，如何产生套利机会。我们也将描述如何在期权市场中套利。在这一节里，我们用一个简单的例子来说明套利的概念。

我们考虑在纽约交易所(New York Stock Exchange, NYSE, www.nyse.com)和伦敦股票交易所(London Stock Exchange, LSE, www.londonstockexchange.com)均有交易的某一股票。假定这一股票在纽约的价格为120美元，同时在伦敦的价格为100英镑，相应的汇率为每英镑1.23美元。一个套利者可以在纽约买入100股股票并同时在伦敦将股票卖出，其无风险收益为

```python 

100×[(1.23×100)-120]

```

即300美元（计算忽略了交易费用）。交易费用的存在可能会消除小投资者的盈利。但是，大型投资银行在股票市场以及外汇市场的交易费用都很低，所以投资银行会发现这一套利机会很诱人，它们会试图从中获利。

以上描述的套利机会不会持续太久。随着套利者在纽约买入股票，供需关系会使股票的美元价格上涨。类似地，随着套利者在伦敦卖出股票，供需关系会使股票的英镑价格下跌。市场很快会使两个价格在当前汇率下趋于平衡。事实上，套利者对于套利的急切渴望使得股票的美元价格以及英镑价格之间不可能存在如此严重的失衡。将此例推广，我们可以讲正是由于套利者的存在，才使得在实际中的大多数金融市场报价中只会存在很小的套利机会。在本书中，大多数关于期货、远期和期权价格的讨论都建立在无套利机会的假设之上。