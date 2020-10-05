# Go from AssemblyScript (kinda like TypeScript/JavaScript) to Wasm:

(If you're running from this repo directly, just do `npm install` and then `yarn asbuild && yarn start`)

```bash
npm init
yarn add @assemblyscript/loader
yarn --dev add assemblyscript static-server
npx asinit .
# add "start": "open http://localhost:9080; static-server" in package.json
# (edit /assembly/index.ts and in asconfig.json and then continue:)
touch demo.js index.html
```

and then from then on:

```bash
yarn asbuild
yarn start # open http://localhost:9080; static-server
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

- <https://www.assemblyscript.org>
- <https://github.com/AssemblyScript/assemblyscript>
- <https://www.assemblyscript.org/quick-start.html>
- <https://wasmbyexample.dev/examples/hello-world/hello-world.assemblyscript.en-us.html>
- This tutorial finally got it working for me: <https://blog.logrocket.com/the-introductory-guide-to-assemblyscript> and <https://github.com/dguo/assemblyscript-demo>

</detail>
