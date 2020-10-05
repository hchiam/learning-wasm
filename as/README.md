# Run WebAssembly in localhost

Wasm <-- AssemblyScript (kinda like TypeScript/JavaScript)

## Starting from my repo

Triple click to select all:

```bash
git clone https://github.com/hchiam/learning-wasm.git && cd learning-wasm && cd as && yarn && yarn go
```

## Starting from scratch

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

<details>
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
- <https://www.assemblyscript.org>
- <https://github.com/AssemblyScript/assemblyscript>
- <https://www.assemblyscript.org/quick-start.html>
- <https://wasmbyexample.dev/examples/hello-world/hello-world.assemblyscript.en-us.html>
- This tutorial finally got it working for me: <https://blog.logrocket.com/the-introductory-guide-to-assemblyscript> and <https://github.com/dguo/assemblyscript-demo>

</details>
