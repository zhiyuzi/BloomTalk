<div align="center">

# 孕语 Bloom Talk

**一个可运行的 Agent Runtime 孕期胎教支持系统，把胎教安排、每日记录和持续陪伴放进同一套流程里。**

<p>
  <img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-9b7b6b">
  <img alt="Runtime: Codex" src="https://img.shields.io/badge/runtime-Codex-c98f65">
  <img alt="Storage: Markdown Files" src="https://img.shields.io/badge/storage-markdown%20files-7c9a92">
  <img alt="Status: Template" src="https://img.shields.io/badge/status-template-7d8fb3">
</p>

`营养` `运动` `情绪` `对话` `音乐` `抚摸` `光照` `美育` `自然`

</div>

## 这是什么

孕语是一个给整个孕期持续使用的胎教陪伴系统。

它把建档、每日安排、晚间反馈和持续整理放在同一个项目里，方便你一直按同一套节奏用下去。

## 它能帮你做什么

你可以把常见胎教内容放进同一套流程里统一安排和记录：

- 营养胎教
- 运动胎教
- 情绪胎教
- 对话胎教
- 音乐胎教
- 抚摸胎教
- 光照胎教
- 美育胎教
- 自然胎教

这样做的好处很直接：

- 不用自己反复整理每天该做什么
- 不用把记录分散在很多地方
- 可以一直沿着同一套节奏持续下去

## 3 分钟开始使用

### 1. 下载整个项目

打开 GitHub 仓库页面，点击下载按钮，把整个项目下载到本地。

### 2. 用 VS Code 打开项目

解压后，用 VS Code 打开项目文件夹。

### 3. 选择运行环境

这个项目默认按 Codex 使用。

如果你准备在其他工具里打开它，先让目标环境里的 agent 读取对应迁移文档并代你完成迁移，再进入编辑器：

- [ClaudeCode 迁移说明](./migration/ClaudeCode.md)
- [OpenClaw 迁移说明](./migration/OpenClaw.md)

### 4. 先完成建档

进入 Codex 后，第一次开始时直接输入：

```text
我要建档
```

系统会先和你完成第一版档案建立。这个步骤最重要，因为后面的每日安排和反馈都建立在这份档案上。

## 每天怎么用

日常使用只要记住这一条主线：

```text
建档 -> 每日执行 -> 晚间反馈 -> 持续循环
```

### 白天

问系统今天该做什么，然后按当天安排去做。内容可能包括营养、运动、音乐、对话、抚摸，或者其他适合当前阶段的胎教活动。

### 晚上

把今天实际做了什么、状态怎么样、有没有不舒服、明天是否要调整，反馈给系统。

### 长期

重复这个过程，让计划、记录、分类整理和展示页一直同步更新。

## 运行环境

### Codex

默认环境，直接使用。

### ClaudeCode

如果你准备在 ClaudeCode 中使用，先看 [ClaudeCode 迁移说明](./migration/ClaudeCode.md)。

### OpenClaw

如果你准备在 OpenClaw 中使用，先看 [OpenClaw 迁移说明](./migration/OpenClaw.md)。

### 其他同类工具

如果你使用的是其他同类工具，可以参考 `migration` 目录中的两份文档，按目标工具的规范调整目录、文件名和路径引用。

## 技术说明

如果你想接入、改造或继续扩展，可以先看这几个位置：

- `AGENTS.md`：运行时身份、读取顺序、模块联动规则
- `bloom-talk-mem/`：当前事实、每日记录、计划和分类追踪
- `bloom-talk-kb/`：知识依据、风险边界和专题研究内容
- `.agents/skills/`：任务型技能目录
- `bloom-talk-calendar.html`：当前的人类可读展示页

整体上，这是一个基于 Markdown 文件组织状态的轻量方案，适合持续整理、版本管理和 Agent 驱动使用。

## 提醒

这个项目适合用于整理信息、持续记录和过程陪伴，但不能替代医生、助产士或其他持证医疗专业人员的判断。

## 协议

本项目采用 MIT License，详见 [LICENSE](./LICENSE)。
