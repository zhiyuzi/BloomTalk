# OpenClaw 迁移说明

这份说明用于把当前仓库迁到 OpenClaw 使用。

## 迁移前先知道

OpenClaw 的官方 workspace 约定会直接读取 `AGENTS.md`，并优先加载工作区里的 `skills/` 目录。

对这份仓库来说，最小必要迁移有三处：

1. 修改 OpenClaw 的 workspace 配置，让它指向这个项目
2. 把目录名从 `.agents` 改成 `skills`
3. 修改 `AGENTS.md` 中所有 `.agents/` 字符串，让路径符合 OpenClaw 结构

## 第一步：让 OpenClaw 指向这个项目

OpenClaw 默认 workspace 在 `~/.openclaw/workspace`，你可以二选一：

- 直接把整个项目放进默认 workspace
- 修改 `~/.openclaw/openclaw.json`，让 workspace 指向当前项目根目录

配置示例：

```json
{
  "agent": {
    "workspace": "D:/opc-os/projects/bloom-talk-template"
  }
}
```

## 第二步：重命名目录

把根目录下的：

```text
.agents
```

改成：

```text
skills
```

改完之后，本项目里的技能目录会变成：

```text
skills/bloom-talk-create-profile/
```

## 第三步：修改 `AGENTS.md` 里的路径字符串

这一步就是你刚刚提醒的重点。

请在 `AGENTS.md` 中全局搜索：

```text
.agents/
```

再按 OpenClaw 的目录结构统一改成：

```text
skills/
```

例如下面这类内容：

```text
./.agents/skills/bloom-talk-create-profile/SKILL.md
```

应该改成：

```text
./skills/bloom-talk-create-profile/SKILL.md
```

当前 `AGENTS.md` 里涉及 `.agents/` 的 skill 路径、索引说明和事实来源说明，都要一起改掉。

## 关于 `AGENTS.md` 文件名

这点和 ClaudeCode 不一样。

OpenClaw 官方 workspace 本来就使用 `AGENTS.md`，所以这里不需要把它改名。你要改的是它里面的路径字符串，而不是文件名本身。

## 关于提醒与定时任务

如果你希望 OpenClaw 帮你保持“白天执行、晚上反馈”的节奏，可以再补两类东西：

### 1. 增加 `HEARTBEAT.md`

在 workspace 里增加一个简短的 `HEARTBEAT.md`，把每天巡检时要做的事情写进去。

### 2. 增加 cron 提醒

OpenClaw 自带 cron。你可以直接加两个提醒：

早上提醒查看当天安排：

```bash
openclaw cron add \
  --name "Bloom Talk Morning" \
  --cron "0 9 * * *" \
  --tz "Asia/Shanghai" \
  --session main \
  --system-event "提醒：查看今天的胎教安排，并开始执行。" \
  --wake now
```

晚上提醒补充反馈：

```bash
openclaw cron add \
  --name "Bloom Talk Evening" \
  --cron "0 21 * * *" \
  --tz "Asia/Shanghai" \
  --session main \
  --system-event "提醒：回顾今天做了什么，并补充晚间反馈。" \
  --wake now
```

## 迁移完成后怎么检查

完成后，建议至少检查这几件事：

- OpenClaw 的 workspace 已经指向这个项目
- 根目录下已经没有 `.agents`，而是 `skills`
- `AGENTS.md` 中已经没有旧的 `.agents/` 字符串

## 参考

以下迁移原则参考了 OpenClaw 官方文档中的 workspace、skills 与 cron 约定：

- https://open-claw.bot/docs/concepts/agent-workspace/
- https://open-claw.bot/docs/tools/skills/
- https://open-claw.bot/docs/cron-docs
