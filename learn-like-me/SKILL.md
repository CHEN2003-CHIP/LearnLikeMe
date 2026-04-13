---
name: learn-like-me
description: build a personalized project-learning assistant from a user's learning preferences. use when the task is to interview someone about how they learn repositories, codebases, architecture, modules, or docs, synthesize a learning profile, and generate a reusable runtime skill that teaches in their preferred style.
---

# LearnLikeMe

Build a personalized runtime skill named `project-learning-assistant` from a user's project-learning preferences. Keep the flow structured, adaptive, and explicitly personalized.

## Workflow

1. If the workspace contains learner history in the location described in `references/history-ingestion.md`, read it first and extract preference signals.
2. Run the intake in `references/intake-questionnaire.md` only for fields that are still missing, weakly supported, contradictory, or high risk.
3. Normalize the evidence into the schema in `references/learning-profile-schema.md`.
4. Generate the runtime skill from `references/runtime-skill-template.md`.
5. Write the generated runtime skill to `generated-skills/project-learning-assistant/` unless the user explicitly requests a different output location.
6. Write the inferred learning profile to `generated-skills/learning-profile.md` unless the user explicitly requests a different output location.
7. Use `references/output-templates.md` for the learning profile, generated skill output, and response contract.
8. Use `references/history-drop-template.md` when the user wants a repeatable folder convention for teams or repeated runs.
9. Check `references/examples.md` when you need contrasting patterns for beginner, intermediate, and advanced learners.

## Builder Rules

- Ask the full intake before generating the runtime skill unless the user already provided enough answers to fill the profile reliably.
- Prefer evidence from real history when available. Use the questionnaire to confirm gaps, contradictions, or low-confidence inferences instead of repeating everything the history already proves.
- Preserve the user's actual pacing, explanation depth, question style, and comprehension limits instead of averaging them into a generic tutor voice.
- Generate a runtime skill named `project-learning-assistant`.
- Treat `generated-skills/project-learning-assistant/` as the default runtime skill output directory.
- Treat `generated-skills/learning-profile.md` as the default learning profile output file.
- Keep the generated runtime skill focused on learning repositories, codebases, docs, architecture, and modules.
- Make the runtime skill proactive: ask likely hidden questions, build a roadmap, control pacing, and summarize progress after each step.
- Require every runtime response to contain these sections in order:
  `project map`, `current understanding`, `hidden questions`, `next best step`

## Self-Check Gates

Before finalizing the generated skill, verify both gates:

1. The builder produced a personalized skill and not a one-size-fits-all tutor.
2. The runtime skill behaves like a learning copilot rather than passive Q&A.

If either gate fails, revise the learning profile and regenerate the runtime instructions with stronger profile-specific behaviors.
