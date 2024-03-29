# 10.4 股票期权的细节

在本章的以下内容里我们将着重讨论股票期权。前面讲过，美国交易所内的股票期权为可以购买或出售100股股票的美式期权。关于合约的细节，例如，到期日、执行价格、股息处理方式、投资者的头寸限额等均由交易所来确定。

## 10.4.1 到期日

用于描述股票期权的参数之一是到期日所在的月份。因此1月IBM看涨期权的到期日为1月的某一天。精确地讲，到期日为到期月份的第3个星期五，在到期日前的每一个营业日（芝加哥时间上午8:30到下午3:00）都可以对期权进行交易。

美国的股票期权是在1月、2月或3月的循环期上进行交易。1月循环期包括1月、4月、7月和10月；2月循环期包括2月、5月、8月和11月；3月循环期包括3月、6月、9月和12月。如果本月份的到期日尚未来到，交易的期权包括在当月到期的期权、下个月到期的期权和当前月循环期中下两个到期月的期权；如果当月的到期日已过，交易期权包括下个月到期的期权，再下一个月到期的期权以及这一个月循环期中下两个到期月的期权。例如，假定IBM股票期权处在1月循环期中。在1月初，该股票期权的到期月份为1月、2月、4月和7月；在1月末，该股票期权的到期月份为2月、3月、4月和7月；在5月初，该股票期权的到期月份为5月、6月、7月和10月等。当一个期权到期后，另一个期权交易随即开始。如果市场对一家公司有很大兴趣，这家公司的期权也可能会在其他月交易。另外，有些期权在每个星期五到期，而不是1个月的第3个星期五，这种期权有时称为单周期权(weekly)。

美国的交易所交易许多家股票上的长期限的期权，这类期权叫作LEAPS（长期资产预期证券，long-term equity anticipation security）。这些期权的期限可能会长达39个月，LEAPS的到期日总是在1月的第3个星期五。

## 10.4.2 执行价格

交易所在选择能够交易的期权的执行价格时，一般会使价格的间隔为2.5美元、5美元、10美元。通常的做法是当股票价格介于5美元与25美元之间时，执行价格的间隔为2.5美元；当股票价格介于25美元与200美元之间时，执行价格的间隔为5美元；当股票价格高于200美元时，执行价格的间隔为10美元。在下面我们将会解释股票分股和股息均会造成非标准的执行价格。

## 10.4.3 术语

对于任何资产，在任何给定的时刻，市场上都可能有许多不同的期权在进行交易。考虑某只股票，其上有4个到期日和5个不同执行价格的期权。如果对于每个到期日与执行价格均有相应的看涨期权与看跌期权交易，这样就会有40种不同的期权合约。所有类型相同的期权（看涨或看跌）都可以归为一个期权类(option class)。例如，IBM的看涨期权为一类，IBM的看跌期权为另一类。一个期权系列(option series)是具有相同到期日与不同执行价格的某个给定类型的所有期权。换句话讲，期权系列是指市场交易中某个特定的合约。例如，IBM 160 2021年10月看涨期权是一个期权系列。

期权可分为实值期权(in-the-money option)、平值期权(at-the-money option)、虚值期权(out-of-the-money option)。如果S为股票价格，K为执行价格，对于看涨期权，当S＞K时为实值期权，当S=K时为平值期权，而当S＜K时为虚值期权。对于看跌期权，当S＜K时为实值期权，当S=K时为平值期权，而当S＞K时为虚值期权。显然，只有在期权为实值期权时才会被行使。没有交易费用的前提下，没有被提前行使的实值期权在到期时肯定会被行使。


期权的内含价值(intrinsic value)定义为如果期权立即被行使时所具有的价值。看涨期权的内含价值为max(S-K,0)，看跌期权的内含价值为max(K-S,0)。实值美式期权的价值至少等于其内含价值，因为该期权持有者可以通过马上行使期权来实现其内含价值。通常一个实值美式期权的持有者最优的做法是等待而不是立即执行期权，这时期权称为具有时间价值(time value)。期权的总价值等于内含价值与时间价值之和。

