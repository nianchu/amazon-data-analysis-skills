# Output contract

## Worksheet: 源数据

Keep all original columns, then append:

- 标准化关键词
- 来源ASIN
- 来源产品层
- 来源类型
- 来源文件
- 来源工作表
- 来源行号
- 正式产品池匹配状态
- 产品相关性状态
- 排除原因
- 关键词主分类
- 搜索意图
- 数据缺失标记

Do not overwrite source measurements.

## Worksheet: 关键词排序

Recommended columns:

- 排名
- 原关键词代表值
- 标准化关键词
- 关键词主分类
- 搜索意图
- 覆盖ASIN数
- 覆盖ASIN占比
- 加权销量覆盖率
- 自然词证据
- 广告词证据
- 搜索量
- 购买量
- 转化率
- 高转化优先级
- 转化证据类型
- CPC
- 竞品数
- 标题密度
- SPR
- 趋势
- 相关性得分
- 需求得分
- 转化证据得分
- 竞争可切入得分
- 市场覆盖得分
- 出价效率得分
- 综合机会分
- 置信等级
- 自然位策略
- 广告位策略
- 建议匹配方式
- 否定词候选
- 计算逻辑/备注

Use blank cells or explicit `N/A` for unavailable metrics. Never render unknown as numeric zero.

## Delivery notes

State:

- Formal-pool version and selected ASIN layers.
- Source files and observation periods.
- Raw and unique row counts.
- Deduplication and normalization rules.
- Ranking weights and deviations from defaults.
- Coverage conclusion and unresolved gaps.
- Recommended next data batch.
- Marketplace, language, CPC currency, and any localization assumptions.
