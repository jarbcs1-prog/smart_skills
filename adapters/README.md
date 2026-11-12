# Wiring guide

The adapter layer is a single shared component. Each skill receives it through
the skill loader — one line — and never touches a model backend itself.

## How a skill fits

1. The skill defines `name`, `description` (trigger clauses), hard gates and a
   router in `SKILL.md`.
2. The skill emits a `Context` envelope (see CONTRACT.md §4).
3. The skill loader resolves the adapter and calls `adapter.call(context, ...)`.
4. The adapter normalizes the call and returns a `ModelResponse` with text.

### Wiring steps

1. Place the adapter under `adapters/` (this folder).
2. Create an adapter implementation for each backend (OpenRouter, local GGUF,
   ...). It must satisfy the `model-provider-adapter.md` contract.
3. In the skill loader, register the active adapter and thread it through the
   skill invocation path.
4. Verify with the evaluation harness: two backends, one skill, identical
   routing and safety behavior across two contexts.

## File layout

```
smart_skills/
├── CONTRACT.md                       # skill interface contract
├── adapters/
│   ├── README.md                     # wiring guide
│   └── model-provider-adapter.md     # adapter contract
└── <skill>/
    ├── SKILL.md                      # router + hard gates + context adapters
    ├── references/                   # depth files, loaded on demand
    ├── chapters/                     # depth files, loaded on demand
    └── templates/                    # snippets (optional)
```
