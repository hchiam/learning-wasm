# Learning Web Assembly (WASM)

Just one of the things I'm learning. <https://github.com/hchiam/learning>

## [Run Wasm in localhost](https://github.com/hchiam/learning-wasm/tree/master/as#starting-from-my-repo):

Convert from AssemblyScript (kinda like TypeScript/JavaScript) to Wasm:

(See example in subfolder [`/as`](https://github.com/hchiam/learning-wasm/tree/master/as))

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

## Some general resources:

<details>
<summary>(click to expand)</summary>

- <https://www.youtube.com/watch?v=LNqicUieSqI>
- <https://mbebenita.github.io/WasmExplorer>
- <https://marketplace.visualstudio.com/items?itemName=dtsvet.vscode-wasm>
- <https://developer.mozilla.org/en-US/docs/WebAssembly/Using_the_JavaScript_API>
- <https://github.com/mdn/webassembly-examples>

</details>
