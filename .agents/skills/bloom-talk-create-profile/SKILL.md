---
name: bloom-talk-create-profile
description: 以访谈式问答创建或修复 Bloom Talk（孕语）的怀孕档案。当用户说“我要建档”、想补齐 profile 基础信息、修正孕周基准或修正预产期依据时使用本技能。触发后应先像人类建档问诊一样进行简短问答，再写入 profile，而不是立刻把未知项批量写成 `未知`。
---

# Bloom Talk 建档技能

本技能的核心不是“填模板”，而是“和人完成建档对话”。

当任务是首次建档时，先用问答方式收集关键信息，再创建 `bloom-talk-mem/profile.md`。

字段结构以 [bloom-talk-mem/profile-template.md](../../../bloom-talk-mem/profile-template.md) 为唯一模板。

如果需要理解字段为什么存在、哪些字段与孕周推算和风险理解密切相关，再读取 [references/profile-fields.md](references/profile-fields.md)。

如果需要知道建档时应该先问什么、每轮问多少、用什么节奏与人交互，再读取 [references/profile-intake.md](references/profile-intake.md)。

## 使用步骤

1. 读取 `AGENTS.md`
2. 读取 [bloom-talk-mem/index.md](../../../bloom-talk-mem/index.md)
3. 读取 [bloom-talk-mem/profile-template.md](../../../bloom-talk-mem/profile-template.md)
4. 读取 [bloom-talk-mem/profile.md](../../../bloom-talk-mem/profile.md)
5. 判断这次是“首次建档”还是“修复已有档案”
6. 如果是首次建档，先进入问答式访谈，不要立刻写文件
7. 只在已经收集到最小必要信息后，再创建或更新 `profile.md`
8. 用户明确说“不知道”的字段，才能写为 `未知`

## 访谈规则

- 访谈时，严格遵守 `AGENTS.md` 中关于“运行时身份”“交互对象判断”“对话规则”“建档对话规则”的要求
- 把建档当作一次简短问诊或建档访谈，不要像脚本一样连续宣布“我将读取什么文件”
- 每轮只问 1 到 3 个紧密相关的问题，等用户回答，再继续下一轮
- 优先先问最关键的信息，再问补充项
- 问题要用自然中文，像人与人对话，不要用机器式播报
- 当用户已经给出了足够信息时，再说明你将根据这些信息写入 `profile.md`
- 如果用户还没回答，不要抢先把大量字段写成 `未知`

## 最小必要信息

首次建档时，优先拿到这几类信息：

- 记录对象称呼或昵称
- 当前状态
- 日期基准：LMP、EDD、超声、当前采用的定孕周依据，至少拿到其中能确认的一部分
- 是否首次怀孕，以及重要既往妊娠史
- 重要健康背景、药物补充剂、过敏禁忌
- 当前是否已经建立医生、助产士或医院照护

拿到这些信息后，就可以先建立第一版档案；其余字段可以在后续补齐。

## 边界

- 本技能不负责定义 profile 字段结构
- 本技能不负责维护 `changelog.md`
- 本技能不直接决定是否同步 `bloom-talk-calendar.html`
- 首次建档时，不要在用户还未回答前就提前同步 HTML

如果 `profile.md` 的变化需要联动其他文件，回到 `AGENTS.md` 的系统联动规则执行。
