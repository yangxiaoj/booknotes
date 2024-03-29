# 20.4 其他刻画波动率微笑的方法


有许多不同的方式可以用来刻画波动率微笑。有时我们将其作为隐含波动率与执行价格之间的关系。然而这种关系依赖资产的当前价格：当资产价格上涨（下跌）时，描述平值期权的执行价格也会上涨（下降），从而描述隐含波动率与执行价格的曲线会向右（左）移动。[插图]正是由于这个原因，波动率微笑常常定义为隐含波动率与执行价格除以当前资产价(K/S0)之间的关系。

图20-1与图20-3中展示的就是这种关系。对这种描述方式的一种改进是将波动率微笑定义为隐含波动率与K/F0之间的关系，其中F0是具有与所考虑期权相同期限的远期价格。交易员也经常将平值期权定义为对应K=F0，而不是K=S0的期权。这样做的原因是F0（而非S0）为在风险中性世界中股票在期权到期时价格的期望值。

还有一种方式是将波动率微笑定义为隐含波动率与期权delta之间的关系（在第19章中定义了delta）。利用这种方式，我们有时可以将波动率微笑应用于欧式和美式看涨与看跌期权之外的其他产品上。当应用这种方法时，我们将平值期权定义为delta等于0.5的看涨期权，或delta等于-0.5的看跌期权。这些平值期权称为“50-delta期权”(50-delta option)。