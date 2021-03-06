# MPC Framework

![Unit tests](https://github.com/yvgny/MPC-Framework/workflows/Unit%20tests/badge.svg)

A multi-party computation framework written in Go using the [lattigo](https://github.com/ldsec/lattigo) library. It provides computation of arbitrary circuit over *N* parties in a semi-honest (passive) adversarial setting. The computations are done without trusted thrid party, using BFV fully homomorphic encryption scheme to generate an arbitrary number of Beaver triplets.

## Build

Clone the repo and compile using the go compiler:

```bash
go build
```

## Usage

The application can be given a circuit ID to show an example of how a computation is done. The implemented circuits are listed in `test_circuits.go`:

```bash
./mpc -id 1
```

It's also possible to disable the decentralized generation of beaver triplets using the flag `-c`. Instead, the triplet will be generated locally and given to each peer as parameters:

```bash
./mpc -c -id 7
```

## Testing

The whole test suite can be run using `go test`. Otherwise, each test circuit can be executed using the following command :

```bash
go test -v -run=ˆTestEval$/ˆcircuitX$
```

where *X* is replaced by the circuit ID of a circuit present in `test_circuits.go`.

Similarly, the benchmarks can be run with the command:
```bash
go test -run=XXX -bench=.
```
