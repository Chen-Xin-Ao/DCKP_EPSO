EPSO

EPSO is an enhanced particle swarm optimization algorithm for the disjunctively constrained knapsack problem (DCKP).

The executable was compiled on Linux x86_64 using CMake/make and GNU C++ 11.5.0. The corresponding C++ source code is provided in DCKP_EPSO_Program.zip.

Usage

The program EPSO requires three input parameters:

InsName Seed InsType

InsName: name or path of the benchmark instance.
Seed: random seed used for the run.
InsType: benchmark-set identifier, where 1 denotes Set I (100 instances) and 2 denotes Set II (6240 instances).

The cutoff time is

T = min(1.5 * n, 1000) seconds for Set I,

T = min(1.5 * n, 600) seconds for Set II,

where n is the number of items.

The program can be executed as:

./EPSO InsName Seed InsType

For example:

./EPSO 2I2 0 1
./EPSO BPPC_1_0_1.txt_0.1 0 2

The two instance files 2I2 and BPPC_1_0_1.txt_0.1 are included as examples for Set I and Set II, respectively.

Output

The result is written to a text file named

InsName_time_result

with the following information:

Instance: <InsName>
BestProfit: <profit>
BestWeight: <weight>
Time: <seconds>
All best combinations (same profit):
ItemIndexBase: <0 or 1>
Comb0: [ ... ] Profit=<profit> Weight=<weight>
...
Source code ：DCKP_EPSO_Program.zip



EPSO_DCKP6340sol_certificates.zip contains the released solution certificates for the benchmark instances.

epso_certificate_validator.zip provides the validation program for independently checking the objective values, total weights, and conflict feasibility of the released solutions.

License

The source code is released under the MIT License.
