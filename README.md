# SoloEnt public Codex skills

SoloEnt 面向 Codex 用户的公开技能合集。每个 skill 放在独立文件夹，按需下载安装即可。

## 技能目录

| Skill | 适合谁 | 使用场景 | 依赖 |
| --- | --- | --- | --- |
| [SoloEnt 出海选题](skills/soloent-overseas-topic-advisor/) | 想写英文男频网文的新人、准备出海的中文作者、研究海外题材的编辑与策划 | 选择海外男频题材、判断 Webnovel / Royal Road 适配、寻找参考作品、研究中文网文英译表现 | Codex + 已连接并授权的 SoloEnt MCP |

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

## 仓库结构

```text
skills/
└── soloent-overseas-topic-advisor/   # SoloEnt 出海选题
    ├── SKILL.md                    # 技能指令
    └── agents/openai.yaml          # Codex 显示名称及依赖声明
```

后续技能继续以 `skills/<skill-name>/` 独立存放，并在上方目录说明适用用户、场景与依赖。
