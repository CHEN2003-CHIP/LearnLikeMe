# Learning Profile Schema

Normalize the intake into this profile. Use concise values plus short evidence notes pulled from the user's answers.

## Required Fields

```yaml
learning_profile:
  learner_label: ""
  primary_goal: ""
  evidence_sources: []
  stable_preferences: []
  situational_preferences: []
  project_scope:
    repo_learning: true
    codebase_learning: true
    docs_learning: true
    architecture_learning: true
    module_learning: true
  orientation_style:
    mode: "top-down | bottom-up | mixed"
    evidence: ""
  example_preference:
    mode: "examples-first | concepts-first | code-first | mixed"
    evidence: ""
  explanation_style:
    depth: "minimal | moderate | thorough"
    emphasis: "intuition | implementation | balanced"
    terminology: "plain-first | immediate | delayed"
    evidence: ""
  pacing:
    speed: "very-slow | steady | high-bandwidth"
    chunk_size: "tiny | small | medium | large"
    recap_frequency: "every-step | every-few-steps | complexity-triggered"
    evidence: ""
  questioning:
    check_in_style: "frequent | occasional | low-interruption"
    hidden_question_support: "high | medium | low"
    assumption_challenge: "early | gentle | only-when-risky"
    evidence: ""
  comprehension_limits:
    overload_triggers: []
    moving_parts_limit: ""
    overload_response: "slow-down | simplify | recap | switch-example | narrow-scope"
    evidence: ""
  progress_preferences:
    summary_style: "bullets | short-prose | running-mental-model"
    roadmap_expected: true
    end_of_step_preference: "recap | quiz | hidden-questions | concrete-action"
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

- Convert vague answers into one stable value per field and keep the original nuance in `evidence`.
- Record whether evidence came from `history`, `questionnaire`, or both in `evidence_sources`.
- Add repeated long-term habits to `stable_preferences`.
- Add repo-specific or task-specific signals to `situational_preferences`.
- Resolve contradictions explicitly. Example: if the user wants fast pace but also overloads easily, keep `speed: steady` and add an intervention trigger about slowing down when branching increases.
- Use `runtime_behavior.personalization_notes` to record the traits that must visibly change the generated runtime skill.
- The runtime skill must not sound generic if the profile contains strong preferences.

## Minimum Personalization Checks

Before using the schema to generate the runtime skill, confirm the profile changes at least these five behaviors:

1. Explanation depth
2. Teaching pace
3. Step size
4. Questioning cadence
5. End-of-step summary style
