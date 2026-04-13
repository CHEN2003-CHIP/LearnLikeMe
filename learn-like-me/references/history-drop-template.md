# History Drop Template

Use this template when standardizing input for multiple users.

## Recommended Workspace Layout

Create the input folder at the same level as `learn-like-me/`:

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

## `preferences.md` Template

```md
# Preferences

- I usually want to learn: repositories / codebases / docs / architecture / modules
- My default goal: orientation / safe edits / debugging / feature work / ownership
- I prefer: top-down / bottom-up / mixed
- I like explanations that are: minimal / moderate / thorough
- I get overloaded by: ...
- I want end-of-step summaries to include: ...
```

## `context.md` Template

```md
# Context

- My role: ...
- The kinds of projects I usually learn: ...
- My time pressure is usually: low / medium / high
- Skills or technologies I already know well: ...
- Things I do not want the assistant to assume: ...
```

## Team Rollout Rule

If multiple people will use this builder, ask everyone to place their files under the sibling folder `learn-like-me-input/` with the same structure. This makes ingestion predictable and avoids ad hoc per-user instructions.
