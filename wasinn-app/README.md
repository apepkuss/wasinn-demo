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
...

*** Performing inference ...
*** module_bin_name: mobilenet.pt
*** image_name: input.jpg
Read torchscript binaries, size in bytes: 14376860
*** [Step 1] load graph ...
         [Done] graph id: 0
*** [Step 2] init execution context ...
         [Done] execution context id: 0
*** [Step 3] set input to the inference engine ...
         read input tensor, size in bytes: 602112
         [Done]
*** [Step 4] perform inference ...
         [Done]
*** [Step 5] parse the inference result ...
         [Done]

*** the inference result ***
   1.) [954](20.6681)banana
   2.) [940](12.1483)spaghetti squash
   3.) [951](11.5748)lemon
   4.) [950](10.4899)orange
   5.) [953](9.4834)pineapple, ananas

...
```
