以下是你提供的英文内容的**中文翻译**：

---

> **注意：** 本仓库包含 Anthropic 为 Claude 实现的技能示例。有关 Agent Skills 标准的信息，请访问 [agentskills.io](http://agentskills.io)。

# 技能 (Skills)

技能是包含指令、脚本和资源的文件夹，Claude 会动态加载这些内容以提升特定任务上的表现。技能教会 Claude 如何以可重复的方式完成特定任务——无论是按照你公司的品牌准则创建文档、使用你组织的特定工作流分析数据，还是自动化处理个人事务。

更多信息请查看：
- [什么是技能？](https://support.claude.com/en/articles/12512176-what-are-skills)
- [在 Claude 中使用技能](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [如何创建自定义技能](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [通过 Agent Skills 为真实世界装备智能体](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

# 关于本仓库

本仓库包含的技能展示了 Claude 技能系统的能力。这些技能涵盖了创意类应用（艺术、音乐、设计）、技术类任务（测试 Web 应用、生成 MCP 服务器）到企业级工作流（沟通、品牌等）。

每个技能都存放在独立的文件夹中，并包含一个 `SKILL.md` 文件，其中含有 Claude 使用的指令和元数据。浏览这些技能，你可以为自己的技能获取灵感，或者理解不同的模式与方法。

本仓库中的许多技能都是开源的（Apache 2.0）。我们还将驱动 [Claude 文档能力](https://www.anthropic.com/news/create-files) 的文档创建与编辑技能以源码形式包含在 [`skills/docx`](./skills/docx)、[`skills/pdf`](./skills/pdf)、[`skills/pptx`](./skills/pptx) 和 [`skills/xlsx`](./skills/xlsx) 子文件夹中。这些技能是源码可用（source-available）而非开源的，但我们希望将这些技能分享给开发者，作为在生产级 AI 应用中实际使用的复杂技能的参考。

## 免责声明

**这些技能仅用于演示和教育目的。** 尽管其中部分功能可能在 Claude 中可用，但您从 Claude 获得的实现和行为可能与这些技能中展示的不同。这些技能旨在说明模式和可能性。在依赖这些技能处理关键任务之前，请始终在您自己的环境中对其进行充分测试。

# 技能集合
- [./skills](./skills)：技能示例，涵盖创意与设计、开发与技术、企业与沟通以及文档技能
- [./spec](./spec)：Agent Skills 规范
- [./template](./template)：技能模板

# 在 Claude Code、Claude.ai 和 API 中试用

## Claude Code
你可以通过运行以下命令，将此仓库注册为 Claude Code 插件市场：
```
/plugin marketplace add anthropics/skills
```

然后，要安装特定的技能集合：
1. 选择 `Browse and install plugins`
2. 选择 `anthropic-agent-skills`
3. 选择 `document-skills` 或 `example-skills`
4. 选择 `Install now`

或者，直接通过以下命令安装任一插件：
```
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

安装插件后，你只需提及该技能即可使用。例如，如果你从市场安装了 `document-skills` 插件，你可以对 Claude Code 说：“使用 PDF 技能提取 `path/to/some-file.pdf` 中的表单字段”。

## Claude.ai

这些示例技能在 Claude.ai 中均对付费用户开放。

要使用本仓库中的任何技能或上传自定义技能，请按照 [在 Claude 中使用技能](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b) 中的说明操作。

## Claude API

你可以通过 Claude API 使用 Anthropic 预构建的技能以及上传自定义技能。更多信息请参见 [Skills API 快速入门](https://docs.claude.com/en/api/skills-guide#creating-a-skill)。

# 创建一个基础技能

创建技能非常简单——只需要一个包含 `SKILL.md` 文件的文件夹，其中包含 YAML 前置数据和指令。你可以使用本仓库中的 **template-skill** 作为起点：

```markdown
---
name: my-skill-name
description: 对该技能功能及使用场景的清晰描述
---

# 我的技能名称

[在此添加当该技能激活时 Claude 将遵循的指令]

## 示例
- 示例用法 1
- 示例用法 2

## 指南
- 指南 1
- 指南 2
```

前置数据只需要两个字段：
- `name` – 技能的惟一标识符（小写，空格用连字符代替）
- `description` – 对技能功能及使用场景的完整描述

下方的 Markdown 内容包含 Claude 将遵循的指令、示例和指南。更多详情请参见 [如何创建自定义技能](https://support.claude.com/en/articles/12512198-creating-custom-skills)。

# 合作伙伴技能

技能是教会 Claude 更好地使用特定软件的好方法。当我们看到合作伙伴提供的优秀技能示例时，可能会在此处重点展示：

- **Notion** – [用于 Claude 的 Notion 技能](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)
