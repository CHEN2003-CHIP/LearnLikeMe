# Codex Starter Prompt

Use this prompt after downloading the repository locally and placing your files under `learn-like-me-input/`.

```text
Read the Markdown chat history under learn-like-me-input/history/,
plus learn-like-me-input/preferences.md and learn-like-me-input/context.md.

Use the learn-like-me builder skill in this repository to do the following:

1. infer my learning profile from history first,
2. ask only the minimum necessary follow-up questions for missing, contradictory, or low-confidence fields,
3. separate stable preferences from situational preferences,
4. capture concrete evidence signals with confidence for major preferences,
5. generate a personalized runtime skill named project-learning-assistant,
6. write the generated runtime skill to:
   generated-skills/project-learning-assistant/
7. write the inferred learning profile to:
   generated-skills/learning-profile.md
8. ensure the generated runtime skill behaves like a proactive project-learning copilot rather than passive Q&A,
9. ensure every runtime response requires these sections in order:
   project map
   current understanding
   hidden questions
   next best step

When you respond, include:
- a plain-language learning profile summary
- a structured learning profile
- the generated file paths
- a short self-review covering:
  - whether the skill is truly personalized
  - whether it is proactive enough
- only ask minimal follow-up questions if truly necessary
```
