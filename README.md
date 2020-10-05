# Learning Web Assembly (WASM)

Just one of the things I'm learning. <https://github.com/hchiam/learning>

## Run Wasm in localhost:

**Very high-level summary:** Wasm <-- can be built from AssemblyScript (which looks very much like TypeScript/JavaScript).

**Conceptual code "flow":** index.html <-- demo.js <-- build/optimized.wasm <-- (built from assembly/index.ts using [`asc`](https://github.com/hchiam/learning-wasm/blob/master/as/package.json#L8)).

Just run this one line of code in CLI: (triple click to select all)

```bash
git clone https://github.com/hchiam/learning-wasm.git && cd learning-wasm && cd as && yarn && yarn go
```

## Or starting from scratch:

```bash
mkdir example-assemblyscript
cd example-assemblyscript
npm init -y
yarn add @assemblyscript/loader
yarn --dev add assemblyscript static-server
npx asinit .
# add "start": "open http://localhost:9080; static-server" in package.json
# (edit /assembly/index.ts and in asconfig.json and then continue:)
touch demo.js index.html
# fill in demo.js and index.html with something like that in this repo sub-folder
```

and then from then on:

```bash
yarn asbuild
yarn start # open http://localhost:9080; static-server
```

## More info on AssemblyScript --> Wasm:

<details>
<summary>(click to expand)</summary>

- `./assembly`: Directory holding the AssemblyScript sources being compiled to WebAssembly.
- `./assembly/tsconfig.json`: TypeScript configuration inheriting recommended AssemblyScript settings.
- `./assembly/index.ts`: Example entry file being compiled to WebAssembly to get you started.
- `./build`: Build artifact directory where compiled WebAssembly files are stored.
- `./build/.gitignore`: Git configuration that excludes compiled binaries from source control.
- `./index.js`: Main file loading the WebAssembly module and exporting its exports.
- `./tests/index.js`: Example test to check that your module is indeed working.
- `./asconfig.json`: Configuration file defining both a 'debug' and a 'release' target.
- `./package.json`: Package info containing the necessary commands to compile to WebAssembly.
- <https://www.assemblyscript.org>
- <https://github.com/AssemblyScript/assemblyscript>
- <https://www.assemblyscript.org/quick-start.html>
- <https://wasmbyexample.dev/examples/hello-world/hello-world.assemblyscript.en-us.html>
- This tutorial finally got it working for me: <https://blog.logrocket.com/the-introductory-guide-to-assemblyscript> and <https://github.com/dguo/assemblyscript-demo>

</details>

<hr>

## [`example.wasm`](https://github.com/hchiam/learning-wasm/blob/master/example.wasm) (when you use a VS Code extension to convert from binary):

```wasm
(module
  (type $t0 (func (param i32 i32) (result i32)))
  (func $_Z3addii (type $t0) (param $p0 i32) (param $p1 i32) (result i32)
    local.get $p1
    local.get $p0
    i32.add)
  (table $T0 0 funcref)
  (memory $memory 1)
  (export "memory" (memory 0))
  (export "_Z3addii" (func $_Z3addii)))
```

## More links to general resources:

<details>
<summary>(click to expand)</summary>

- <https://www.youtube.com/watch?v=LNqicUieSqI>
- <https://mbebenita.github.io/WasmExplorer>
- <https://marketplace.visualstudio.com/items?itemName=dtsvet.vscode-wasm>
- <https://developer.mozilla.org/en-US/docs/WebAssembly/Using_the_JavaScript_API>
- <https://github.com/mdn/webassembly-examples>

</details>
