<div align="center">
  <img src="https://raw.githubusercontent.com/igorskyflyer/npm-tsconfig/main/media/tsconfig.png" alt="Icon of TSConfig" width="256" height="256">
  <h1>TSConfig</h1>
</div>

<blockquote align="center">Strict By Default • ES2024 • Node & Browser • Zero Config </blockquote>

<h4 align="center">
  🔧 Opinionated, reusable TSConfig base for modern TypeScript projects by igorskyflyer. 🧠
</h4>

<br>

## Table of Contents

- ✨ [**Features**](#features)
- 🕵🏼 [**Usage**](#usage)
- ⚙️ [**Implementation**](#implementation)
- 🎯 [**Motivation**](#motivation)
- 📝 [**Changelog**](#changelog)
- 🪪 [**License**](#license)
- 💖 [**Support**](#support)
- 🧬 [**Related**](#related)
- 👨🏻‍💻 [**Author**](#author)

<br>

## Features

- 🔧 Strict `TypeScript` rules enabled by default
- 📦 Separate configs for `Node` and `browser` environments
- 🎯 `ES2024` target - `modern` and future-ready
- 🗂️ Predefined `src/`, `dist/` and `test/` structure
- 🔍 Catches `unused` locals, parameters and implicit `any`
- 🗺️ `Source maps` and `declaration` maps included
- ⚡ `Zero-config` setup - extend and go

<br>

## Usage

Install it by executing any of the following, depending on the preferred package manager:

```bash
pnpm add -D @igorskyflyer/tsconfig
```

```bash
yarn add -D @igorskyflyer/tsconfig
```

```bash
npm i -D @igorskyflyer/tsconfig
```

<br>

Then extend the preferred config in `tsconfig.json`:

**Node (default):**
```jsonc
{
  "extends": "@igorskyflyer/tsconfig",
  "include": ["src/**/*"],
  "exclude": ["node_modules/**/*", "test/**/*", "dist/**/*"],
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist"
  }
}
```

**Node (explicit):**
```jsonc
{
  "extends": "@igorskyflyer/tsconfig/node",
  "include": ["src/**/*"],
  "exclude": ["node_modules/**/*", "test/**/*", "dist/**/*"],
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist"
  }
}
```

**Browser:**
```jsonc
{
  "extends": "@igorskyflyer/tsconfig/browser",
  "include": ["src/**/*"],
  "exclude": ["node_modules/**/*", "test/**/*", "dist/**/*"],
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist"
  }
}
```

**Base only:**
```jsonc
{
  "extends": "@igorskyflyer/tsconfig/base",
  "include": ["src/**/*"],
  "exclude": ["node_modules/**/*", "test/**/*", "dist/**/*"],
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist"
  }
}
```

>[!NOTE]
> `include`, `exclude`, `rootDir` and `outDir` are project-specific and must be defined locally.
>

<br>

## Implementation

All configs extend `base`, which defines the shared structure and strict rules.

### Base
```jsonc
{
  "compilerOptions": {
    "declaration": true,      // generate .d.ts files
    "declarationMap": true,   // generate .d.ts.map files
    "sourceMap": true,        // generate .js.map files
    "verbatimModuleSyntax": true, // enforce explicit import/export types
    "strict": true,               // enable all strict checks
    "noUnusedLocals": true,       // error on unused local variables
    "noUnusedParameters": true,   // error on unused function parameters
    "noImplicitAny": true,        // error on implicit 'any' types
    "noImplicitReturns": true,    // error on missing return statements
    "skipLibCheck": true,         // skip type-checking of .d.ts files
    "forceConsistentCasingInFileNames": true, // enforce consistent file casing
    "noEmitOnError": true         // skip emit if type errors exist
  }
}
```

### Node

Extends `base` and adds `Node` environment targeting:
```jsonc
{
  "extends": "./tsconfig.base.json",
  "compilerOptions": {
    "target": "ES2024",          // modern JS output
    "lib": ["ES2024"],           // modern built-in types
    "module": "NodeNext",        // Node ESM-compatible modules
    "moduleResolution": "NodeNext" // Node ESM module resolution
  }
}
```

### Browser

Extends `base` and adds `browser` environment targeting:
```jsonc
{
  "extends": "./tsconfig.base.json",
  "compilerOptions": {
    "target": "ES2024",                        // modern JS output
    "lib": ["ES2024", "DOM", "DOM.Iterable"],  // modern + DOM types
    "module": "ESNext",                        // bundler-compatible modules
    "moduleResolution": "Bundler"              // bundler module resolution
  }
}
```

<br>

## Motivation

Managing `TypeScript` configuration across multiple projects is tedious and error-prone. Each project ends up with its own `tsconfig.json`, slightly different, slightly outdated, with no single source of truth.

`@igorskyflyer/tsconfig` solves this by providing one opinionated, versioned config that propagates across all projects via a simple `extends`. *Update once, apply everywhere* - just like all packages of the `@igorskyflyer` ecosystem do!

<br>

## Changelog

Read about the latest changes in the [**CHANGELOG**](https://github.com/igorskyflyer/npm-tsconfig/blob/main/CHANGELOG.md).

<br>

## License

Licensed under the [**MIT license**](https://github.com/igorskyflyer/npm-tsconfig/blob/main/LICENSE).

<br>

## Support

<div align="center">
  Engineering and documenting open-source projects<br>
  involves a significant investment of time.
  <br><br>
  If this project or its implementation has provided value,<br>
  support is greatly appreciated.
  <br><br>
  <a href="https://ko-fi.com/igorskyflyer" target="_blank"><img src="https://raw.githubusercontent.com/igorskyflyer/igorskyflyer/main/assets/ko-fi.png" alt="Donate to igorskyflyer" width="180" height="46"></a>
  <br><br>
  <em>Thank you for supporting these efforts!</em> 🙏😊
</div>

<br>

## Related

[**@igorskyflyer/duoscribi**](https://www.npmjs.com/package/@igorskyflyer/duoscribi)

> _✒ DúöScríbî allows you to convert letters with diacritics to regular letters. 🤓_

<br>

[**@igorskyflyer/zep**](https://www.npmjs.com/package/@igorskyflyer/zep)

> _🧠 Zep is a zero-dependency, efficient debounce module. ⏰_

<br>

[**@igorskyflyer/common-types**](https://www.npmjs.com/package/@igorskyflyer/common-types)

> _🔦 Provides frequently used types for your TypeScript projects. 🦄_

<br>

[**@igorskyflyer/zitto**](https://www.npmjs.com/package/@igorskyflyer/zitto)

> _🤫 Zitto - quiet config, loud clarity. A zero-dependency TypeScript/JavaScript helper for merging defaults and options across Node, Deno, Bun, and browsers. 🍯_

<br>

[**@igorskyflyer/magic-queryselector**](https://www.npmjs.com/package/@igorskyflyer/magic-queryselector)

> _🪄 A TypeScript-types patch for querySelector/querySelectorAll, make them return types you expect them to! 🔮_

<br>

## Author
Created by **Igor Dimitrijević ([*@igorskyflyer*](https://github.com/igorskyflyer/))**.
