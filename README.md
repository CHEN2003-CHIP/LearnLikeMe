# LearnLikeMe

<p align="center">
  <img src="./assets/learnlikeme-logo.svg" alt="LearnLikeMe logo" width="140" />
</p>

<p align="center">
  Turn real chat history into a personalized project-learning copilot with Codex.
</p>

<p align="center">
  用真实聊天历史，生成一个真正适合自己的项目学习副驾。
</p>

<p align="center">
  <img src="https://img.shields.io/badge/openai-agent%20skill-111827?style=for-the-badge" alt="OpenAI Agent Skill" />
  <img src="https://img.shields.io/badge/personalized-learning-0f766e?style=for-the-badge" alt="Personalized Learning" />
  <img src="https://img.shields.io/badge/history-driven-f59e0b?style=for-the-badge" alt="History Driven" />
</p>

LearnLikeMe is a Codex-friendly OpenAI Agent Skill package that helps people build their own project-learning assistant from the way they already learn.

LearnLikeMe 是一个面向 Codex 的 OpenAI Agent Skill 项目。它的目标不是做一个通用 tutor，而是把用户真实的学习习惯沉淀成一个可复用的项目学习助手。

Instead of forcing every user through the same generic tutor flow, LearnLikeMe can ingest prior Markdown chat history, infer stable learning patterns, ask only the missing questions, and generate a runtime skill that teaches codebases the way that specific person actually absorbs them.

它会优先读取历史 Markdown 对话，提炼稳定偏好与场景偏好，只补问必要问题，然后生成一个个性化的 `project-learning-assistant`。

## Why This Is Different | 为什么不一样

Most AI tutor setups are still one-size-fits-all.

大多数 AI 学习助手仍然是“一套话术讲所有人”。

LearnLikeMe is built around a different idea:

- your chat history already contains strong evidence about how you learn
- your ideal pace, explanation depth, and question style should shape the assistant
- project learning should be proactive, roadmap-driven, and adaptive
- the assistant should help you learn repositories, docs, architecture, and modules, not just answer isolated questions
- the repo is structured so Codex can read local files and generate the personalized skill directly

LearnLikeMe 的设计重点是：

- 用户历史对话里已经藏着大量学习偏好证据
- 节奏、讲解深度、提问方式应该跟着人走，而不是人迁就工具
- 项目学习应该是主动式、路线图驱动、可调节节奏的
- 它应该帮助用户学 repo / codebase / architecture / modules，而不只是回答一个孤立问题
- 整个仓库结构已经按 Codex 可直接读取本地文件来设计

## What You Get | 你会得到什么

- A builder skill: `learn-like-me`
- A generated runtime skill: `project-learning-assistant`
- A fixed output location for generated skills: `generated-skills/`
- History-first personalization from Markdown exports
- A stable drop-folder convention for repeated use
- A proactive output contract for every learning step:
  - `project map`
  - `current understanding`
  - `hidden questions`
  - `next best step`

对应中文理解：

- 一个 builder skill：`learn-like-me`
- 一个最终生成的 runtime skill：`project-learning-assistant`
- 一个固定生成目录：`generated-skills/`
- 优先使用历史聊天记录做个性化
- 一个稳定的投递目录规范
- 每一步学习都要求固定输出：
  - `project map`
  - `current understanding`
  - `hidden questions`
  - `next best step`

## Built For | 适合谁

LearnLikeMe works especially well for people who want to:

- understand unfamiliar repositories without drowning in details
- turn old AI conversations into a reusable learning profile
- onboard faster into real codebases
- learn architecture and modules step by step
- avoid generic explanations that never match their pace

这个项目特别适合这些人：

- 经常要看陌生仓库，但又不想一上来被细节淹没
- 想把过去和 AI 的聊天沉淀成长期可复用的学习画像
- 想更快进入真实代码库
- 想按步骤理解架构和模块
- 讨厌“听起来都对，但就是不适合自己”的通用解释

## How It Works | 工作方式

### 1. Drop your history | 放入历史聊天

Put your exported Markdown chats here:

把导出的 Markdown 聊天记录放到这里：

```text
learn-like-me-input/
  history/
  preferences.md
  context.md
```

### 2. Let the builder infer your learning style | 让 builder 推断你的学习方式

`learn-like-me` reads the history, extracts repeated patterns, separates stable preferences from task-specific ones, and only asks targeted follow-up questions when needed.

`learn-like-me` 会读取历史对话，提取重复出现的学习模式，区分“稳定偏好”和“场景偏好”，并且只在必要时追问。

