# 2.4 保证金账户的运作

如果两个投资者通过直接接触而同意在将来某时刻按约定的价格交易某一资产，很明显这笔交易存在风险：投资者的一方可能对该交易感到后悔并想退出交易。另外，投资者也可能没有财力来履行承诺。交易所的一个关键职责是组织交易以避免发生违约，这正是设定保证金账户的目的。

## 2.4.1 每日结算

为了说明保证金的运作方式，我们假定一位投资者在某天与经纪人联系，准备买入两份CME集团的纽约商品交易所COMEX分所12月到期的黄金期货合约。我们假定期货合约的当时价格为每盎司1750美元，由于合约的规模为100盎司黄金，所以投资者建立了以这一价格买入200盎司黄金的合约。经纪人会要求投资者将一定数量的资金存入保证金账户(margin account)之中。投资者在最初开仓交易时必须存入的资金量叫初始保证金(initial margin)。我们假定每份合约的初始保证金为6000美元，因此保证金总共为12000美元。在每个交易日结束时，保证金账户的金额数量都会得到调整，从而反映投资者的盈亏。这种做法叫每日结算(daily settlement)或叫作按市场定价(marking to market)。

例如，假设在第1个交易日结束时，期货价格跌了9美元，即从1750美元跌至1741美元。投资者的损失为1800(=200×9)美元，因为投资者约定要以1750美元的价格买入的200盎司的12月黄金，现在仅能以1741美元出售。因此保证金账户中的金额要减少1800美元，保证金减至10200美元。类似地，如果12月期货价格在第一个交易日结束时上涨到1759美元，保证金账户的金额将会增加1800美元，保证金增至13800美元。一笔交易首先以达成交易这一天闭市时的市场价格来结算，在随后的交易日，这笔交易都要以当天闭市时的市场价格来结算。

每日结算导致资金在持有多头头寸和空头头寸的投资者之间流动。如果从一天到下一天，期货价格上涨，资金就会从持有空头头寸的投资者流向持有多头头寸的投资者。如果期货价格下跌，资金就会向反方向流动，即从持有多头头寸的投资者流向持有空头头寸的投资者。这种投资者之间的每日资金流动可以反映收益和损失，被称为变动保证金(variation margin)。

大多数个人必须联系经纪人进行交易。他们需要受到维持保证金(maintenance margin)的限制，维持保证金会低于初始保证金数量。当保证金账户的余额低于维持保证金水平时，投资者会收到保证金催付(margin call)通知：短时间内投资者需要将保证金账户内的资金增加到初始保证金水平，这一部分增加的资金被称为追加保证金(variation margin)。当投资者不能提供追加保证金时，经纪人将对合约平仓。在以上例子中，可以通过卖出12月交割200盎司黄金的合约对现有合约进行平仓。

如果投资者持有的合约价值增加，保证金账户中的余额也会增加。投资者可以提取保证金账户中超过初始保证金的部分。

表2-1说明了上例中投资者保证金账户随期货价格变动的例子。假设维持保证金为每份合约4500美元，即总共9000美元。在交易的第7天，保证金账户的余额比维持保证金低1020美元。这时，经纪人通知客户需要追加4020美元保证金来使保证金达到最初12000美元的水平。我们假设投资者确实在第8天收盘之前提供了这一保证金。在交易的第11天，保证金账户中的余额又低于维持保证金的水平，这时经纪人又会发出追加3780美元的通知。投资者在第12天收盘之前又提供了保证金。在第16天，投资者决定通过卖出两个合约来对交易进行平仓。这一天合约的价格为1726.90美元，投资者累计损失为4620美元。注意在第8，13，14，15天投资者的保证金账户余额超出了初始保证金数量。在表2-1中，我们假设投资者没有提取多余资金。

![](images/2024-02-20-10-51-32.png)

![](images/2024-02-20-10-51-51.png)

