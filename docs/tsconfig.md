<h1 align="center">
  typescript-study
</h1>

## 目录

### File Inclusion

|选项|类型|默认|描述|
|---|----|---|---|
|exclude|`string[]`|`['node_modules', 'bower_components', 'jspm_packages']`|需要排除的文件|
|extends|`string`|-|从指定的文件中继承配置，这里配置的是继承文件的路径|
|files|`string[]`|-|指定包含在程序中的文件列表，如果文件未找到则会报错|

### Project Options

|选项|类型|默认|描述|
|---|----|---|---|
|[`allowJs`](#allowJs)|`boolean`|`false`|允许编译JS文件|
|[`checkJs`](#checkJs)|`boolean`|`false`|	报告JS文件中的错误。|
|[`declaration`](#declaration)|`boolean`|`false`|生成类型定义文件|
|[`declarationDir`](#declarationDir)|`string`|`n/a`|指定类型定义文件目录|
|[`declarationMap`](#declarationMap)|`boolean`|`false`|生成类型定义的source map|
|[`emitDeclarationOnly`](#emitDeclarationOnly)|`boolean`|`false`|只生成类型定义文件|
|[`noEmit`](#noEmit)|`boolean`|`false`|禁止生成文件|
|[`baseUrl`](#baseUrl)|`string`|-|定义根目录，进行绝对路径文件解析|

### Strict Checks

## 编译选项

### allowJs

设置为`true`时，js文件将被 tsc 编译，否则不会。

使用场景：

- 项目中使用`TS`、`JS`进行混合开发

查看示例：

- [allowJs-true](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/allowJs-true)
- [allowJs-false](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/allowJs-false)

```
# 设置为 true 时，编译后的文件包含 foo.js
├── dist
│   ├── foo.js
│   └── index.js
├── src
│   ├── foo.js
│   └── index.ts
├── package.json
└── tsconfig.json
```

```
# 设置为 false 时，编译后的文件不包含 foo.js
├── dist
│   └── index.js
├── src
│   ├── foo.js
│   └── index.ts
├── package.json
└── tsconfig.json
```

[⇧ 回到目录](#目录)

### checkJs

和`allowJs`配合使用，设置为`true`时，则会报告JS文件中的错误

使用场景：

- 项目中使用`TS`、`JS`进行混合开发

查看示例：

- [checkJs-true](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/checkJs-true)
- [checkJs-false](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/checkJs-false)

```js
// constants.js
// parseFloat(3.124); 参数只能为字符串，编译报错
module.exports.pi = parseFloat(3.124);
```

[⇧ 回到目录](#目录)

### declaration

设置为`true`时，生成类型定义文件

使用场景：

- 开发组件库、工具库需要生成类型定义文件时使用

查看示例：

- [declaration-true](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/declaration-true)
- [declaration-false](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/declaration-false)

```
# 设置为 true 时，编译后的文件包含 *.d.ts
├── dist
│   ├── index.d.ts
│   └── index.js
├── src
│   └── index.ts
├── package.json
└── tsconfig.json
```

```
# 设置为 false 时，编译后的文件不包含 *.d.ts
├── dist
│   └── index.js
├── src
│   └── index.ts
├── package.json
└── tsconfig.json
```

[⇧ 回到目录](#目录)

### declarationDir

和`declaration`配合使用，指定类型定义文件目录

使用场景：

- 开发组件库、工具库需要生成类型定义文件时使用

查看示例：

- [declarationDir](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/declarationDir)

```
# 设置为 dist/types 时，则类型文件将输出到 dist/types
├── dist
│   ├── types
│   │   └── index.d.ts
│   └── index.js
├── src
│   └── index.ts
├── package.json
└── tsconfig.json
```

[⇧ 回到目录](#目录)

### declarationMap

生成类型定义的source map

使用场景：

- 开发组件库、工具库需要生成类型定义文件时使用

查看示例：

- [declarationMap-true](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/declarationMap-true)
- [declarationMap-false](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/declarationMap-false)

```
# 设置为 true 时，编译后的文件包含 *.d.ts.map
├── dist
│   ├── index.d.ts
│   ├── index.d.ts.map
│   └── index.js
├── src
│   └── index.ts
├── package.json
└── tsconfig.json
```

```
# 设置为 false 时，编译后的文件不包含 *.d.ts.map
├── dist
│   ├── index.d.ts
│   └── index.js
├── src
│   └── index.ts
├── package.json
└── tsconfig.json
```

[⇧ 回到目录](#目录)

### emitDeclarationOnly

设置为`true`，只生成类型定义文件

使用场景：

- 只需要类型定义的时候使用

查看示例：

- [emitDeclarationOnly-true](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/emitDeclarationOnly-true)
- [emitDeclarationOnly-false](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/emitDeclarationOnly-false)

```
# 设置为 true 时，不会包含 *.js
├── dist
│   └── index.d.ts
├── src
│   └── index.ts
├── package.json
└── tsconfig.json
```

```
# 设置为 false 时，包含 *.js
├── dist
│   ├── index.d.ts
│   └── index.js
├── src
│   └── index.ts
├── package.json
└── tsconfig.json
```

[⇧ 回到目录](#目录)

### noEmit

设置为`true`，禁止生成文件

查看示例：

- [noEmit-true](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/noEmit-true)
- [noEmit-false](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/noEmit-false)

```
# 设置为 true 时，不会生成编译文件
├── src
│   └── index.ts
├── package.json
└── tsconfig.json
```

```
# 设置为 false 时，生成编译文件
├── dist
│   └── index.js
├── src
│   └── index.ts
├── package.json
└── tsconfig.json
```

[⇧ 回到目录](#目录)

### baseUrl

定义根目录，进行绝对路径文件解析

查看示例：

- [baseUrl](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/baseUrl)

```
# 设置为`./src`时，则可以写绝对路径
# import { helloWorld } from 'hello/world';
├── src
│   ├── hello
│   │   └── world.ts
│   └── index.ts
├── package.json
└── tsconfig.json
```

[⇧ 回到目录](#目录)