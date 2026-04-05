<div align="center">

# Bloom Talk

**A runnable Agent Runtime for prenatal support, bringing prenatal routines, daily records, and ongoing companionship into one workflow.**

[English](./README.en.md) | [中文](./README.md)

<p>
  <img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-9b7b6b">
  <img alt="Runtime: Codex" src="https://img.shields.io/badge/runtime-Codex-c98f65">
  <img alt="Storage: Markdown Files" src="https://img.shields.io/badge/storage-markdown%20files-7c9a92">
  <img alt="Status: Template" src="https://img.shields.io/badge/status-template-7d8fb3">
</p>

`nutrition` `exercise` `emotion` `dialog` `music` `touch` `light` `art` `nature`

</div>

## What It Is

Bloom Talk is a prenatal support system designed to be used throughout pregnancy.

It keeps profile intake, daily routines, evening feedback, and ongoing organization inside the same workflow, so the whole process can follow one consistent rhythm.

## What It Helps With

You can manage common prenatal education categories in one place:

- Nutrition
- Exercise
- Emotion
- Dialog
- Music
- Touch
- Light
- Art
- Nature

The main benefits are straightforward:

- You do not have to reorganize what to do every day
- Your records do not get scattered across different places
- The whole process stays consistent over time

## Get Started In 3 Minutes

### 1. Download the whole project

Open the GitHub repository page, click the download button, and save the whole project locally.

### 2. Open it in VS Code

Unzip the project and open the folder in VS Code.

### 3. Choose your runtime

This project is set up for Codex by default.

If you want to open it in another tool, let the agent in that target environment read the corresponding migration guide and perform the migration for you before you start using the editor:

- [ClaudeCode Migration Guide](./migration/ClaudeCode.md)
- [OpenClaw Migration Guide](./migration/OpenClaw.md)

### 4. Start with profile intake

Once you are in Codex, begin by typing:

```text
我要建档
```

The system will guide you through the first profile setup. This is the most important step, because the later daily routines and feedback depend on that profile.

## How To Use It Every Day

The daily loop is simple:

```text
profile intake -> daily routines -> evening feedback -> repeat
```

### Daytime

Ask the system what to do today, then follow the suggested routines. That may include nutrition, exercise, music, dialog, touch, or other prenatal activities that fit the current stage.

### Evening

Tell the system what you actually did, how you felt, whether anything was uncomfortable, and whether tomorrow's plan needs adjustment.

### Long-term use

Repeat this process so that plans, logs, categorized records, and the overview page keep updating together.

## Runtime Options

### Codex

This is the default runtime, so you can use it directly.

### ClaudeCode

If you want to use ClaudeCode, read the [ClaudeCode Migration Guide](./migration/ClaudeCode.md) first.

### OpenClaw

If you want to use OpenClaw, read the [OpenClaw Migration Guide](./migration/OpenClaw.md) first.

### Other similar tools

If you use another similar tool, you can refer to the guides in the `migration` directory and adjust directory names, file names, and path references to match that tool's conventions.

## Technical Notes

If you want to integrate, customize, or extend the project, start with these locations:

- `AGENTS.md`: runtime identity, reading order, and module coordination rules
- `bloom-talk-mem/`: current facts, daily logs, plans, and categorized tracking
- `bloom-talk-kb/`: knowledge boundaries, risk notes, and topic research
- `.agents/skills/`: task-specific skill directory
- `bloom-talk-calendar.html`: the current human-readable overview page

Overall, this is a lightweight Markdown-based approach for storing runtime state, versioning ongoing records, and supporting Agent Runtime workflows.

## Note

This project is suitable for organizing information, keeping ongoing records, and supporting the pregnancy process, but it does not replace doctors, midwives, or other licensed medical professionals.

## License

This project is licensed under the MIT License. See [LICENSE](./LICENSE) for details.
