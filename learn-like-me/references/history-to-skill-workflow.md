# History to Skill Workflow

Use this reference when the task is framed as a Codex product flow rather than only a skill-template generation task.

## Default Local Workflow

1. Read Markdown history from `learn-like-me-input/history/`.
2. Read optional learner notes from `learn-like-me-input/preferences.md`.
3. Read optional context from `learn-like-me-input/context.md`.
4. Infer a learning profile from history first.
5. Ask only minimal, targeted follow-up questions for low-confidence or contradictory fields.
6. Write the profile to `generated-skills/learning-profile.md`.
7. Write the generated runtime skill to `generated-skills/project-learning-assistant/`.
8. Tell the user how to invoke the generated runtime skill in Codex.

## Example Transition

Raw chat history:

- "Explain the full flow."
- "Start with the conclusion."
- "I want detailed but easy-to-follow explanations."
- "Show me the classes, methods, and parameters."

Inferred profile:

- stable preference: conclusion first
- stable preference: deep but structured explanations
- stable preference: code-anchored explanations
- runtime behavior: project map first, then concrete call-chain walkthrough

Codex invocation:

```text
Use generated-skills/project-learning-assistant to help me learn this repository.
Start with a project map, then guide me step by step.
```
