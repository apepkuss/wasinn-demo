# WASI-NN App

This example demonstrates how to use WasmEdge Rust SDK to load, register and run a AI inference application via the WASI-NN interface. The application performs the object detection task. It is compiled into a WebAssembly binary instead of native form.

## Environment Requirements

Please use Ubuntu-20.04+ to build this example.

## Build & Run

> Assume that the WebAssembly binary `wasinn-mobilenet-app.wasm` has already generated. For how to get it, go to the `wasinn-mobilenet-app` project and refer to the README file.

To build and run the example, go into the directory of `wasinn-app` and then simply run the following command:

```bash
cargo run wasinn-mobilenet-app.wasm mobilenet.pt input.jpg
```

If the command runs successfully, the following message will be printed on the screen:

```bash
```
