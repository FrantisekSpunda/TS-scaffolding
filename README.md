<h2 align="center">TypeScript skeleton</h2>
<p align="center">
  Intended for some Typescript testing projects. 
  <br><br>
  <strong align="center">This package is using TypeScript.</strong>
</p>

### Requirements 🧾

- node.js and npm
- nodemon `npm install nodemon --save-dev`
- ts-node `npm install ts-node --save-dev`

### Installation 🐱‍💻

Just clone this repository with git. Or you download.

```
git clone https://github.com/FrantisekSpunda/ts-skeleton.git
```

### Packages 📦

##### npm

- `typescript` - This skeleton is
- `@type/node` - We need this package for using Node.js with TypeScript

##### other - just optional

- `prettier` - Automatically format code same way.

### About

Project is configured for using NodeNext and CommonJS at same time. Just name `.cts` or `.cjs` files where you need use CommonJS.

In `package.json` you can find scripts that are using nodemon, so you must have installed nodemon and ts-node. All your code then put in a folder `src`.

Project is using JS like modules. So package.json is specified that.

```json
// 📦 package.json
{
  ...
  "type": "module",
  ...
}
```

Then we need to configure our TS for work with this modules. Ofcourse we want configure lot other stuffs.

```json
// 📄 tsconfig.json
{
  "compilerOptions": {
    // Set absolute path for TS.
    "baseUrl": "./src",
    // Define how TS is commpiled.NodeNext is for "type: module".
    // CommonJS is used for classic JS, where we are using "require" insted of "import".
    "module": "NodeNext",
    // Here we are specifi way, how we are importing code from other files.
    // With NodeNext we can use files .ts, .js for module"NodeNext" and use "import ... from ..."
    // and CommonJS for files .cts, .cjs and use classic JS with "require('...')"
    "moduleResolution": "NodeNext",
    // This specify version of JS into witch is commpiled.
    "target": "ES2022",
    // Compile JS back to TS for better debugging.
    "sourceMap": true,
    // Folder where we want to compile our TS.
    "outDir": "dist"
  },
  // Files that are commpiled.
  "include": ["src/**/*"]
}
```

Bcs of all our configuration we can use NodeNext and CommonJS at the same time.
