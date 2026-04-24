# Source Notes

These are the main external facts this task pack is based on.

## Your llama.cpp TurboQuant fork

Repo branch inspected:

`https://github.com/RishiJain905/llama.cpp-turboquant-hip-Windows-ROCm/tree/feature/turboquant-hip-port-clean`

Repo structure observed:

- `.github`
- `benches`
- `common`
- `docs`
- `examples`
- `ggml`
- `include`
- `src`
- `tests`
- `tools`
- `vendor`
- top-level `CMakeLists.txt`, `README.md`, conversion scripts, etc.

Relevant speculative folder:

`examples/speculative`

Observed files:

- `CMakeLists.txt`
- `README.md`
- `speculative.cpp`

Relevant docs:

`docs/speculative.md`

Important doc idea:

- llama.cpp supports speculative decoding.
- Draft-model speculation uses a smaller draft model.
- Draftless speculative modes include n-gram cache/map/mod options.

## DFlash

Repo inspected:

`https://github.com/z-lab/dflash`

Important facts:

- DFlash is described as a lightweight block diffusion model for speculative decoding.
- It provides separate DFlash draft models for supported target models.
- Examples use a target model plus a separate DFlash draft model.
- DFlash examples currently show support through vLLM, SGLang, Transformers, and MLX.
- DFlash support in vLLM requires a nightly build according to the README.
