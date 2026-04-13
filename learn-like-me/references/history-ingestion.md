# History Ingestion

Use this workflow when a user wants to generate a personalized learning assistant from prior chat history instead of answering the full intake from scratch.

## Recommended Drop Location

Use a fixed folder next to the `learn-like-me/` skill folder:

```text
<workspace>/
|- learn-like-me/
`- learn-like-me-input/
   |- history/
   |  |- chat-1.md
   |  |- chat-2.md
   |  `- ...
   |- preferences.md
   `- context.md
```

Minimum supported input:

- one or more Markdown chat exports in `<workspace>/learn-like-me-input/history/`

Optional supporting files:

- `preferences.md`: explicit learner notes such as "I prefer top-down explanations"
- `context.md`: role or project context such as "I usually learn backend repos"

## Ingestion Goal

Infer the learner's actual behavior from real conversations before asking questions. The builder should reduce questionnaire length when the history already provides strong evidence.

## Minimum Extraction Checklist

Extract and evaluate evidence for these dimensions from chat logs:

- orientation style
- explanation depth
- pacing and chunk size
- preferred structure
- overload triggers
- question style
- summary style
- preferred evidence type
- hidden-question tolerance

## Evidence Model

For each important preference signal, capture:

- `signal`
- `confidence`: `high | medium | low`
- `evidence`: a short excerpt or paraphrase
- `classification`: `stable | situational`
- `affected_runtime_behavior`

## Conflict Resolution

When history suggests mixed preferences:

1. Prefer repeated behavior over a single explicit claim.
2. Prefer recent evidence only when it clearly looks like a stable correction rather than a one-off task constraint.
3. If two plausible interpretations remain, keep the safer default in the profile and ask one narrowly scoped follow-up question.
4. Record the conflict in the evidence notes instead of hiding it.

## Insufficient Evidence Rule

Do not guess on thin evidence. If a field materially affects runtime behavior and history support is weak, ask a targeted follow-up question only for that field.

## Recommended Builder Flow

1. Read all Markdown files from `<workspace>/learn-like-me-input/history/`.
2. Extract repeated preference signals and attach evidence to schema fields.
3. Classify each signal as stable or situational.
4. Assign confidence to each major signal.
5. Pre-fill the learning profile.
6. Ask only targeted follow-up questions for missing, contradictory, or low-confidence fields.
7. Show the inferred profile in plain language and invite corrections.
8. Generate `project-learning-assistant` from the corrected profile.
9. Write outputs to `generated-skills/project-learning-assistant/` and `generated-skills/learning-profile.md` by default.

## Important Boundaries

- Do not assume one project-specific preference applies globally without enough evidence.
- Separate stable learning habits from one-off task requirements.
- Prefer asking one short confirmation question over hard-coding a shaky inference.
- Keep the repo optimized for Codex use of local files; generic ChatGPT-direct installation is out of scope for this iteration.
