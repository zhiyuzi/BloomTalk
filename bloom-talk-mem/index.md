# Bloom Talk Memory 模块说明

本文件定义 `bloom-talk-mem/` 的内部边界。

Memory 层只负责两类东西：

- 模块契约与字段模板
- 当前事实、记录、计划与分类索引

跨模块联动由 [AGENTS.md](../AGENTS.md) 统一定义，本文件不重复承担系统级编排。

## Memory 内部层次

### 1. 契约文件

- [index.md](./index.md)：Memory 的模块说明
- [profile-template.md](./profile-template.md)：`profile.md` 的唯一字段模板

### 2. 状态与记录文件

- [profile.md](./profile.md)：当前有效的个人事实与日期基准
- [changelog.md](./changelog.md)：核心基准修正轨迹
- `logs/`：按日期保存的实际记录
- `plans/`：按日期保存的计划快照
- `tracks/`：按胎教类型整理的第二索引层

## 设计原则

- 每个文件只承担一种主要职责
- `profile.md` 的字段结构只由 [profile-template.md](./profile-template.md) 定义
- `profile.md` 保存当前值，不保存字段设计说明
- `tracks/` 是分类索引，不是原始日记
- Memory 只保存事实与记录，不负责知识论证

## 文件与目录职责

### [profile-template.md](./profile-template.md)

这是 `profile.md` 的唯一字段模板。

它负责：

- 定义 `profile.md` 的字段顺序
- 定义哪些字段是 profile 的固定组成部分
- 为建档和修复档案提供统一结构

它不负责：

- 保存真实数据
- 解释医学依据
- 记录某次具体修改

如果以后要新增、删除或重命名 profile 字段，先修改本文件，再处理 `profile.md` 与相关 skill。

### [profile.md](./profile.md)

用于保存当前有效的个人事实和日期基准。

它负责：

- 保存当前生效的档案内容
- 记录当前采用的孕周与预产期依据
- 保存长期有效的健康、照护与生活背景

它不负责：

- 维护字段设计说明
- 记录某一天发生的具体事件
- 保存某一天的计划清单
- 长期堆积重复性日记内容

### [changelog.md](./changelog.md)

用于记录核心基准的修正轨迹。

它负责：

- 预产期修正
- 定孕周依据变更
- 重要日期基准修正

它不负责：

- 普通日记
- 当日计划
- 分类活动摘要

### `logs/`

用于记录某一天真实发生的事情。

规则如下：

- 文件名格式为 `YYYY-MM-DD.md`
- `YYYY-MM-DD.example.md` 仅作为写法示例，不属于真实运行数据
- 记录实际做了什么、感受如何、出现了什么情况
- 如有需要，可写入计划执行后的实际结果
- 如需后续分类汇总，可在记录中写出相关类别，便于同步到 `tracks/`

### `plans/`

用于记录某一天准备做什么。

规则如下：

- 文件名格式为 `YYYY-MM-DD.md`
- `YYYY-MM-DD.example.md` 仅作为写法示例，不属于真实运行数据
- 只有在用户明确提出制定或整理计划时才创建或更新
- 不自动删除
- 同一天的计划变化直接修改同一个日期文件
- 已完成事项可以在计划文件中标记，也可以把执行结果写入当天 `logs/`

一句话理解：

- `plans/` 记录准备做什么
- `logs/` 记录实际做了什么

### `tracks/`

用于按胎教类型做第二层索引。

当前固定分类包括：

- `nutrition.md`
- `exercise.md`
- `emotion.md`
- `touch.md`
- `dialog.md`
- `music.md`
- `light.md`
- `art.md`
- `nature.md`

它负责：

- 某一类活动的累计摘要
- 某一类活动的时间线
- 某一类活动的阶段性观察

它不负责：

- 取代 `logs/` 成为原始记录
- 取代 `profile.md` 成为个人档案

## 内部更新边界

- 修改 `profile.md` 时，不在本文件中决定是否同步 `changelog.md` 或 HTML
- 修改 `logs/` 时，是否需要同步 `tracks/` 与 HTML，由 [AGENTS.md](../AGENTS.md) 决定
- Skill 可以读取本文件理解 Memory 结构，但不在这里定义系统联动流程

## 一句话理解

- `profile-template.md`：档案应该长什么样
- `profile.md`：当前档案是什么
- `changelog.md`：核心基准怎么改过
- `logs/`：实际发生了什么
- `plans/`：准备做什么
- `tracks/`：某一类事情累计发生了什么
