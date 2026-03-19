# EPSO

Compiled on Linux x86_64 with CMake/make and GNU C++ 11.5.0.

The program `EPSO` contains three input parameters: `InsName Seed InsType`.

1) `InsName`: the name of each instance tested.
2) `Seed`: the random seed.
3) `InsType`: the type of each instance tested. There are only two candidate values:
   `1` for the Set I of 100 DCKP instances, `2` for the Set II of 6240 DCKP instances.

The cut-off time is computed by:

`T = clamp(1.5 * n, 60, 1000)`

where `n` is the number of items and `clamp(x, a, b) = max(a, min(x, b))`.

Keep the program and the benchmark instances in the same folder.

Then the job can be submitted as follows:

```bash
./EPSO InsName Seed InsType
```

For example:

```bash
./EPSO 1I1 0 1
```

The results are stored in a text file named:

`InsName_time_result`

The file content format is as follows:

```text
Instance: <InsName>
BestProfit: <profit>
BestWeight: <weight>
Time: <seconds>
All best combinations (same profit):
ItemIndexBase: <0 or 1>
Comb0: [ ... ] Profit=<profit> Weight=<weight>
...
```
