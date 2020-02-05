# eslint-config-spec

![版本](https://img.shields.io/badge/%40qtt%2Feslint--config--spec-v1.0.3-blue)

统一团队内部编码规范的 ESLint 标准规则集，目前支持 `js` 规则以及 `vue` 规则。基于 [eslint-config-alloy](https://github.com/AlloyTeam/eslint-config-alloy) 修改。

## 注释解释

* `@recommended` 表示当前规则在官方基础规则中已包含，如果自定义规则和推荐规则不同则会加上 `x` 标识。
* `@fix` 表示可以被 eslint 自动修复。
* `@desc` 表示对于当前规则功能和制定的背景说明。

## 如何使用

请先安装规则集。

```
npm i @qtt/eslint-config-spce --save-dev
```

### 使用 JavaScript 规则

请在 `.eslintrc.js` 中添加以下配置，并安装相关依赖 `babel-eslint`。

```js
module.exports = {
  extends: ['@qtt/eslint-config-spec']
  // ... 自定义配置
}
```

### 使用 Prettier 规则

请在 `.eslintrc.js` 中添加以下配置，并安装相关依赖 `prettier` `eslint-config-prettier` `eslint-plugin-prettier`。

```js
module.exports = {
  extends: [
    '@qtt/eslint-config-spec',
    '@qtt/eslint-config-spec/prettier',
  ]
  // ... 自定义配置
}
```

### 使用 Vue 规则

请在 `.eslintrc.js` 中添加以下配置，并安装相关依赖：

* `eslint-plugin-vue`
* `vue-eslint-parser`
* `eslint-plugin-prettier-vue`

`eslint-plugin-prettier-vue` 可以指定将 `prettier` 的规则运用于 `template`, `script`, `style` 中的哪一个模块，默认关闭了 `template` 的校验。

```js
module.exports = {
  extends: [
    '@qtt/eslint-config-spec',
    // 如果需要 prettier
    '@qtt/eslint-config-spec/prettier',
    '@qtt/eslint-config-spec/vue',
  ]
  // ... 自定义配置
}
```

因为 `eslint` 本身不支持 `vue` 的解析所以需要在 `VSCode` 中添加以下配置：

```json
// .vscode/settings.js
{
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    {
      "language": "vue",
      "autoFix": true
    },
    {
      "language": "typescript",
      "autoFix": true
    },
    {
      "language": "typescriptreact",
      "autoFix": true
    }
  ],
  "javascript.validate.enable": false,
  "vetur.format.enable": false,
  "vetur.validation.template": false,
}
```

## 本地调试

请在 `VSCode` 中安装 `eslint` 插件以及 `prettier` 插件。