大多数经纪人向投资者保证金账户中的余额支付利息。如果保证金账户提供的利率与通过其他途径所获得的利率相比具有一定的竞争性，那么这一账户中的余额并不能算是真正的费用。为了满足初始保证金（而不是后来的追加保证金）要求，投资者有时可以将有价证券存放在经纪人那里。通常短期国债可以按其面值的90%代替现金。有时股票也可以代替现金，但只能为其市值的50%。

对于远期合约，只有在最后到期时才会进行结算，而期货合约却每天都需要结算。在每个交易日结束时，投资者的盈利（亏损）会被加入其保证金账户（从保证金中扣除），从而使得期货合约的价值变为0。这相当于期货合约每天都要进行一次平仓，然后又以新价格开仓。

对于期货合约，交易所清算中心会设定初始保证金和维持保证金的最低要求。经纪人要求客户存放的保证金可能会比交易所清算中心规定的要高。保证金的最低数量是根据标的资产价格的变化程度来决定的，并且在需要时会加以调整。资产价格变化程度越大，保证金水平也越高。维持保证金通常为初始保证金的75%。

注意对于期货空头方的保证金要求与对期货多头方的保证金要求是一样的。承约期货空头方与承约期货多头方一样容易，而在即期市场上则不具备这种对称性：持有即期市场的多头会涉及购买资产并立即支付，这不存在任何问题，而持有即期空头则是卖出一种你不拥有的资产，这是一种比较复杂的交易，在某些市场上可能做不到这一点。在第5章我们将仔细讨论这个问题。

## 2.4.2 清算中心

与其会员在期货交易中，清算中心(clearing house)起着中介的作用，它保证交易双方会履行合约。清算中心拥有一定数量的结算会员，不是清算中心会员的经纪人必须通过会员来开展业务，并在会员处注入保证金。清算中心的主要任务是记录每天的交易，以便计算每一个会员的净头寸。

清算中心要求会员提供初始保证金（有时也被称作结算保证金(clearing margin)），其数量反映了所要结算合约的总数量。清算中心对会员没有维持保证金的要求。每天结束，会员处理的交易都要经过清算中心来进行结算。如果会员处理的交易总和出现了亏损，会员需要向交易所清算中心提供追加保证金；如果交易总和出现了盈余，会员将从交易所清算中心收到变动保证金。当价格或头寸有剧烈变化时，清算中心也许会向会员要求日内(intraday)追加保证金；如果不能满足保证金要求，会员将被清算出场。

在计算保证金时，未平仓合约的数量一般是按净持仓来计算的，这意味着在合约总数的计算过程中，会员持有的空头合约数量会抵消该会员所持有的多头合约数量。假定某清算中心的会员共有两个客户：一个客户持有20份合约的多头，另一个客户持有15份合约的空头，这时最初保证金数量的计算是基于5份合约的。通常在保证金计算方法的设计上，清算中心要做到99%确定，在某会员违约而被清算出场的情况下，保证金要足够填补损失。清算中心会员需要向清算中心提供担保基金(guaranty fund)。当会员需要提供追加保证金却没能做到时，担保基金可以用来填补将会员的头寸平仓时所出现的亏损。

## 2.4.3 信用风险

保证金体系的目的是保证当交易员赚钱时能够有足够的资金用来支付给交易员。从整体上来讲，这一系统十分成功。在大型交易所里，还没有出现过对交易员所做的交易没有兑现的情况。1987年10月19日期货市场曾经承受过考验：在这一天里标准普尔500指数下跌幅度超过20%，持有标准普尔500指数多头方的交易员发现自己保证金账户的余额成了负数，不能满足保证金催付要求的交易员的交易被平仓，且这些交易员仍然欠经纪人的钱。有些人没有支付欠款，从而使一些经纪人破产，原因是在没有拿到客户资金时，经纪人无法满足代表客户持有的合约的保证金催付要求。即使这样，交易所仍有足够多的资金去支付持有标准普尔500指数期货空头方的客户。