# Adapter normalization layer

Shared, provider-agnostic normalization layer for every LLM call the skills
make. Skills never reference a model backend directly.

## Files
- `model-provider-adapter.md` — the interface the adapter must implement.
- `README.md`                — wiring guide (OpenRouter, local GGUF, ...).

## Contract (`model-provider-adapter.md`)

An adapter must expose a single callable:

    call(context: Context, system: str, messages: list[Message], params: Params)
    -> ModelResponse

with these guarantees:

1. **System prompt assembly** is provider-agnostic — the skill emits a plain
   string; the adapter handles how it is injected.
2. **Message shaping** (system/reasoning/user/tool) is normalized per
   provider so the skill never emits provider-specific message envelopes.
3. **Parameter mapping** — temperature, max_tokens, stop, repeat_penalty,
   reasoning effort, etc. are mapped to the provider's native equivalents.
4. **Response parsing** — text extraction is provider-agnostic.
5. **Fallback behavior** — a defined path when the primary backend is
   unreachable or returns an error the skill cannot interpret.
6. **Observability hook** — the adapter reports which provider handled the
   call, latency and token usage, so the evaluation harness can measure and
   compare backends without changing the skill.

## Skill context envelope

Skills emit a minimal `Context` so the adapter can adapt:

    { modality: voice | chat | email | async | audit | training,
      call_type: outbound-cold-calling | inbound-receptionist | ...,
      jurisdiction: ..., identity_anchor: ..., scope: ... }

The contract guarantees: **the same skill instruction produces identical
routing and safety behavior across all modalities and all supported backends.**
