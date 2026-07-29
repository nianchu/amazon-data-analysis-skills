# Output contract

## Worksheet: 源数据

Keep all original columns, then append:

- 标准化关键词
- 来源ASIN
- 来源类型
- 来源文件
- 来源工作表
- 来源行号
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
- 自然词证据
- 广告词证据
- 搜索量
- 购买量
- 转化率
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

Use blank cells or explicit `N/A` for unavailable metrics according to workbook conventions. Never render unknown as numeric zero.

## Delivery notes

State:

- Source files and observation periods
- Raw and unique row counts
- Deduplication and normalization rules
- Ranking weights and changes from defaults
- Coverage conclusion
- Exclusions and unresolved borderline terms
- Recommended next data batch

