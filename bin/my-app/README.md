<!--
 * @LastEditors: Mark
 * @Description: none
 * @Author: Mark
 * @Date: 2019-05-15 17:41:26
 * @LastEditTime: 2019-05-25 15:53:49
 -->

# Public_Taro_MiniPrograms_TS

基于`Taro`和`TypeScript`的小程序多端编译框架,根据公司需求专门开发定制

官方文档 <https://nervjs.github.io/taro/docs/GETTING-STARTED.html>

## 运行方式

```bash
#安装本地工具
npm install -g @tarojs/cli

#升级本地工具
taro update self

#升级依赖
taro update project

#安装本地包
npm install

#默认配置微信小程序打包编译
npm run start
npm run build

#微信小程序
npm run dev:weapp
npm run build:weapp

#百度小程序
npm run dev:swan
npm run build:swan

#支付宝小程序
npm run dev:alipay
npm run build:alipay

#字节跳动小程序
npm run dev:tt
npm run build:tt

#H5
npm run dev:h5
npm run build:h5

```

### VSCode 插件

- ESlint

美化辅助插件

- Prettier

### settings.json 设置

```json
{
  "editor.formatOnSave": true,
  "editor.formatOnType": true,
  "prettier.eslintIntegration": true,
  "eslint.autoFixOnSave": true,
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[typescriptreact]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "eslint.validate": [
    "html",
    "javascript",
    "javascriptreact",
    {
      "language": "typescript",
      "autoFix": true
    },
    {
      "language": "typescriptreact",
      "autoFix": true
    },
    {
      "language": "vue",
      "autoFix": true
    }
  ],
}
```

## 脚手架定制化

- 支持编译 less,css 以及 scss

## 状态管理和页面通信

Mobx

文档地址
<https://cn.mobx.js.org/>

## 演示 demo

## 客户端本地存储

## 数据请求方法

## 实用工具库

Lodash

文档地址
<https://www.lodashjs.com/>

引用官方推荐命名

```js
import _ from "lodash";
import _ from "lodash/core";
import fp from "lodash/fp";
import array from "lodash/array";
import object from "lodash/fp/object";
import at from "lodash/at";
import curryN from "lodash/fp/curryN";
```

## 额外注意事项

`不支持在 render 生命周期之外编写 jsx`

`如果代码效果无法出现,请重新执行 npm start`

## 生命周期对应表

| 小程序            |          taro          |
| ----------------- | :--------------------: |
| Page.onLoad       |   componentWillMount   |
| onShow            |    componentDidShow    |
| onHide            |    componentDidHide    |
| onReady           |   componentDidMount    |
| onUnload          |  componentWillUnmount  |
| onError           | componentDidCatchError |
| App.onLaunch      |   componentWillMount   |
| Component.created |   componentWillMount   |
| attached          |   componentDidMount    |
| ready             |   componentDidMount    |
| detached          |  componentWillUnmount  |
| moved             |          保留          |

## js 模块引用的路径别名配置 `Webpack alias`

建议别名使用 @/ 开头而非仅用 @ 开头，因为有小概率会与某些 scoped 形式的 npm 包（如：@babel/core）产生命名冲突。

```js

  '@': path.resolve(__dirname, '..', 'src'),

```

> css 暂不支持`alias` , 在 app.js 中使用的样式会自动生效于全局(函数无法全局生效)
