
# 源码分析

## 文件结构

``` bash
/Users/liufang/openSource/FunnyLiu/rollup
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE-CORE.md
├── LICENSE.md
├── README.md
├── browser
|  ├── crypto.ts
|  ├── fs.ts
|  └── path.ts
├── cli
|  ├── help.md
|  ├── index.ts
|  ├── logging.ts
|  ├── run
|  |  ├── batchWarnings.ts
|  |  ├── build.ts
|  |  ├── index.ts
|  |  ├── loadConfigFile.ts
|  |  ├── resetScreen.ts
|  |  ├── timings.ts
|  |  └── watch.ts
|  └── sourceMappingUrl.ts
├── docs
|  ├── 00-introduction.md
|  ├── 01-command-line-reference.md
|  ├── 02-javascript-api.md
|  ├── 03-es-module-syntax.md
|  ├── 04-tutorial.md
|  ├── 05-plugin-development.md
|  ├── 06-faqs.md
|  ├── 07-tools.md
|  ├── 08-troubleshooting.md
|  └── 999-big-list-of-options.md
├── markdownlint.json
├── package-lock.json
├── package.json
├── rollup.config.js
├── scripts
|  ├── load-perf-config.js
|  ├── perf-debug.js
|  ├── perf-init.js
|  ├── perf.js
|  └── test-package.js
├── src
|  ├── Chunk.ts
|  ├── ExternalModule.ts
|  ├── Graph.ts
|  ├── Module.ts
|  ├── ModuleLoader.ts
|  ├── ast
|  |  ├── CallOptions.ts
|  |  ├── DeoptimizableEntity.ts
|  |  ├── Entity.ts
|  |  ├── ExecutionContext.ts
|  |  ├── keys.ts
|  |  ├── nodes
|  |  |  ├── ArrayExpression.ts
|  |  |  ├── ArrayPattern.ts
|  |  |  ├── ArrowFunctionExpression.ts
|  |  |  ├── AssignmentExpression.ts
|  |  |  ├── AssignmentPattern.ts
|  |  |  ├── AwaitExpression.ts
|  |  |  ├── BinaryExpression.ts
|  |  |  ├── BlockStatement.ts
|  |  |  ├── BreakStatement.ts
|  |  |  ├── CallExpression.ts
|  |  |  ├── CatchClause.ts
|  |  |  ├── ClassBody.ts
|  |  |  ├── ClassDeclaration.ts
|  |  |  ├── ClassExpression.ts
|  |  |  ├── ConditionalExpression.ts
|  |  |  ├── ContinueStatement.ts
|  |  |  ├── DoWhileStatement.ts
|  |  |  ├── EmptyStatement.ts
|  |  |  ├── ExportAllDeclaration.ts
|  |  |  ├── ExportDefaultDeclaration.ts
|  |  |  ├── ExportNamedDeclaration.ts
|  |  |  ├── ExportNamespaceSpecifier.ts
|  |  |  ├── ExportSpecifier.ts
|  |  |  ├── ExpressionStatement.ts
|  |  |  ├── ForInStatement.ts
|  |  |  ├── ForOfStatement.ts
|  |  |  ├── ForStatement.ts
|  |  |  ├── FunctionDeclaration.ts
|  |  |  ├── FunctionExpression.ts
|  |  |  ├── Identifier.ts
|  |  |  ├── IfStatement.ts
|  |  |  ├── ImportDeclaration.ts
|  |  |  ├── ImportDefaultSpecifier.ts
|  |  |  ├── ImportExpression.ts
|  |  |  ├── ImportNamespaceSpecifier.ts
|  |  |  ├── ImportSpecifier.ts
|  |  |  ├── LabeledStatement.ts
|  |  |  ├── Literal.ts
|  |  |  ├── LogicalExpression.ts
|  |  |  ├── MemberExpression.ts
|  |  |  ├── MetaProperty.ts
|  |  |  ├── MethodDefinition.ts
|  |  |  ├── NewExpression.ts
|  |  |  ├── NodeType.ts
|  |  |  ├── ObjectExpression.ts
|  |  |  ├── ObjectPattern.ts
|  |  |  ├── Program.ts
|  |  |  ├── Property.ts
|  |  |  ├── RestElement.ts
|  |  |  ├── ReturnStatement.ts
|  |  |  ├── SequenceExpression.ts
|  |  |  ├── SpreadElement.ts
|  |  |  ├── SwitchCase.ts
|  |  |  ├── SwitchStatement.ts
|  |  |  ├── TaggedTemplateExpression.ts
|  |  |  ├── TemplateElement.ts
|  |  |  ├── TemplateLiteral.ts
|  |  |  ├── ThisExpression.ts
|  |  |  ├── ThrowStatement.ts
|  |  |  ├── TryStatement.ts
|  |  |  ├── UnaryExpression.ts
|  |  |  ├── UnknownNode.ts
|  |  |  ├── UpdateExpression.ts
|  |  |  ├── VariableDeclaration.ts
|  |  |  ├── VariableDeclarator.ts
|  |  |  ├── WhileStatement.ts
|  |  |  ├── YieldExpression.ts
|  |  |  ├── index.ts
|  |  |  └── shared
|  |  |     ├── ClassNode.ts
|  |  |     ├── Expression.ts
|  |  |     ├── FunctionNode.ts
|  |  |     ├── MultiExpression.ts
|  |  |     ├── Node.ts
|  |  |     ├── Pattern.ts
|  |  |     └── knownGlobals.ts
|  |  ├── scopes
|  |  |  ├── BlockScope.ts
|  |  |  ├── CatchScope.ts
|  |  |  ├── ChildScope.ts
|  |  |  ├── FunctionScope.ts
|  |  |  ├── GlobalScope.ts
|  |  |  ├── ModuleScope.ts
|  |  |  ├── ParameterScope.ts
|  |  |  ├── ReturnValueScope.ts
|  |  |  └── Scope.ts
|  |  ├── utils
|  |  |  └── PathTracker.ts
|  |  ├── values.ts
|  |  └── variables
|  |     ├── ArgumentsVariable.ts
|  |     ├── ExportDefaultVariable.ts
|  |     ├── ExportShimVariable.ts
|  |     ├── ExternalVariable.ts
|  |     ├── GlobalVariable.ts
|  |     ├── LocalVariable.ts
|  |     ├── NamespaceVariable.ts
|  |     ├── ThisVariable.ts
|  |     ├── UndefinedVariable.ts
|  |     └── Variable.ts
|  ├── browser-entry.ts
|  ├── chunk-optimization.ts
|  ├── finalisers
|  |  ├── amd.ts
|  |  ├── cjs.ts
|  |  ├── esm.ts
|  |  ├── iife.ts
|  |  ├── index.ts
|  |  ├── shared
|  |  |  ├── esModuleExport.ts
|  |  |  ├── getExportBlock.ts
|  |  |  ├── getInteropBlock.ts
|  |  |  ├── getInteropNamespace.ts
|  |  |  ├── sanitize.ts
|  |  |  ├── setupNamespace.ts
|  |  |  ├── trimEmptyImports.ts
|  |  |  └── warnOnBuiltins.ts
|  |  ├── system.ts
|  |  └── umd.ts
|  ├── node-entry.ts
|  ├── rollup
|  |  ├── index.ts
|  |  └── types.d.ts
|  ├── utils
|  |  ├── FileEmitter.ts
|  |  ├── PluginCache.ts
|  |  ├── PluginContext.ts
|  |  ├── PluginDriver.ts
|  |  ├── addons.ts
|  |  ├── assignChunkIds.ts
|  |  ├── base64.ts
|  |  ├── blank.ts
|  |  ├── buildPhase.ts
|  |  ├── chunkColouring.ts
|  |  ├── collapseSourcemaps.ts
|  |  ├── commondir.ts
|  |  ├── crypto.ts
|  |  ├── decodedSourcemap.ts
|  |  ├── deconflictChunk.ts
|  |  ├── defaultPlugin.ts
|  |  ├── entryHashing.ts
|  |  ├── error.ts
|  |  ├── executionOrder.ts
|  |  ├── fs.ts
|  |  ├── getCodeFrame.ts
|  |  ├── getExportMode.ts
|  |  ├── getIndentString.ts
|  |  ├── getOriginalLocation.ts
|  |  ├── identifierHelpers.ts
|  |  ├── mergeOptions.ts
|  |  ├── path.ts
|  |  ├── pluginUtils.ts
|  |  ├── pureComments.ts
|  |  ├── relativeId.ts
|  |  ├── renderChunk.ts
|  |  ├── renderHelpers.ts
|  |  ├── renderNamePattern.ts
|  |  ├── reservedNames.ts
|  |  ├── safeName.ts
|  |  ├── sanitizeFileName.ts
|  |  ├── sourceMappingURL.ts
|  |  ├── systemJsRendering.ts
|  |  ├── timers.ts
|  |  ├── transform.ts
|  |  ├── traverseStaticDependencies.ts
|  |  ├── treeshakeNode.ts
|  |  └── variableNames.ts
|  └── watch
|     ├── chokidar.ts
|     ├── fileWatchers.ts
|     └── index.ts
├── tsconfig.json
├── tslint.json
└── typings
   ├── declarations.d.ts
   ├── hash.js.d.ts
   └── package.json.d.ts

directory: 2316 file: 7132 symboliclink: 2

ignored: directory (3)

```

