## Purpose

`evmtx` is purposed to be a collection of primitive tools for EVM Transaction accounting against addresses, allowing use of specifications in other applications, binaries for micro-utility or entire environment for base accounting.

## Motive (and of implementation in rust)

evmtx is inspired by [trueblocks-core](https://github.com/TrueBlocks/trueblocks-core) and interfaces are largely to be a selective port from the same. However, following are the specific motives.

- Composability from existing type specifications and utilities through [ethers-rs](https://github.com/gakonst/ethers-rs)

- Highly concurrent consumption and creation of existing indexes (primarily [unchained index](https://unchainedindex.io/))

- Robust specifications for address accounting

- Portability to web and light mediums through modular compilation to wasm

- Usability though CLI, FFI, RPC, HTTP APIs

- Supporting rust ecosystem

- Enabling [glove](https://github.com/pintnetwork/glove) to achieve one of its desired set of UX

## Towards RPC recipes

A recipe is a code written in any language that can compile to wasm.

- Make validation to make sure it is indeed making only EVM RPC calls, this is tricky and bulk of implementation complexity

- Compile to wasm, this is intertwined with above, as it may be that we can perform validation on compiled wasm too

- 