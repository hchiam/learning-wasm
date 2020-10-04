# Go from AssemblyScript (kinda like TypeScript/JavaScript) to Wasm:

- <https://www.assemblyscript.org>
- <https://github.com/AssemblyScript/assemblyscript>
- <https://www.assemblyscript.org/quick-start.html>
- <https://wasmbyexample.dev/examples/hello-world/hello-world.assemblyscript.en-us.html>

```bash
npm init
yarn add @assemblyscript/loader assemblyscript
npx asinit .
# (edit stuff in /assembly and in asconfig.json and then continue:)
yarn asbuild
```

<detail>
<summary>Non-essential notes, just in case:</summary>

- `./assembly`: Directory holding the AssemblyScript sources being compiled to WebAssembly.
- `./assembly/tsconfig.json`: TypeScript configuration inheriting recommended AssemblyScript settings.
- `./assembly/index.ts`: Example entry file being compiled to WebAssembly to get you started.
- `./build`: Build artifact directory where compiled WebAssembly files are stored.
- `./build/.gitignore`: Git configuration that excludes compiled binaries from source control.
- `./index.js`: Main file loading the WebAssembly module and exporting its exports.
- `./tests/index.js`: Example test to check that your module is indeed working.
- `./asconfig.json`: Configuration file defining both a 'debug' and a 'release' target.
- `./package.json`: Package info containing the necessary commands to compile to WebAssembly.

</detail>