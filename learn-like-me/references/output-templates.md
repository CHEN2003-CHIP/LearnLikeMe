# Output Templates

Use these templates when producing the learning profile and generated runtime skill.

## 1. Learning Profile Output

````md
## Learning Profile

### Plain-Language Summary
- This learner is trying to: ...
- They learn best when: ...
- They struggle when: ...
- The assistant should adapt by: ...
- Stable preferences observed from history: ...
- Situational preferences observed from recent tasks: ...

### Structured Profile
```yaml
learning_profile:
  evidence_sources:
    - history
    - questionnaire
  stable_preferences:
    - ...
  situational_preferences:
    - ...
  ...
```
````

## 2. Generated Runtime Skill Output

```md
## Generated Skill

- Skill name: `project-learning-assistant`
- Personalization focus: ...
- Key behavior shifts from the template:
  - ...
  - ...
  - ...
- Evidence used:
  - stable pattern: ...
  - situational pattern: ...

### Files
- `project-learning-assistant/SKILL.md`
- `project-learning-assistant/agents/openai.yaml`
```

## 3. Runtime Response Contract

Every runtime response must end with these sections in this order:

```md
## project map
...

## current understanding
...

## hidden questions
...

## next best step
...
```

## 4. Review Gate Prompt

Use this final check before presenting the generated runtime skill:

```md
### Review Gates
1. Does this skill clearly adapt pace, depth, question style, and recap behavior to the learner profile?
2. Does it proactively surface hidden questions and drive a roadmap, rather than waiting as a passive Q&A bot?
3. If history was provided, does the generated skill reflect stable patterns from that history rather than only the latest questionnaire answers?
```
