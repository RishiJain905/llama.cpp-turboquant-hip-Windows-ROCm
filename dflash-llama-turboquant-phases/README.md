# DFlash-style llama.cpp + TurboQuant Integration Plan

This pack is built around your current base:

- Repo: `RishiJain905/llama.cpp-turboquant-hip-Windows-ROCm`
- Branch: `feature/turboquant-hip-port-clean`
- Current working stack: Windows + AMD HIP/ROCm + llama.cpp + GGUF + FlashAttention + TurboQuant KV compression
- Future goal: investigate whether DFlash-style speculative decoding can be added on top of that stack.

## Important framing

This is **not** claiming a clean full DFlash port on day one.

The correct research framing is:

> Build a benchmark-first experimental path for DFlash-inspired speculative decoding in a llama.cpp TurboQuant fork, then gradually move from existing llama.cpp speculative decoding to an actual DFlash draft-model integration.

## Why there are 4 phases

1. **Phase 1** proves the current repo, build, flags, and benchmark harness are solid.
2. **Phase 2** maps llama.cpp speculative decoding and adds stronger measurement.
3. **Phase 3** creates a DFlash-style integration boundary without needing full DFlash model support immediately.
4. **Phase 4** attempts actual DFlash draft-model support, optimization, and public GitHub packaging.

## Repo-aware notes from inspection

The branch has the normal llama.cpp layout, including key areas such as:

- `examples/speculative`
- `docs/speculative.md`
- `common`
- `include`
- `src`
- `ggml`
- `tools`
- `tests`

The `examples/speculative` folder contains `CMakeLists.txt`, `README.md`, and `speculative.cpp`.

The branch documentation says `llama-server` supports speculative decoding, including draft-model and draftless n-gram implementations. That is the main reason this plan starts by using existing speculative machinery before designing a DFlash-specific path.

## Suggested execution style

Use separate git branches or worktrees:

```bash
git checkout feature/turboquant-hip-port-clean

git checkout -b phase-1-benchmark-baseline
git checkout -b phase-2-spec-map
git checkout -b phase-3-dflash-interface
git checkout -b phase-4-dflash-model-support
```

For every task:

1. Make the smallest possible change.
2. Build.
3. Run at least one benchmark.
4. Save results.
5. Commit with a clear message.
6. Update that phase's `progress.md`.
