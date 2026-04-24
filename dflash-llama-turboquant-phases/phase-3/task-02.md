# Task 02 - Draft provider interface

## Objective

Create a small internal abstraction for a draft provider that returns a candidate token block and metadata such as block size, confidence, and timing.

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
phase-3: task 02 - draft provider interface
```
