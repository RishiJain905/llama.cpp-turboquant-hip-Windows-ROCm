# Task 05 - Native ggml prototype option

## Objective

If conversion looks realistic, begin a native ggml/llama.cpp draft model loader path with minimal model support.

## Why this matters

This task moves the project toward a benchmark-first DFlash-style speculative decoding experiment on top of your existing llama.cpp TurboQuant + FlashAttention stack.

## Suggested files / areas to inspect

- `docs/speculative.md`
- `examples/speculative/`
- `common/`
- `include/`
- `src/`
- `ggml/`
- `tests/`
- `benches/`

Use the relevant subset only. Do not touch unrelated areas unless the task clearly requires it.

## Work steps

1. Read the relevant existing files.
2. Write down the current behavior before changing anything.
3. Make the smallest useful change or report.
4. Build the project.
5. Run a controlled test.
6. Save results in the phase folder.
7. Update `progress.md`.

## Acceptance criteria

- [ ] The task output exists as code, script, benchmark data, or a Markdown report.
- [ ] The result is reproducible.
- [ ] Any assumptions are written down.
- [ ] The build is not broken.
- [ ] The phase progress file is updated.

## Commit message idea

```text
phase-4: task 05 - native ggml prototype option
```