## 10.4.4 灵活期权

芝加哥期权交易所提供股票和股指的灵活期权(FLEX option)，这种期权具有交易员之间认可的一些非标准条款。这种期权的非标准条款里的到期日或执行价格和场内交易的期权有所不同，结算方式（美式或欧式）也可以灵活定制。灵活期权是期权交易所试图从场外市场争夺客户的一种尝试。交易所会注明灵活期权交易的最小规模（比如100份合约）。

## 10.4.5 股息和股票分股

早期的场外期权受到股息保护。如果一家公司发放现金股息，公司股票期权的执行价格会在除息日减去股息金额。而交易所交易的期权不受股息保护。换句话讲，当公司发放现金股息时，期权中的条款不做任何调整。大额现金股息是例外。当公司宣布股息高于股票价格10%时，CBOE的期权清算公司将决定如何对看涨期权与看跌期权进行调整。通常的做法是按股息量下调执行价格。

当股票分股时，交易所交易的期权要进行调整。股票进行分股时，现存的股票被分割成更多的股票。例如，在股票3对1(3-for-1)分股时，3股新发行的股票将代替原来的1股股票。因为股票分股不改变公司的资产与盈利能力，因此我们不应该期望分股会影响公司股东的财富。在其他条件不变的情况下，3对1股票分股会使得分股后的股票价格等于分股前价格的1/3。一般来讲，n对m股票分股会使得股票价格下跌为分股前价格的m/n。期权中的条款会有所调整以便反映因分股而造成的价格变化。在n对m股票分股时，期权的执行价格也变为分股前执行价格的m/n倍，每一份期权合约所涉及的股票数量为初始期权所涉及股票数量的n/m倍。如果股票价格按所预料的那样下跌，期权承约方与买入方的头寸都保持不变。

【例10-1】 考虑可以让持有者以每股30美元的价格买入100股股票的看涨期权。假定公司进行了2对1股票分股，期权合约的条款将变为持有者有权以每股15美元的价格买入200股股票。

股票期权也对股票股息进行调整。股票股息可以是公司向其股东分发更多的股票。例如，20%的股票股息是指股东每拥有5股原公司股票就会收到1股新股票。同股票分股类似，发放股票股息对公司的资产与盈利均无影响。在公司发放股票股息后，可以预计公司的股票价格会有所下降。20%的股票股息基本上等价于6对5股票分股。在其他条件不变的情况下，这一股票股息会造成股价下跌到发放股票股息前价格的5/6。与股票分股类似，这时期权合约中的条款会有所调整，以便反映股票股息所带来的股票价格变化。

【例10-2】 考虑可以让持有者以每股15美元的价格出售100股股票的看跌期权。假定公司发放25%股票股息，这等价于5对4的股票分股。期权合约的条款将会变成持有者有权以12美元的价格出售125股股票。

对于优先权证(rights issues)，期权条款也会加以调整。基本的调整方法是首先计算权证的理论价格，然后从执行价格中减去这一数量。

## 10.4.6 头寸限额与行使限额


芝加哥期权交易所常常指定期权合同的头寸限额(position limit)。这些限额是一个投资者在市场的一方中可持有期权合约的最大数量，这时看涨期权的多头和看跌期权的空头被认为是市场的同一方。同样，看涨期权的空头与看跌期权的多头也被看作市场的同一方。行使限额(exercise limit)通常与头寸限额相同，它规定了任何投资个人（或者投资群体）在5个连续交易日中可以行使期权合约的最大额度。对于市场上最大与交易最频繁的股票期权头寸限额为250000份合约。市场规模较小的股票期权头寸限额可以是200000、75000、50000与25000份合约不等。


虽然头寸限额与行使限额的设定是为了防止某些个人或群体操纵市场，但是人们对于这些额度的设定是否有必要仍有争议。