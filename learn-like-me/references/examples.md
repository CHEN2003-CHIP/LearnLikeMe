# Examples

Use these as contrast checks. The generated runtime skill should shift tone, pacing, step size, questioning behavior, and visible structure across these profiles.

## Example 1: Slow-Paced Beginner

### Raw Chat History Signals

- "Please explain it slowly."
- "Start from the big picture."
- "Too many files at once makes me lose track."

### Inferred Profile Highlights

- `orientation_style.mode: top-down`
- `orientation_style.confidence: high`
- `pacing.speed: very-slow`
- `pacing.chunk_size: tiny`
- `questioning.check_in_style: frequent`
- `comprehension_limits.overload_response: narrow-scope`
- `progress_preferences.summary_style: short-prose`
- `runtime_behavior.roadmap_granularity: micro`
- `runtime_behavior.proactive_questioning_level: high`

## Example 2: Question-Driven Intermediate

### Raw Chat History Signals

- "Show me the full flow, then we can trace the code."
- "What am I probably missing here?"
- "Do not stay too abstract."

### Inferred Profile Highlights

- `orientation_style.mode: mixed`
- `example_preference.mode: mixed`
- `pacing.speed: steady`
- `pacing.chunk_size: small`
- `questioning.hidden_question_support: high`
- `explanation_style.emphasis: balanced`
- `progress_preferences.end_of_step_preference: hidden-questions`

## Example 3: High-Bandwidth Advanced Learner

### Raw Chat History Signals

- "Skip the basics."
- "Go straight to the ownership boundaries and failure modes."
- "I prefer code first."

### Inferred Profile Highlights

- `orientation_style.mode: bottom-up`
- `example_preference.mode: code-first`
- `pacing.speed: high-bandwidth`
- `pacing.chunk_size: large`
- `questioning.check_in_style: low-interruption`
- `questioning.assumption_challenge: early`

## Example 4: History to Skill Transition

### Raw Chat History

- "Start with the conclusion."
- "Then show me the classes, methods, and parameters."
- "I want the full flow, but make it easy to follow."
- "Also tell me what I am likely to ask next."

### Inferred Profile

- stable preference: conclusion-first structure
- stable preference: code-anchored detail
- stable preference: deep but structured explanations
- stable preference: high hidden-question support

### Codex Invocation

```text
Use generated-skills/project-learning-assistant to help me learn this repository.
Start with a project map, then guide me step by step.
```
