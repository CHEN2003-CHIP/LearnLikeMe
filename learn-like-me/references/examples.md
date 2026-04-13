# Examples

Use these as contrast checks. The generated runtime skill should shift tone, pacing, step size, and questioning behavior across these profiles.

## Example 1: Slow-Paced Beginner

### Intake Snapshot

- Goal: understand enough to make safe small edits
- Orientation: top-down first
- Example preference: examples before abstractions
- Pace: very slow
- Detail: moderate
- Questioning: frequent check-ins
- Overload trigger: too many files at once
- End-of-step preference: recap plus one concrete next action

### Normalized Profile Highlights

- `orientation_style.mode: top-down`
- `pacing.speed: very-slow`
- `pacing.chunk_size: tiny`
- `questioning.check_in_style: frequent`
- `comprehension_limits.overload_response: narrow-scope`
- `progress_preferences.summary_style: short-prose`
- `runtime_behavior.roadmap_granularity: micro`
- `runtime_behavior.proactive_questioning_level: high`

### Expected Runtime Behavior

- Start with a gentle mental map before naming many files.
- Teach one component boundary at a time.
- Recap after every step.
- Surface hidden questions like "which file should I ignore for now?" and "what can I safely postpone?"

## Example 2: Question-Driven Intermediate

### Intake Snapshot

- Goal: become productive in an unfamiliar codebase
- Orientation: mixed
- Example preference: concept plus code together
- Pace: steady
- Detail: moderate to thorough
- Questioning: wants the assistant to surface likely questions
- Overload trigger: architecture talk with no concrete trace
- End-of-step preference: hidden questions list

### Normalized Profile Highlights

- `orientation_style.mode: mixed`
- `example_preference.mode: mixed`
- `pacing.speed: steady`
- `pacing.chunk_size: small`
- `questioning.hidden_question_support: high`
- `explanation_style.emphasis: balanced`
- `progress_preferences.end_of_step_preference: hidden-questions`
- `runtime_behavior.intervention_triggers: ["too much abstraction without code anchors"]`

### Expected Runtime Behavior

- Alternate between project map and concrete path tracing.
- Surface likely questions before blockers appear.
- Use checkpoints like "do you want to stay at the architecture layer or trace one request end-to-end?"
- Keep the roadmap visible and update it as uncertainty narrows.

## Example 3: High-Bandwidth Advanced Learner

### Intake Snapshot

- Goal: reach deep ownership fast
- Orientation: bottom-up with architecture synthesis
- Example preference: code first
- Pace: high-bandwidth
- Detail: thorough
- Questioning: low interruption unless risk is high
- Overload trigger: repetitive basics
- End-of-step preference: compressed current state plus next leverage point

### Normalized Profile Highlights

- `orientation_style.mode: bottom-up`
- `example_preference.mode: code-first`
- `pacing.speed: high-bandwidth`
- `pacing.chunk_size: large`
- `questioning.check_in_style: low-interruption`
- `questioning.assumption_challenge: early`
- `progress_preferences.summary_style: bullets`
- `runtime_behavior.roadmap_granularity: compressed`
- `runtime_behavior.proactive_questioning_level: medium`

### Expected Runtime Behavior

- Move quickly into request paths, ownership boundaries, and failure modes.
- Skip gentle onboarding language unless confusion is detected.
- Surface hidden questions like "which abstractions leak?" and "where does state actually become authoritative?"
- Summarize aggressively and push to the next leverage point.
