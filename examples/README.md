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

### Strict Checks

## 编译选项

### allowJs

设置为`true`时，将允许导入JS文件到你的项目，否则不会。

**使用场景**

- 项目中使用`TS`、`JS`进行混合开发

**查看示例**

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

**使用场景**

- 项目中使用`TS`、`JS`进行混合开发

**查看示例**

- [checkJs-true](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/checkJs-true)
- [checkJs-false](https://github.com/wangxingkang/typescript-study/tree/main/examples/project-options/checkJs-false)

```js
// constants.js
// parseFloat(3.124); 参数只能为字符串，编译报错
module.exports.pi = parseFloat(3.124);
```

[⇧ 回到目录](#目录)

### allowSyntheticDefaultImports

