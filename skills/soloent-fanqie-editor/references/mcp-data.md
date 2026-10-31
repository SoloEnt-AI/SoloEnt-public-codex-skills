# MCP 取数与频道路由

## 已确认的工具

| 用途 | 当前完整工具名 | 参数 |
| --- | --- | --- |
| 查询可用站点、成绩和日期定义 | `mcp__soloent__soloent_insight__insight_sites` | `{}` |
| 查询标签排名、作品数、市场参考分和已发布介绍 | `mcp__soloent__soloent_insight__insight_reference_tags` | `site`, 可选 `window` |

实际名称可能带其他前缀，以运行环境的工具 schema 为准。

已通过实际调用确认：站点列表包含 `fanqie`（番茄男频）与 `fanqie_f`（番茄女频），成绩为在读，日期为首章日期。`insight_reference_tags` 支持两者，返回 `site`、`window`、`generated_at`、`total`、`tags`，标签包含 `ranking`、`tag`、`work_count`、`market_score`、已发布的 `writing_advice.标签介绍`。使用时仍以当次响应为准，不把本说明当成永久服务保证。

## 最小调用流程

1. 首次任务查询 `insight_sites`，确认目标频道当前可用；同一任务可复用已确认结果。
2. 调用 `insight_reference_tags`：男频 `site="fanqie"`，女频 `site="fanqie_f"`，默认 `window="6m"`。用户指定时间范围时遵从服务实际支持范围，不杜撰参数。
3. 对照核心故事和介绍选主标签，必要时列少量备选。不得因词面相似就判命中，不为每个叠加标签重复计分。
4. 记录实际来源、所用频道与范围；存在 `generated_at` 时作为数据生成日期，查询日期另记。

## 额外工具边界

`insight_advisor_cn_tags` 与 `insight_advisor_cn_tag` 当前 schema 只接受 `qidian` 或 `fanqie`，不是女频工具。不能向它们强传 `fanqie_f`，也不能把男频榜或作品冒充女频样本。

男频确需补充成绩统计、分类、完整建议或代表作品时，可用 `insight_advisor_cn_tag(site="fanqie", tag=实际标签, window="6m", limit=10)`；需要近期榜单时用 `insight_advisor_cn_tags(site="fanqie")`。默认审稿不必额外抓全榜。

女频参考工具未返回代表作品、详细成绩或完整写作建议时，就不声称已获取。将来如有专用女频工具，先发现并核实 schema 和返回频道，再使用；不可自行猜测工具名或 REST 地址。

## 数据与评分

`market_score` 与 `potential_score` 不互换，参考分不是官方签约标准或成功概率。不能以两个频道的分数大小认定某频道更好写或更容易赚钱。标签作品数是覆盖样本，不是完整平台竞争规模；小样本时谨慎，缺失字段不补造。

没有对应标签或介绍时可讨论文本卖点，但不把“未覆盖”判为没有市场。无足够市场证据时平台项待评，仍可做正文四维诊断。

查询失败时，参数错误按 schema 修正；权限或连接问题简要说明影响，不反复重试，不回退静态标签表、不索要聊天明文密钥。平台当前投稿规则、签约门槛或分发算法不能从该数据推导；确需确认时查平台官方来源。
