# 从零学量化58：QuantStats库之可视化分析中文指南（五）
## 三、quantstats.reports 函数介绍
### 1. metrics
metrics函数是quantstats.reports库中的一个函数，该函数用于批量计算并返回金融投资组合的各种统计指标。这个函数的参数定义如下：
```python 

metrics(returns, benchmark=None, rf=0.0, display=True, mode='basic', sep=False, compounded=True, periods_per_year=252, prepare_returns=True, match_dates=True, **kwargs)

```
- returns: 投资组合的收益率，可以是Pandas Series或单列DataFrame。
- benchmark: 基准收益率，可以是Pandas Series或一个字符串表示的基准名称。
- rf: 无风险收益率，默认为0.0。
- display: 是否将结果打印到控制台，默认为True。
- mode: 指定输出的详细级别，可以是'basic'或'full'，默认为'basic'。
- sep: 是否在输出中包括空行，默认为False。
- compounded: 是否使用复利计算，默认为True。
- periods_per_year: 每年的交易周期数，默认为252（代表一年中大约有252个交易日）。
- prepare_returns: 是否需要对收益率进行预处理，默认为True。
- match_dates: 是否需要将收益率和基准的日期对齐，默认为True。
- **kwargs: 其他参数。

当mode='basic'时，该函数会返回以下的基本统计指标：

- 开始和结束日期
- 无风险收益率
- 在市场中的时间百分比
- 累积收益率或总收益率
- CAGR (复合年化增长率)
- Sharpe比率和概率Sharpe比率
- Sortino比率
- Sortino/√2
- Omega比率
- 最大回撤百分比和最长回撤天数
- Gain/Pain比率
- Payoff比率，Profit因子，常识比率，CPC指数，Tail比率，异常赢率，异常亏损率
- 最近的月收益率，3个月收益率，6个月收益率，年度收益率，1年收益率，3年复合年化收益率，5年复合年化收益率，10年复合年化收益率，全部时间复合年化收益率
- 回撤指标，如恢复因子，溃疡指数，宁静指数

当mode='full'时，该函数会返回以上所有基本指标，再加上以下的高级统计指标：

- Smart Sharpe比率，Smart Sortino比率，Smart Sortino/√2
- 年化波动率，R^2，信息比率
- Calmar比率，偏度，峰度
- 预期的每日、每月和每年收益率，Kelly准则，破产风险
- 每日价值在风险，预期短缺（cVaR）
- 最大连续赢次数，最大连续亏损次数
- 最好和最差的日收益率，月收益率，年收益率
- 平均上涨月份百分比，平均下跌月份百分比，获胜日百分比，获胜月百分比，获胜季度百分比，获胜年份百分比
- Beta，Alpha，相关性，Treynor比率

这个函数返回一个Pandas DataFrame，每行对应一个指标，每列对应一个投资策略或基准。如果display=True，那么这个函数会将结果打印到控制台，并返回None。
### 2. plots
plots函数是quantstats.reports库中的一个函数，该函数用于绘制金融投资组合的各种统计图表。这个函数的参数定义如下：

```python 

plots(returns, benchmark=None, grayscale=False, figsize=(8, 5), mode='basic', compounded=True, periods_per_year=252, prepare_returns=True, match_dates=True, **kwargs)

```
- returns: 投资组合的收益率，可以是Pandas Series或DataFrame。
- benchmark: 基准收益率，可以是Pandas Series或一个字符串表示的基准名称。
- grayscale: 是否以灰度模式绘制图形，默认为False。
- figsize: 图形的大小，默认为(8, 5)。
- mode: 指定输出的详细级别，可以是'basic'或'full'，默认为'basic'。
- compounded: 是否使用复利计算，默认为True。
- periods_per_year: 每年的交易周期数，默认为252（代表一年中大约有252个交易日）。
- prepare_returns: 是否需要对收益率进行预处理，默认为True。
- match_dates: 是否需要将收益率和基准的日期对齐，默认为True。
- **kwargs: 其他参数。

当mode='basic'时，该函数会输出以下的基本图表：

- 收益率图：包括累积收益率，年度收益率和月度收益率。
- 回撤情况图
- 月度热图：显示每个月的收益率。

当mode='full'时，该函数会输出以上所有基本图表，再加上以下的高级统计图表：

- 收益率时间序列图
- 对数收益率时间序列图
- 标准化风险的收益率时间序列图
- 年度收益率条形图
- 收益率直方图
- 每日收益率条形图
- 滚动Beta图
- 滚动波动率图
- 滚动Sharpe比率图
- 滚动Sortino比率图
- 回撤期间图
- 最大回撤图
- 月度收益率热图
- 收益率分布图

这个函数不返回任何值，但会直接在控制台中显示图形。
### 3. basic
basic函数是quantstats.reports库中的一个函数，该函数用于生成投资组合的基本统计报告和相关的数据图表。具体来说，这个函数首先会调用metrics函数计算一些基本的统计指标，然后调用plots函数生成相关的图表。这个函数的参数定义如下：
```python 

basic(returns, benchmark=None, rf=0.0, grayscale=False, figsize=(8, 5), display=True, compounded=True, periods_per_year=252, match_dates=True, **kwargs)

```

- returns: 投资组合的收益率，可以是Pandas Series或DataFrame。
- benchmark: 基准收益率，可以是Pandas Series或一个字符串表示的基准名称。
- rf: 无风险收益率，默认为0.0。
- grayscale: 是否以灰度模式绘制图形，默认为False。
- figsize: 图形的大小，默认为(8, 5)。
- display: 是否将结果打印到控制台，默认为True。
- compounded: 是否使用复利计算，默认为True。
- periods_per_year: 每年的交易周期数，默认为252（代表一年中大约有252个交易日）。
- match_dates: 是否需要将收益率和基准的日期对齐，默认为True。
- **kwargs: 其他参数，可以包括 benchmark_title（基准的标题）和 strategy_title（策略的标题）。