## 外部模块依赖

请在： http://npm.broofa.com?q=rollup 查看

## 内部模块依赖

![img](./inner.svg)
  

# Rollup

<p align="center">
  <a href="https://www.npmjs.com/package/rollup">
    <img src="https://img.shields.io/npm/v/rollup.svg" alt="npm version" >
  </a>
  <a href="https://packagephobia.now.sh/result?p=rollup">
    <img src="https://packagephobia.now.sh/badge?p=rollup" alt="install size" >
  </a>
  <a href="https://codecov.io/gh/rollup/rollup">
    <img src="https://codecov.io/gh/rollup/rollup/graph/badge.svg" alt="code coverage" >
  </a>
  <a href="#backers" alt="sponsors on Open Collective">
      <img src="https://opencollective.com/rollup/backers/badge.svg" alt="backers" >
  </a> 
  <a href="#sponsors" alt="Sponsors on Open Collective">
    <img src="https://opencollective.com/rollup/sponsors/badge.svg" alt="sponsors" >
  </a> 
  <a href="https://github.com/rollup/rollup/blob/master/LICENSE.md">
    <img src="https://img.shields.io/npm/l/rollup.svg" alt="license">
  </a>
  <a href="https://david-dm.org/rollup/rollup">
    <img src="https://david-dm.org/rollup/rollup/status.svg" alt="dependency status">
  </a>
  <a href='https://gitter.im/rollup/rollup?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge'>
    <img src='https://badges.gitter.im/rollup/rollup.svg' alt='Join the chat at https://gitter.im/rollup/rollup'>
  </a>
