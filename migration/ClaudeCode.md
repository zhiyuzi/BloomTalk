# ClaudeCode 迁移说明

这份说明用于把当前仓库从 Codex 约定迁到 ClaudeCode 可直接读取的结构。

## 迁移前先知道

ClaudeCode 的项目级说明文件是 `CLAUDE.md`。官方文档也把 `~/.claude/` 作为用户级目录。

对这份仓库来说，最小必要迁移就是三件事：

1. 把目录名从 `.agents` 改成 `.claude`
2. 把入口文件从 `AGENTS.md` 改成 `CLAUDE.md`
3. 把项目里所有旧路径和旧文件名引用统一改掉

## 第一步：重命名目录

把根目录下的：

```text
.agents
```

改成：

```text
.claude
```

改完之后，本项目里的技能目录会变成：

```text
.claude/skills/
```

## 第二步：重命名入口文件

把根目录下的：

```text
AGENTS.md
```

改成：

```text
CLAUDE.md
```

## 第三步：统一修改字符串引用

这一步最容易漏。

请在整个项目里全局搜索下面两个字符串，并统一替换：

- `AGENTS.md`
- `.agents/`

推荐替换方式：

- `AGENTS.md` -> `CLAUDE.md`
- `.agents/` -> `.claude/`

当前仓库里，至少这些位置会命中：

- `CLAUDE.md`（原 `AGENTS.md`）
- `bloom-talk-mem/index.md`
- `.claude/skills/bloom-talk-create-profile/SKILL.md`

其中最重要的是根目录说明文件里的 skill 路径。例如下面这类内容：

```text
./.agents/skills/...
```

要统一改成：

```text
./.claude/skills/...
```

## 迁移完成后怎么检查

完成后，建议再做一次全局搜索：

- 搜索 `AGENTS.md`
- 搜索 `.agents/`

如果你准备完全按 ClaudeCode 版本使用，这两类旧引用都应该已经处理完。

## 参考

以下迁移原则参考了 ClaudeCode 官方文档中的项目级 `CLAUDE.md` 与 `~/.claude/` 目录约定：

- https://docs.anthropic.com/en/docs/claude-code/memory
