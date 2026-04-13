# LearnLikeMe

<p align="center">
  <img src="./assets/learnlikeme-logo.svg" alt="LearnLikeMe logo" width="140" />
</p>

<p align="center">
  Turn real chat history into a personalized project-learning copilot.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/openai-agent%20skill-111827?style=for-the-badge" alt="OpenAI Agent Skill" />
  <img src="https://img.shields.io/badge/personalized-learning-0f766e?style=for-the-badge" alt="Personalized Learning" />
  <img src="https://img.shields.io/badge/history-driven-f59e0b?style=for-the-badge" alt="History Driven" />
</p>

LearnLikeMe is an OpenAI Agent Skill package that helps people build their own project-learning assistant from the way they already learn.

Instead of forcing every user through the same generic tutor flow, LearnLikeMe can ingest prior Markdown chat history, infer stable learning patterns, ask only the missing questions, and generate a runtime skill that teaches codebases the way that specific person actually absorbs them.

## Why This Is Different

Most "AI tutor" setups are still one-size-fits-all.

LearnLikeMe is built around a different idea:

- your chat history already contains strong evidence about how you learn
- your ideal pace, explanation depth, and question style should shape the assistant
- project learning should be proactive, roadmap-driven, and adaptive
- the assistant should help you learn repositories, docs, architecture, and modules, not just answer isolated questions

## What You Get

- A builder skill: `learn-like-me`
- A generated runtime skill: `project-learning-assistant`
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

The builder creates `project-learning-assistant`, a runtime skill that adapts to your pace, depth, question habits, and comprehension limits.

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

1. Put your Markdown chat exports into `learn-like-me-input/history/`.
2. Add optional notes to `learn-like-me-input/preferences.md` and `learn-like-me-input/context.md`.
3. Use the `learn-like-me` builder skill.
4. Review the inferred learning profile.
5. Generate your personalized `project-learning-assistant`.

## Core Idea

The best project-learning assistant should not start from zero.

It should start from you.