</p>


## Overview

Rollup is a module bundler for JavaScript which compiles small pieces of code into something larger and more complex, such as a library or application. It uses the standardized ES module format for code, instead of previous idiosyncratic solutions such as CommonJS and AMD. ES modules let you freely and seamlessly combine the most useful individual functions from your favorite libraries. Rollup can optimize ES modules for faster native loading in modern browsers, or output a legacy module format allowing ES module workflows today.

## Quick Start Guide

Install with `npm install --global rollup`. Rollup can be used either through a [command line interface](https://rollupjs.org/#command-line-reference) with an optional configuration file, or else through its [JavaScript API](https://rollupjs.org/#javascript-api). Run `rollup --help` to see the available options and parameters. The starter project templates, [rollup-starter-lib](https://github.com/rollup/rollup-starter-lib) and [rollup-starter-app](https://github.com/rollup/rollup-starter-app), demonstrate common configuration options, and more detailed instructions are available throughout the [user guide](https://rollupjs.org/).

### Commands

These commands assume the entry point to your application is named main.js, and that you'd like all imports compiled into a single file named bundle.js.

For browsers:

```bash
# compile to a <script> containing a self-executing function
$ rollup main.js --format iife --name "myBundle" --file bundle.js
```

For Node.js:

```bash
# compile to a CommonJS module
$ rollup main.js --format cjs --file bundle.js
```

For both browsers and Node.js:

```bash
# UMD format requires a bundle name
$ rollup main.js --format umd --name "myBundle" --file bundle.js
```

## Why

Developing software is usually easier if you break your project into smaller separate pieces, since that often removes unexpected interactions and dramatically reduces the complexity of the problems you'll need to solve, and simply writing smaller projects in the first place [isn't necessarily the answer](https://medium.com/@Rich_Harris/small-modules-it-s-not-quite-that-simple-3ca532d65de4). Unfortunately, JavaScript has not historically included this capability as a core feature in the language.

This finally changed with ES modules support in JavaScript, which provides a syntax for importing and exporting functions and data so they can be shared between separate scripts. The specification is now implemented in all major browsers and in Node.js behind the --experimental-modules flag for ".mjs" files. Rollup allows you to write your code using this module system, either outputting optimized ES modules for use in these native environments, or compiling it back down to existing supported formats such as CommonJS modules, AMD modules, and IIFE-style scripts. This means that you get to *write future-proof code*, and you also get the tremendous benefits of...

## Tree Shaking

In addition to enabling the use of ES modules, Rollup also statically analyzes and optimizes the code you are importing, and will exclude anything that isn't actually used. This allows you to build on top of existing tools and modules without adding extra dependencies or bloating the size of your project.

For example, with CommonJS, the *entire tool or library must be imported*.

```js
// import the entire utils object with CommonJS
var utils = require( 'utils' );
var query = 'Rollup';
// use the ajax method of the utils object
utils.ajax( 'https://api.example.com?search=' + query ).then( handleResponse );
```

But with ES modules, instead of importing the whole `utils` object, we can just import the one `ajax` function we need:

```js
// import the ajax function with an ES import statement
import { ajax } from 'utils';
var query = 'Rollup';
// call the ajax function
ajax( 'https://api.example.com?search=' + query ).then( handleResponse );
```

Because Rollup includes the bare minimum, it results in lighter, faster, and less complicated libraries and applications. Since this approach is based on explicit `import` and `export` statements, it is vastly more effective than simply running an automated minifier to detect unused variables in the compiled output code.

## Compatibility

### Importing CommonJS

Rollup can import existing CommonJS modules [through a plugin](https://github.com/rollup/rollup-plugin-commonjs).

### Publishing ES Modules

To make sure your ES modules are immediately usable by tools that work with CommonJS such as Node.js and webpack, you can use Rollup to compile to UMD or CommonJS format, and then point to that compiled version with the `main` property in your `package.json` file. If your `package.json` file also has a `module` field, ES-module-aware tools like Rollup and [webpack 2](https://webpack.js.org/) will [import the ES module version](https://github.com/rollup/rollup/wiki/pkg.module) directly.

## Contributors

This project exists thanks to all the people who contribute. [[Contribute](CONTRIBUTING.md)].
<a href="https://github.com/rollup/rollup/graphs/contributors"><img src="https://opencollective.com/rollup/contributors.svg?width=890" /></a>


## Backers

Thank you to all our backers! 🙏 [[Become a backer](https://opencollective.com/rollup#backer)]

<a href="https://opencollective.com/rollup#backers" target="_blank"><img src="https://opencollective.com/rollup/backers.svg?width=890"></a>


## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](https://opencollective.com/rollup#sponsor)]

<a href="https://opencollective.com/rollup/sponsor/0/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/rollup/sponsor/1/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/rollup/sponsor/2/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/rollup/sponsor/3/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/rollup/sponsor/4/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/rollup/sponsor/5/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/rollup/sponsor/6/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/rollup/sponsor/7/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/rollup/sponsor/8/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/rollup/sponsor/9/website" target="_blank"><img src="https://opencollective.com/rollup/sponsor/9/avatar.svg"></a>



## License

[MIT](https://github.com/rollup/rollup/blob/master/LICENSE.md)
