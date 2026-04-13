# LearnLikeMe

<p align="center">
  <img src="./assets/learnlikeme-logo.svg" alt="LearnLikeMe logo" width="140" />
</p>

<p align="center">
  Turn real chat history into a personalized project-learning copilot with Codex.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/openai-agent%20skill-111827?style=for-the-badge" alt="OpenAI Agent Skill" />
  <img src="https://img.shields.io/badge/personalized-learning-0f766e?style=for-the-badge" alt="Personalized Learning" />
  <img src="https://img.shields.io/badge/history-driven-f59e0b?style=for-the-badge" alt="History Driven" />
</p>

LearnLikeMe is a Codex-friendly OpenAI Agent Skill package that helps people build their own project-learning assistant from the way they already learn.

Instead of forcing every user through the same generic tutor flow, LearnLikeMe can ingest prior Markdown chat history, infer stable learning patterns, ask only the missing questions, and generate a runtime skill that teaches codebases the way that specific person actually absorbs them.

## Why This Is Different

Most "AI tutor" setups are still one-size-fits-all.

LearnLikeMe is built around a different idea:

- your chat history already contains strong evidence about how you learn
- your ideal pace, explanation depth, and question style should shape the assistant
- project learning should be proactive, roadmap-driven, and adaptive
- the assistant should help you learn repositories, docs, architecture, and modules, not just answer isolated questions
- the repo is structured so Codex can read local files and generate the personalized skill directly

## What You Get

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

## Built For

LearnLikeMe works especially well for people who want to:

- understand unfamiliar repositories without drowning in details
- turn old AI conversations into a reusable learning profile
- onboard faster into real codebases
- learn architecture and modules step by step
- avoid generic explanations that never match their pace

## How It Works

### 1. Drop your history

Put your exported Markdown chats here:

```text
learn-like-me-input/
  history/
  preferences.md
  context.md
```

### 2. Let the builder infer your learning style

`learn-like-me` reads the history, extracts repeated patterns, separates stable preferences from task-specific ones, and only asks targeted follow-up questions when needed.

### 3. Generate your own runtime learning copilot

The builder creates `project-learning-assistant`, writes it to `generated-skills/project-learning-assistant/`, and adapts it to your pace, depth, question habits, and comprehension limits.

### 4. Learn real projects better

The generated runtime skill helps you learn:

- repos
- codebases
- architecture
- modules
- docs

And it does it proactively by surfacing hidden questions, building a roadmap, controlling pacing, and summarizing progress after every step.

## Example User Experience

Instead of saying:

> "Please explain this repo."

You get a learning copilot that behaves more like:

- "Here is the project map for your current goal."
- "Here is what you probably understand already."
- "Here are the hidden questions you have not asked yet."
- "Here is the next best step based on your pace."

That difference is where most of the value lives.

## Codex Quick Start

This repository is currently optimized for users who download it locally and use Codex against the project files.

### Step 1. Clone the repo

```bash
git clone https://github.com/CHEN2003-CHIP/LearnLikeMe.git
cd LearnLikeMe
```

### Step 2. Put your materials into the input folder

Drop your exported Markdown chats into:

```text
learn-like-me-input/history/
```

Then optionally edit:

- `learn-like-me-input/preferences.md`
- `learn-like-me-input/context.md`

### Step 3. Open the repo in Codex

Point Codex at the local project folder so it can read:

- `learn-like-me/`
- `learn-like-me-input/history/`
- `learn-like-me-input/preferences.md`
- `learn-like-me-input/context.md`
- `generated-skills/`

### Step 4. Give Codex the starter prompt

Open [CODEX-STARTER-PROMPT.md](./CODEX-STARTER-PROMPT.md) and paste that prompt into Codex, or use the equivalent instruction in your own words.

### Step 5. Let Codex generate your personalized skill

Codex should:

1. read the history files first
2. infer your learning profile
3. ask only minimal follow-up questions if needed
4. generate `project-learning-assistant`
5. write it to `generated-skills/project-learning-assistant/`
6. keep the output proactive, roadmap-driven, and personalized

### Step 6. Use the generated runtime skill to learn real projects

After generation, tell Codex to use the generated skill directly, for example:

```text
Use generated-skills/project-learning-assistant to help me learn this repository.
Start with a project map, then guide me step by step.
```

Once generated, the runtime skill should help you learn:

- repository structure
- code flow
- architecture
- modules
- docs

Every step should end with:

- `project map`
- `current understanding`
- `hidden questions`
- `next best step`

## Repository Structure

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

## Why People Star Projects Like This

Projects earn stars when they feel immediately useful, surprisingly clear, and easy to try.

LearnLikeMe aims for exactly that:

- easy to understand
- easy to adapt
- easy to extend
- deeply practical for real developer onboarding

If you believe developer tools should adapt to how humans learn, this project is for you.

## Quick Start

1. Clone the repository locally.
2. Put your Markdown chat exports into `learn-like-me-input/history/`.
3. Add optional notes to `learn-like-me-input/preferences.md` and `learn-like-me-input/context.md`.
4. Open the repo in Codex.
5. Paste the prompt from `CODEX-STARTER-PROMPT.md`.
6. Let Codex write the generated skill to `generated-skills/project-learning-assistant/`.
7. Review the inferred learning profile.
8. Ask Codex to use `generated-skills/project-learning-assistant` to teach your target repo.

## Core Idea

The best project-learning assistant should not start from zero.

It should start from you.
