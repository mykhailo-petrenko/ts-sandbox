# TS Debug boilerplate

```
npm init -y
npm i -D typescript ts-node tsconfig-paths @types/node
```

Create `tsconfig.json`.

```
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "outDir": "out",
    "sourceMap": true,
    "baseUrl": "."
  }
}
```

launch.json for MSVSC
```
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug TS",
      "type": "pwa-node",
      "request": "launch",
      "runtimeArgs": [
        "-r",
        "ts-node/register",
        "-r",
        "tsconfig-paths/register"
      ],
      "program": "${file}",
      "console": "integratedTerminal",
      "skipFiles": [
        "<node_internals>/**"
      ],
      "outFiles": [
        "${workspaceFolder}/**/*.js",
        "!**/node_modules/**"
      ]
    }
  ]
}
```
