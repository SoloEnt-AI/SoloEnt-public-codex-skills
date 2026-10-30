# SoloEnt public Codex skills

SoloEnt 面向 Codex 用户的公开技能合集。每个 skill 放在独立文件夹，按需下载安装即可。

## 技能目录

| Skill | 适合谁 | 使用场景 | 依赖 |
| --- | --- | --- | --- |
| [SoloEnt 出海选题](skills/soloent-overseas-topic-advisor/) | 想写英文男频网文的新人、准备出海的中文作者、研究海外题材的编辑与策划 | 选择海外男频题材、判断 Webnovel / Royal Road 适配、寻找参考作品、研究中文网文英译表现 | Codex + 已连接并授权的 SoloEnt MCP |
| [人人能写五分钟剧本](skills/everyone-can-write-5min-scripts/) | 零基础创作者、短视频作者、编剧及短片制作团队 | 从灵感写成五分钟剧本、改稿、检查节奏和冲突、定稿转分镜 | Codex，无额外 MCP 依赖 |

## 下载与安装

1. 点击本仓库 **Code → Download ZIP**，解压；或克隆本仓库。
2. 找到 `skills/` 下需要的技能文件夹，将整个文件夹复制到下面任一目录：
   - 个人使用：`~/.codex/skills/`
   - 项目使用：项目根目录的 `.agents/skills/`
3. 保留文件夹内的 `SKILL.md` 和 `agents/` 等结构。下一轮对话中使用该技能。

例如，安装后的文件结构为：

```text
~/.codex/skills/
└── soloent-overseas-topic-advisor/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
```

也可以在 Codex 中说：

> 请从 https://github.com/SoloEnt-AI/SoloEnt-public-codex-skills 安装 skills/soloent-overseas-topic-advisor 技能。

更新时，用仓库中的新版本替换对应技能文件夹；若有个人修改，请先备份。

## SoloEnt 出海选题

### 适用用户与场景

- **刚准备出海的作者**：根据经验、擅长题材和英文产出方式，找到适合的方向。
- **已有中文写作经验的作者**：参考中文网文英译表现，判断现有题材如何面向海外读者。
- **准备写 Webnovel 或 Royal Road 的作者**：筛选标签、比较平台适配、寻找可拆解的参考作品。
- **编辑与内容策划**：了解海外男频的主要风向，整理候选题材和作品卖点。

技能以 Webnovel 与 Royal Road 作为海外男频风向的主要参考，结合作者条件给出首选、备选、参考作品和落地建议。

### 使用前准备

需要在自己的 Codex 中连接并授权 **SoloEnt MCP**，并确保以下工具可用：

- `insight_advisor_intl_sites`
- `insight_advisor_intl_tags`
- `insight_advisor_intl_tag`

实际工具名称可能带有服务前缀。MCP 连接和授权需单独完成；下载本仓库不会自动配置数据服务。本仓库不包含服务凭据或市场数据库，不需要把密钥写入技能文件。

### 如何调用

直接输入 `$soloent-overseas-topic-advisor`，或用自然语言描述需求：

> 用 SoloEnt 出海选题帮我选题。我写过中文系统升级流，准备先中文创作再翻译，每天能更新一章，想找适合海外读者的方向。

> 我更想写 Royal Road，擅长硬设定和成长机制，帮我推荐三个方向及参考作品。

> 看看中文网文英译作品里，哪些题材表现较好，找几本参考书。

### 你会得到什么

结合市场数据与个人条件的题材建议、站点适配判断、代表作品和具体研究点；确定方向后，可整理成继续创作的选题摘要。技能只查询数据，不在平台发布作品，也不保证新书成绩。正文与开篇评价需有额外阅读证据。

## 人人能写五分钟剧本

### 适用用户与场景

- **零基础创作者**：通过一轮一个关键问题，逐步找到故事、人物和结尾。
- **短视频作者与独立短片创作者**：把脑洞、生活素材或人物关系变成约五分钟的完整故事。
- **已有草稿的编剧**：直接检查开场、冲突、结尾和预计时长，修改薄弱段落。
- **制作团队**：把已完成的剧本转成带画面、动作、台词和音效的分镜。

### 如何使用

按照上方安装步骤，将 `skills/everyone-can-write-5min-scripts/` 整个文件夹复制到技能目录，保留 `references/` 和 `agents/`。本技能不依赖额外 MCP 或付费数据接口。

调用 `$everyone-can-write-5min-scripts`，也可以直接说：

> 用人人能写五分钟剧本带我写一个家庭题材的短片。我没有编剧经验，希望一步步讨论。

> 我想写一个失忆机器人回家找母亲的故事，请直接给我约五分钟的完整剧本，人物不超过三人、主要场景只有一个。

> 帮我修改这份短剧，重点检查冲突是否可信、结尾是否有余味，并估算表演时长。

### 你会得到什么

按任务需要交付故事锚定卡、够用的角色与设定、四幕大纲、正式剧本及审稿修改建议；需要时再转为分镜。既可以逐步陪写，也可以直接生成完整初稿，或从已有材料开始改稿。

真人、AI 真人、动画及横竖屏均可按需要选择。时长以对白与动作估算、朗读或试演校准，不用固定字数冒充五分钟。技能提供文字创作与制作规划，不生成视频、不替用户发布。

## 仓库结构

```text
skills/
├── soloent-overseas-topic-advisor/   # SoloEnt 出海选题
│   ├── SKILL.md
│   └── agents/openai.yaml
└── everyone-can-write-5min-scripts/  # 人人能写五分钟剧本
    ├── SKILL.md
    ├── references/                 # 题材、结构、格式与审稿参考
    └── agents/openai.yaml
```

后续技能继续以 `skills/<skill-name>/` 独立存放，并在上方目录说明适用用户、场景与依赖。
