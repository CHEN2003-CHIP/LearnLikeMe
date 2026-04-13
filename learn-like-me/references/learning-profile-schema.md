# Learning Profile Schema

Normalize the intake and history evidence into this profile. Use concise values plus short evidence notes.

## Required Fields

```yaml
learning_profile:
  learner_label: ""
  primary_goal: ""
  evidence_sources: []
  stable_preferences: []
  situational_preferences: []
  evidence_signals:
    - signal: ""
      confidence: "high | medium | low"
      evidence: ""
      classification: "stable | situational"
      affected_runtime_behavior: []
  project_scope:
    repo_learning: true
    codebase_learning: true
    docs_learning: true
    architecture_learning: true
    module_learning: true
  orientation_style:
    mode: "top-down | bottom-up | mixed"
    confidence: "high | medium | low"
    evidence: ""
  example_preference:
    mode: "examples-first | concepts-first | code-first | mixed"
    preferred_evidence_type: "files | call-chains | examples | diagrams-in-words | balanced"
    confidence: "high | medium | low"
    evidence: ""
  explanation_style:
    depth: "minimal | moderate | thorough"
    emphasis: "intuition | implementation | balanced"
    terminology: "plain-first | immediate | delayed"
    preferred_structure: "conclusion-first | gradual-build | code-first | mixed"
    confidence: "high | medium | low"
    evidence: ""
  pacing:
    speed: "very-slow | steady | high-bandwidth"
    chunk_size: "tiny | small | medium | large"
    recap_frequency: "every-step | every-few-steps | complexity-triggered"
    confidence: "high | medium | low"
    evidence: ""
  questioning:
    check_in_style: "frequent | occasional | low-interruption"
    hidden_question_support: "high | medium | low"
    assumption_challenge: "early | gentle | only-when-risky"
    confidence: "high | medium | low"
    evidence: ""
  comprehension_limits:
    overload_triggers: []
    moving_parts_limit: ""
    overload_response: "slow-down | simplify | recap | switch-example | narrow-scope"
    confidence: "high | medium | low"
    evidence: ""
  progress_preferences:
    summary_style: "bullets | short-prose | running-mental-model"
    roadmap_expected: true
    end_of_step_preference: "recap | quiz | hidden-questions | concrete-action"
    confidence: "high | medium | low"
    evidence: ""
  constraints:
    time_pressure: "low | medium | high"
    confidence_support: ""
    avoid_patterns: []
  runtime_behavior:
    roadmap_granularity: "micro | standard | compressed"
    proactive_questioning_level: "high | medium | low"
    intervention_triggers: []
    personalization_notes: []
```

## Synthesis Rules

- Convert vague answers into one stable value per field and keep the nuance in `evidence`.
- Record whether evidence came from `history`, `questionnaire`, or both in `evidence_sources`.
- Add repeated long-term habits to `stable_preferences`.
- Add repo-specific or task-specific signals to `situational_preferences`.
- Populate `evidence_signals` for major behavior-shaping preferences, not only the final normalized fields.
- Resolve contradictions explicitly.
- Use `runtime_behavior.personalization_notes` to record the traits that must visibly change the generated runtime skill.
- The runtime skill must not sound generic if the profile contains strong preferences.

## Confidence Policy

- `high`: repeated evidence or explicit correction that clearly changes runtime behavior
- `medium`: plausible signal with enough context to shape defaults, but worth light caution
- `low`: insufficient support to lock a behavior without a follow-up question

If a field remains `low` and it materially changes runtime behavior, ask a narrow follow-up question instead of guessing.

## Minimum Personalization Checks

Before using the schema to generate the runtime skill, confirm the profile changes at least these behaviors:

1. Explanation depth
2. Teaching pace
3. Step size
4. Questioning cadence
5. End-of-step summary style
6. Preferred explanation structure
7. Hidden-question behavior
