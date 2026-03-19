# EPSO

Single-instance runner for two DCKP benchmark sets.

Compiled on Linux x86_64 with CMake/make and GNU C++ 11.5.0.

## Run

Keep the executable and the benchmark instance files in the same folder (run from that folder).

```bash
./EPSO InsName Seed InsType
```

- `InsName`: instance filename (no need to provide full path).
- `Seed`: seed input (printed as provided).
- `InsType`: `"1"` for Set I (100 instances), `"2"` for Set II (6240 instances).

Cut-off time formula (seconds), where `n` is the number of items:

`T = clamp(1.5 * n, 60, 1000)`

(`clamp(x, a, b) = max(a, min(x, b))`)

## Output

The program creates exactly one output file in the current folder:

`<InsName>_<time>_<result>`

File content format:

```
Instance: <InsName>
BestProfit: <profit>
BestWeight: <weight>
Time: <seconds>
All best combinations (same profit):
ItemIndexBase: <0 or 1>
Comb0: [ ... ] Profit=<profit> Weight=<weight>
...
```

## Reproducibility

For the strongest reproducibility, build and run on the same platform/toolchain.

Different platforms or standard library implementations may produce different search paths and final results, even with the same input seed, because the program depends on floating-point calculations and C++ random distributions whose exact behavior is not guaranteed to be identical across toolchains.
