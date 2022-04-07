# IBC Test Framework

This repo is going to house a new IBC testing framework based on the following work:
- https://github.com/PeggyJV/sommelier/tree/main/integration_tests
- https://github.com/strangelove-ventures/horcrux/tree/main/test
- https://github.com/cosmos/relayer/tree/main/test

The goals are to support:
- [ ] Testing complex IBC interactions between arbitrary chains
- [ ] Testing multiple relayer implemenations
    - [ ] cosmos/relayer
    - [ ] hermes
    - [ ] tsrelayer
- [ ] Testing multiple versions of each chain and compatability of new versions

The tests will be run in `go test` and utilize docker to spin up complete chains and utilize only the chain docker images themseleves.

This repo will rely on images built from https://github.com/strangelove-ventures/heighliner

# How to test
0. get genesis file, e.g. `wget http://88.99.65.142/juno-96-dimi.zip`
1. build the correct binaries `go build`
2. execute all tests or a specific test of interest:
```
./ibc-test-framework test -s juno:v2.1.0 --src-chain-id juno-2 JunoConsesusTest`
```