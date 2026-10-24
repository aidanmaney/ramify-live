# ramify-live

Lean 4 (v4.32.2) compiled to WebAssembly, hosted for the live tier of the
[Ramify playground](https://aidanmaney.github.io/ramify-lean4/playground.html)
("Run real Lean"). This repository holds build output only; the source, the
build recipe and the patches are in
[aidanmaney/ramify-lean4](https://github.com/aidanmaney/ramify-lean4)
(`scripts/wasm/`, `docs/wasm-spike.md`).

| File | What it is |
|---|---|
| `live.wasm.gz` | Lean's runtime and the playground's stepping code, compiled with Emscripten (gzip) |
| `init.tar.gz` | Lean's `Init` library as 32-bit `.olean`s (gzip) |
| `live.js`, `live.worker.js` | Emscripten's loader and its pthread worker |
| `worker.js` | The playground's Web Worker: downloads, caches and drives the engine |
| `manifest.json` | Version (a content hash) and sizes; the page reads it |

Lean is licensed under the Apache License 2.0 (`LICENSE-LEAN`; third-party
notices in `LICENSES-LEAN/`). The build applies the patches recorded in
`scripts/wasm/recipe/` of the Ramify repository.
