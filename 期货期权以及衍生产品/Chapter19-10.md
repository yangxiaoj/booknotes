# 19.10 对冲的现实性

在一个理想世界里，金融机构的交易员可以随时调整对冲交易以确保投资组合的所有希腊值均为0。但在现实生活中这样做是不可能的。在管理依赖于某个单一资产的交易组合时，为了确保交易组合的delta为0或接近于0，交易员通常是至少每天都重新平衡一次组合。不幸的是，由于在市场上很难找到价格合理并且适量的期权或其他非线性产品，保证gamma与vega为0就没有那么容易。业界事例19-1讨论了在金融机构里动态对冲是如何进行的。


对于期权交易而言，这里存在一个很大的规模经济问题：从经济上讲，为一个资产上的少量期权每天维持delta中性往往是不现实的，这是因为对冲各个期权的交易费用很高。但是，对于衍生产品交易商来讲，保持某一个资产上很大的交易组合delta中性就变得切实可行，这时对冲每份期权的交易费用会变得比较合理。

## 业界事例19-1

## 实践中的动态对冲

一家金融机构一般指定某一交易员或某一个交易组来负责管理与某一特定资产有关的期权交易组合。例如，高盛公司的某一交易员可能被指定负责与澳元有关的所有衍生产品交易组合。交易组合的市价和有关的希腊值均通过计算机系统来产生。对应于每一项风险都会设定不同的风险额度，如果交易员的交易量在交易日结束时超过额度，他必须得到特殊批准。


delta额度的表达形式通常是对应于标的资产的最大交易量。例如，假设高盛公司关于微软股票的delta额度为100万美元。假如微软股价为50美元，这意味着对应的delta绝对值数量不能超过20000。vega的交易额度通常表达为当标的价格波动率变化1%时所对应价值变化的最大限量。


事实上，交易员在每天交易日结束时会保证交易组合delta中性或接近中性。gamma和vega会得到监控，但这些风险量并不是每天都得到调整。金融机构常常发现自己因业务需要而向客户卖出期权，天长日久自己会积累负的gamma与vega。因此金融机构往往会寻求适当的机会以合适的价格买入期权来中和自己所面临的gamma与vega风险。


期权组合的一个特征会从某种意义上减轻管理gamma和vega的负担：当期权刚刚卖出时，期权一般为平值（或很接近平值），而此时期权的gamma和vega会很大。但随着时间的流逝，当标的资产价格变化足够大后，期权会变成实值或虚值期权，此时期权的gamma和vega会很小，从而对交易组合的影响很小。当一个期权接近到期而且标的资产价格与执行价格较为接近时进行，对冲是让交易员最头痛的事。