basic函数的输出结果主要分为两部分：

- 投资组合的基本统计指标，这些指标由metrics函数（mode参数设为'basic'）计算并打印到控制台。指标包括开始和结束日期，无风险收益率，收益率的统计描述（如平均值，标准差等），最大回撤，夏普比率，索提诺比率等。
- 投资组合的相关图表，这些图表由plots函数（mode参数设为'basic'）生成并显示在控制台。图表包括收益率时间序列图，收益率分布图，每月收益率热图等。

注意，这个函数不返回任何值，但会直接在控制台中显示结果。如果你想获取这些结果，你应该直接调用metrics函数和plots函数，并把display参数设为False。
### 4. full
full函数是quantstats.reports库中的一个函数，该函数用于生成投资组合的完整统计报告和相关的数据图表。具体来说，这个函数首先会调用metrics函数计算一些高级的统计指标，然后调用plots函数生成相关的图表。这个函数的参数定义如下：
```python 

full(returns, benchmark=None, rf=0.0, grayscale=False, figsize=(8, 5), display=True, compounded=True, periods_per_year=252, match_dates=True, **kwargs)

```

- returns: 投资组合的收益率，可以是Pandas Series或DataFrame。
- benchmark: 基准收益率，可以是Pandas Series或一个字符串表示的基准名称。
- rf: 无风险收益率，默认为0.0。
- grayscale: 是否以灰度模式绘制图形，默认为False。
- figsize: 图形的大小，默认为(8, 5)。
- display: 是否将结果打印到控制台，默认为True。
- compounded: 是否使用复利计算，默认为True。
- periods_per_year: 每年的交易周期数，默认为252（代表一年中大约有252个交易日）。
- match_dates: 是否需要将收益率和基准的日期对齐，默认为True。
- **kwargs: 其他参数，可以包括 benchmark_title（基准的标题）和 strategy_title（策略的标题）。

full函数的输出结果主要分为两部分：

- 投资组合的高级统计指标，这些指标由metrics函数（mode参数设为'full'）计算并打印到控制台。指标包括开始和结束日期，无风险收益率，收益率的统计描述（如平均值，标准差等），最大回撤，夏普比率，索提诺比率，Beta，Alpha等。
- 投资组合的相关图表，这些图表由plots函数（mode参数设为'full'）生成并显示在控制台。图表包括收益率时间序列图，收益率分布图，每月收益率热图，滚动Beta图，滚动波动率图，滚动Sharpe比率图，滚动Sortino比率图，最大回撤图等。此外，full函数还会输出最差的5个回撤期的详细信息，包括回撤开始日期，回撤结束日期，回撤持续的天数，回撤的深度，回撤的恢复时间等。

注意，这个函数不返回任何值，但会直接在控制台中显示结果。如果你想获取这些结果，你应该直接调用metrics函数和plots函数，并把display参数设为False。
### 5. html
html函数是quantstats.reports库中的一个函数，该函数用于生成一个HTML报告，报告中包含投资组合的完整统计指标和相关的数据图表。这个函数的参数定义如下：

```python 

html(returns, benchmark=None, rf=0.0, grayscale=False, title='Strategy Tearsheet', output=None, compounded=True, periods_per_year=252, download_filename='quantstats-tearsheet.html', figfmt='svg', template_path=None, match_dates=True, **kwargs)

```

- returns: 投资组合的收益率，可以是Pandas Series或DataFrame。
- benchmark: 基准收益率，可以是Pandas Series或一个字符串表示的基准名称。
- rf: 无风险收益率，默认为0.0。
- grayscale: 是否以灰度模式绘制图形，默认为False。
- title: 报告的标题，默认为"Strategy Tearsheet"。
- output: 输出文件的路径，如果未指定，将在浏览器中打开HTML报告。
- compounded: 是否使用复利计算，默认为True。
- periods_per_year: 每年的交易周期数，默认为252（代表一年中大约有252个交易日）。
- match_dates: 是否需要将收益率和基准的日期对齐，默认为True。
- download_filename: 下载的HTML文件的名称，默认为"quantstats-tearsheet.html"。
- figfmt: 图形的格式，默认为"svg"。
- template_path: HTML模板的路径，如果未指定，将使用默认的模板。
- **kwargs: 其他参数，可以包括 benchmark_title（基准的标题）和 strategy_title（策略的标题）。

html函数的输出结果是一个HTML报告，报告中包括以下内容：

- 投资组合的高级统计指标，这些指标由metrics函数计算并以表格的形式展示。指标包括开始和结束日期，无风险收益率，收益率的统计描述（如平均值，标准差等），最大回撤，夏普比率，索提诺比率，Beta，Alpha等。
- 投资组合的相关图表，这些图表由plots函数生成并以图形的形式展示。图表包括收益率时间序列图，收益率分布图，每月收益率热图，滚动Beta图，滚动波动率图，滚动Sharpe比率图，滚动Sortino比率图，最大回撤图等。
- 此外，html函数还会输出最差的10个回撤期的详细信息，包括回撤开始日期，回撤结束日期，回撤的深度，回撤的持续时间等。

注意，这个函数不返回任何值，但会生成一个HTML文件。如果参数output被指定，那么HTML文件会被保存到指定的路径；如果output未被指定，并且在Jupyter notebook环境下运行，那么HTML报告将在新的浏览器窗口中打开；如果output未被指定，并且在非Jupyter notebook环境下运行，那么将会抛出一个错误。

（完）
