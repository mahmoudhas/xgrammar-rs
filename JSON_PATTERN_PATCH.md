# Temporary JSON-pattern safety pin

This branch is xgrammar-rs **v0.5.1** (`2b7126f`) with unchanged Rust bindings.
Only the native submodule URL/revision changes, plus this note:

- Native base: `82505d0d987c36a4209fb3d8571cf6b0f28b5acd`.
- Native patch: `72f14e5a7815f47aa5367a2d7d8db4bbd3616cf3`.
- Upstream proposal: https://github.com/mlc-ai/xgrammar/pull/986.

The patch keeps Unicode JSON string patterns on the JSON-safe FSM path and
rejects empty/unsupported canonical pattern languages instead of falling back
to an unescaped CFG. Escaped-only patterns now fail compilation rather than
allowing malformed JSON. Raw regex behavior is unchanged. Keep independent
output validation enabled.

Consumers should pin the binding fork by an immutable git revision. Replace
this temporary fork with an upstream release after the native change is
accepted and the binding submodule is updated; do not track the fork's branch.
