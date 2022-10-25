# WASI-NN Mobilenet App

This example illustrates an AI inference application. The application makes use of PyTorch Mobilenet model to perform object detection.

Different from the normal native AI inference applications, this AI inference application will be run in the WebAssembly mode:

* First, it will be compiled into a WebAssembly binary; and then,

* it will be loaded and run  as a WebAssembly module on WasmEdge Runtime via the WASI-NN interfaces. WasmEdge Runtime provides the support for the standard WASI-NN proposal.

## Environment Requirements

Please use Ubuntu-20.04+ to build this example.

## Build

Before build the application, please guarantee that the `wasm32-wasi` target has already been deployed in your build environment. To install the `wasm32-wasi` target, run the following command:

```bash
rustup target add wasm32-wasi
```

Now use the following command in the root directory of `wasinn-demo` to build the application into a WebAssembly file:

```bash
cargo build -p wasinn-mobilenet-app --target wasm32-wasi --release
```

If the build process is done successfully, a WebAssembly file named `wasinn-mobilenet-app.wasm` can be found in the `target/wasm32-wasi/release` directory.

## Next

The next step is to use the generated `wasinn-mobilenet-app.wasm` in the `wasinn-app` project.
