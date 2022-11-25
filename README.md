# 订阅模式 | ScriptCat

> ## Excerpt
> 文件开头必须使用UserSubscribe而不是UserScript，安装时的链接推荐使用user.sub.js后缀，必须使用https链接。

---
一个订阅脚本可以描述所需要的多个脚本的安装链接，通过订阅模式安装的脚本使用静默安装，不会弹出确认安装页面，所安装的脚本也会展示在脚本列表中，但是`connect`权限会使用订阅中所声明的`connect`，而不会使用脚本自身的`connect`权限。

```javascript
// ==UserSubscribe==
// @name         xxx
// @description  订阅xxx系列脚本
// @version      0.1.0
// @author       You
// @connect      www.baidu.com
// @scriptUrl    https://script.tampermonkey.net.cn/48.user.js
// @scriptUrl    https://script.tampermonkey.net.cn/49.user.js
// ==/UserSubscribe==
```

订阅每次更新和变化会使用脚本链接与已安装的脚本进行比对，新的订阅中没有的脚本会进行删除，新增的脚本会进行静默安装。脚本的更新通过脚本自身的`version`去更新，与用户正常安装脚本的更新逻辑一致。

订阅的脚本使用静默的方式进行安装，订阅新增/删除脚本时仅会弹出一个通知，不会再次由用户进行确认，脚本的更新机制不发生变化需要由用户确认，若用户勾选了`设置->非重要变更静默更新脚本`的选项，则按照改规则进行更新。由于静默更新的机制，请选择安全且值得信任的订阅方。
