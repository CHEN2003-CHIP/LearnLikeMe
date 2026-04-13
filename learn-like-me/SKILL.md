---
name: learn-like-me
description: build a personalized project-learning assistant from a user's learning preferences. use when the task is to infer how someone learns repositories, codebases, architecture, modules, or docs from chat history first, synthesize a learning profile, and generate a reusable runtime skill that teaches in their preferred style.
---

# LearnLikeMe

Build a personalized runtime skill named `project-learning-assistant` from a user's project-learning preferences. Default to chat-history-first inference, use follow-up questions only to close important gaps, and write the generated artifacts to the local `generated-skills/` workspace area.

## Workflow

1. Read learner history first from the location described in `references/history-ingestion.md`.
2. Extract preference evidence, confidence, and stable-vs-situational distinctions before asking questions.
3. Ask only for missing, contradictory, or low-confidence fields using the intake guidance in `references/intake-questionnaire.md`.
4. Normalize all evidence into the schema in `references/learning-profile-schema.md`.
5. Generate the runtime skill from `references/runtime-skill-template.md`.
6. Write the runtime skill to `generated-skills/project-learning-assistant/` unless the user explicitly requests a different output location.
7. Write the inferred learning profile to `generated-skills/learning-profile.md` unless the user explicitly requests a different output location.
8. Use `references/output-templates.md` for the learning profile, generated skill output, and response contract.
9. Use `references/history-to-skill-workflow.md` when the task is framed as a Codex product workflow from local history to reusable skill.
10. Use `references/history-drop-template.md` when the user wants a repeatable folder convention for teams or repeated runs.
11. Check `references/examples.md` when you need contrasting patterns for beginner, intermediate, and advanced learners.

## Builder Rules

- Treat history as the default evidence source. The questionnaire is a targeted gap-filling tool, not the default first step.
- Preserve the user's actual pacing, explanation depth, question style, and comprehension limits instead of averaging them into a generic tutor voice.
- Separate `stable_preferences` from `situational_preferences` as a required output.
- Record concrete evidence for major preference claims and keep confidence visible in the profile.
- Generate a runtime skill named `project-learning-assistant`.
- Treat `generated-skills/project-learning-assistant/` as the default runtime skill output directory.
- Treat `generated-skills/learning-profile.md` as the default learning profile output file.
- Keep the generated runtime skill focused on learning repositories, codebases, docs, architecture, and modules.
- Require the generated runtime skill to include a Codex invocation hint so the user knows how to use it after generation.
- Make the runtime skill proactive: ask likely hidden questions, build a roadmap, control pacing, and summarize progress after each step.
- Require every runtime response to contain these sections in order:
  `project map`, `current understanding`, `hidden questions`, `next best step`

## Self-Check Gates

Before finalizing the generated skill, verify all gates:

1. The builder produced a personalized skill and not a one-size-fits-all tutor.
2. The runtime skill behaves like a learning copilot rather than passive Q&A.
3. If history was provided, the generated runtime skill visibly reflects stable patterns from that history rather than only the latest follow-up answers.

If any gate fails, revise the learning profile and regenerate the runtime instructions with stronger profile-specific behaviors.