### 3. Generate your runtime learning copilot | 生成你的运行时学习助手

The builder creates `project-learning-assistant`, writes it to `generated-skills/project-learning-assistant/`, and adapts it to your pace, depth, question habits, and comprehension limits.

builder 会生成 `project-learning-assistant`，并把它写入：

```text
generated-skills/project-learning-assistant/
```

生成出来的 skill 会按照你的节奏、讲解深度、提问习惯和理解上限来定制。

### 4. Use the generated skill with Codex | 让 Codex 用它继续带你学项目

Once generated, the runtime skill helps you learn:

- repos
- codebases
- architecture
- modules
- docs

And it does it proactively by surfacing hidden questions, building a roadmap, controlling pacing, and summarizing progress after every step.

生成完成后，你就可以让 Codex 使用这个 runtime skill 来继续带你学项目。它不是被动答题，而是会：

- 主动补全隐藏问题
- 先建立学习路线图
- 根据你的节奏控制展开速度
- 每一步后总结当前理解状态

## Codex Quick Start | Codex 使用步骤

This repository is currently optimized for users who download it locally and use Codex against the project files.

这个项目当前优先优化的是“用户把仓库下载到本地后，直接让 Codex 读取并生成 skill”的工作流。

### Step 1. Clone the repo | 克隆仓库

```bash
git clone https://github.com/CHEN2003-CHIP/LearnLikeMe.git
cd LearnLikeMe
```

### Step 2. Put your materials into the input folder | 把材料放进输入目录

Drop your exported Markdown chats into:

```text
learn-like-me-input/history/
```

Then optionally edit:

- `learn-like-me-input/preferences.md`
- `learn-like-me-input/context.md`

也可以按需补充这两个文件：

- `learn-like-me-input/preferences.md`
- `learn-like-me-input/context.md`

### Step 3. Open the repo in Codex | 用 Codex 打开仓库

Point Codex at the local project folder so it can read:

- `learn-like-me/`
- `learn-like-me-input/history/`
- `learn-like-me-input/preferences.md`
- `learn-like-me-input/context.md`
- `generated-skills/`

### Step 4. Give Codex the starter prompt | 把启动提示词发给 Codex

Open [CODEX-STARTER-PROMPT.md](./CODEX-STARTER-PROMPT.md) and paste that prompt into Codex.

打开 [CODEX-STARTER-PROMPT.md](./CODEX-STARTER-PROMPT.md)，把里面那段提示词直接发给 Codex。

### Step 5. Let Codex generate the skill | 让 Codex 生成 skill

Codex should:

1. read the history files first
2. infer your learning profile
3. ask only minimal follow-up questions if needed
4. generate `project-learning-assistant`
5. write it to `generated-skills/project-learning-assistant/`
6. keep the output proactive, roadmap-driven, and personalized

也就是：

1. 先读历史聊天
2. 推断 learning profile
3. 只问最少的补充问题
4. 生成 `project-learning-assistant`
5. 写入 `generated-skills/project-learning-assistant/`
6. 确保它是主动式、路线图驱动、真正个性化的

### Step 6. Use the generated runtime skill | 使用生成后的 runtime skill

After generation, tell Codex to use the generated skill directly, for example:

```text
Use generated-skills/project-learning-assistant to help me learn this repository.
Start with a project map, then guide me step by step.
```

中文也可以直接这样说：

```text
请使用 generated-skills/project-learning-assistant 带我学习这个仓库。
先给我 project map，再一步一步讲。
```

Every step should end with:

- `project map`
- `current understanding`
- `hidden questions`
- `next best step`

每一步都应该以这四个部分收尾：

- `project map`
- `current understanding`
- `hidden questions`
- `next best step`

## Repository Structure | 仓库结构

```text
.
|- learn-like-me/
|  |- SKILL.md
|  |- agents/
|  |- references/
|  `- assets/
|- learn-like-me-input/
|  |- history/
|  |- preferences.md
|  `- context.md
|- generated-skills/
|  `- project-learning-assistant/
`- skill.zip
```

## Notes on Privacy | 隐私说明

The repository is set up so that user chat history placed under `learn-like-me-input/history/` is not meant to be pushed to GitHub.

这个仓库已经按“历史聊天记录默认不上传 GitHub”的思路组织，`learn-like-me-input/history/` 主要用于本地生成 skill。

## Core Idea | 核心理念

The best project-learning assistant should not start from zero.

It should start from you.

最好的项目学习助手，不应该从零开始。

它应该从“你是怎么学习的”开始。
