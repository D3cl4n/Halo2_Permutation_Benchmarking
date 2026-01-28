# Poseidon and Rescue-Prime Permutation Benchmarking in Halo2

## Summary 

We implement a shared circuit construction for the Poseidon and Rescue-Prime permutations: POSEIDON^π and Rescue-XLIX. The shared construction provides a skeleton of common parameters and functionality, thus controlling confounding variables during benchmarking. Each permutation builds on the shared construction, completing its functionality. Our comparative analysis of the low-level circuit metrics highlights design differences between the permutations. We analyze how these design differences affect low-level circuit metrics in Halo 2 PLONKish circuits. 

## Common Parameters for Both Circuits
1) Underlying field: `BLS12-381`
2) State size: `m=3`
3) Security level: `128 bits`
4) Total rows: `2^k` with `k=10`
5) Advice columns: `3`
6) Fixed columns: `3`
7) Instance columns: `1`
8) Chips per permutation: `1`
9) ARC gates and constraints
10) ML gates and constraints

## Software Versions
1) OS: `Ubuntu 22.04.4 (in WSL2)`
2) rustc version: `1.87.0`
3) Kernel: `x86_64 Linux 6.6.87.2-microsoft-standard-WSL2`
4) halo2\_proofs: `0.3.1`
5) halo2curves: `0.9.0`
6) num-bigint: `0.4`

## Running the Code
Execute `cargo run` from the repository's top-level directory. 

## Disclaimer
This work does not introduce new cryptographic constructions or security results. Its contribution is an empirical evaluation, and comparative analysis, of existing arithmetic hash permutations in a shared Halo2 circuit construction. Because this work is intended solely for benchmarking, the code is not designed for a production deployment.