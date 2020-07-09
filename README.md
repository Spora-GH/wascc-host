[![crates.io](https://img.shields.io/crates/v/wascc-host.svg)](https://crates.io/crates/wascc-host)&nbsp;
![Rust build](https://github.com/wascc/wascc-host/workflows/Rust/badge.svg)&nbsp;
![license](https://img.shields.io/crates/l/wascc-host.svg)&nbsp;
[![documentation](https://docs.rs/wascc-host/badge.svg)](https://docs.rs/wascc-host)

# waSCC Host

The _WebAssembly Secure Capabilities Connector_ (waSCC) host library allows consumers to add actor modules, portable capability providers, and native capability providers to a single runtime host and provide each of those modules with their own unique, per-capability configuration. This allows actors to each have their own separate message broker subscriptions, key-value stores, HTTP server ports, etc.

For more information on concepts, architecture, and tutorials, check out [wascc.dev](https://wascc.dev).

## Examples

To run the examples, simply issue the following command (assuming you have the latest version of Rust installed) from the root `wascc-host` directory:

```
$ RUST_LOG=wascc_host=info cargo run --example [example name]
```

Where the example name is the name (without the `.rs`) of any of the examples in the examples folder.

**Pre-Requisites** - For the `subscriber` example, you will need an instance of [NATS](https://nats.io) running locally. For the `kvcounter` example, you will need **Redis** running locally on the default port.

**NOTE** - All of these examples use _native_ capability providers, and therefore utilize the linux dynamic libraries (`.so` files). To use these examples on a Mac, you will need to manully build Mac dynamic libraries (`.dylib` files) and modify the examples to read those files instead.

## waSCC on Kubernetes

Looking to deploy waSCC actors on Kubernetes? Check out the [krustlet](https://github.com/deislabs/krustlet) project.
