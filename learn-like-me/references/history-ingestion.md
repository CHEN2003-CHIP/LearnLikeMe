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

- `preferences.md`: explicit user notes such as "I prefer top-down explanations"
- `context.md`: project or role context such as "I usually learn backend repos"

If the environment does not contain this exact folder, use any user-provided Markdown path, but prefer the convention above for repeatability across users.

## Ingestion Goal

Infer the learner's actual behavior from real conversations before asking questions. The builder should reduce questionnaire length when the history already provides strong evidence.

## Signals to Extract

Map historical evidence into the learning profile by looking for repeated patterns such as:

- requests for top-down overview vs bottom-up tracing
- requests for concrete call chains, files, methods, parameters, or examples
- requests for slower pacing, smaller chunks, or more recap
- phrases that indicate overload: "too abstract", "hard to follow", "do not expand yet", "too much at once"
- phrases that indicate desired structure: "start with the conclusion", "overall picture first", "give me a timeline", "step by step"
- whether the user asks many follow-up questions or relies on the assistant to surface likely next questions
- whether the user values directness, roadmap summaries, diagrams, timelines, or implementation detail

## Stable vs Situational Preferences

Separate long-term habits from one-off task needs.

- Stable preference: appears repeatedly across sessions or in explicit corrections, and should shape the generated runtime skill by default.
- Situational preference: appears tied to one repo, one debugging task, or one document type, and should be kept as context rather than promoted to a permanent teaching rule.

Examples:

- Stable: "start with the big picture before deep tracing"
- Stable: "explanations should stay detailed but easy to follow"
- Situational: "for this repo, include classes, methods, and parameters in full detail"
- Situational: "for rewind logic, focus on command dispatch instead of tools"

## Confidence Rules

Treat a preference as high confidence when:

- it appears multiple times across conversations, or
- the user explicitly corrects the assistant toward that preference, or
- the same pattern appears in both the user's request wording and the assistant responses that the user accepts

Treat a preference as low confidence when:

- it appears only once,
- it may be specific to one project rather than the learner generally, or
- there is conflicting evidence elsewhere in the history

## Recommended Builder Flow

1. Read all Markdown files from `<workspace>/learn-like-me-input/history/`.
2. Extract repeated preference signals and attach short evidence quotes or paraphrases to schema fields.
3. Classify each signal as stable or situational.
4. Pre-fill the learning profile.
5. Ask only targeted follow-up questions for missing, contradictory, or low-confidence fields.
6. Show the inferred profile in plain language and invite corrections.
7. Generate `project-learning-assistant` from the corrected profile.

## What This Improves

- less repetitive intake for the user
- more realistic personalization based on observed behavior
- better portability because every user can follow the same drop-folder convention
- easier automation later if the builder is extended with scripts or import tooling

## Important Boundaries

- Do not assume one project-specific preference applies globally without enough evidence.
- Separate stable learning habits from one-off task requirements.
- Prefer asking one short confirmation question over hard-coding a shaky inference.
