# LXGW WenKai Screen / 霞鹜文楷屏幕阅读版 网络字体仓库

> 其他版本霞鹜文楷字体的网络字体仓库：
>   - [霞鹜文楷 / LXGW WenKai](https://github.com/CMBill/lxgw-wenkai-web)：原版。
>   - [霞鹜文楷 GB / LXGW WenKai GB](https://github.com/CMBill/lxgw-wenkai-gb-web)：调整字形和笔形，符合 G 源字形规范。包含《通用规范汉字表》8105 个汉字。
>   - [霞鹜文楷 TC / LXGW WenKai TC](https://github.com/CMBill/lxgw-wenkai-tc-web)：繁体中文版。

[![NPM Version](https://img.shields.io/npm/v/lxgw-wenkai-screen-web?labelColor=cb0000&color=ffffff)](https://www.npmjs.com/package/lxgw-wenkai-screen-web)
[![Cdnjs](https://img.shields.io/cdnjs/v/lxgw-wenkai-screen-web?labelColor=ff6934&color=ebebeb)](https://cdnjs.com/libraries/lxgw-wenkai-screen-web)
[![JsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/lxgw-wenkai-screen-web/badge?style=rounded)](https://www.jsdelivr.com/package/npm/lxgw-wenkai-screen-web)

## 简介

[LXGW WenKai Screen / 霞鹜文楷屏幕阅读版](https://github.com/lxgw/LxgwWenKai-Screen) 是 [霞鹜文楷](https://github.com/lxgw/LxgwWenKai) 的屏幕舒适阅读版本，更适合 PC 及 Android 手机屏幕显示。字体详情请参阅原字体仓库。

为使原字体更适合进行网络分发，本仓库使用 Github Action，利用[中文网字计划](https://chinese-font.netlify.app/)开发的[字体分包工具](https://github.com/KonghaYao/cn-font-split)对原字体分包，网页加载时只需获取所使用的文字所在的分包，大幅降低所需加载的大小，提升网页加载速度。

为方便使用，本仓库的版本号将与字体原仓库版本号一致。目前只提供了 `v1.315` 及之后的版本（在 v1.320 及以后提供的均是使用 Roboto 打底补全缺失字符的版本，并未单独区分）。

## 在网页中使用

直接将文后提供的链接以 `<link>` 的形式添加到网页的 `<head>` 内即可

```html
<html>
<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/style.css" />
  <style>
    body {
      font-family: "LXGW WenKai Screen";
      font-weight: normal;
    }
  </style>
</head>
<body>
  
</body>
</html>
```

这样引入 `style.css` 的可以调用仓库包含的所有字体，使用字体时以表格中所示 `font-family` 与 `font-weight` 在 CSS 中调用即可。

| 字体                       | `font-family`                | `font-weight` |
| -------------------------- | ---------------------------- | ------------- |
| LXGW WenKai Screen         | `LXGW WenKai Screen`         | `normal`      |
| LXGW WenKai GB Screen      | `LXGW WenKai GB Screen`      | `normal`      |
| LXGW WenKai Mono Screen    | `LXGW WenKai Mono Screen`    | `normal`      |
| LXGW WenKai Mono GB Screen | `LXGW WenKai Mono GB Screen` | `normal`      |

如果只需某一特定的字体，也可只引用其对应分包的 CSS 文件，按如下表格中链接进行替换即可。

| 字体                       | 链接                                                            |
| -------------------------- | --------------------------------------------------------------- |
| LXGW WenKai Screen         | `https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/lxgwwenkaiscreen/result.css`       |
| LXGW Wenkai GB Screen      | `https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/lxgwwenkaigbscreen/result.css`     |
| LXGW WenKai Mono Screen    | `https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/lxgwwenkaimonoscreen/result.css`   |
| LXGW WenKai Mono GB Screen | `https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/lxgwwenkaimonogbscreen/result.css` | 

例如若只需调用 LXGW WenKai Mono Screen，则只需引入：

```
https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/lxgwwenkaimonoscreen/result.css
```
## 部署到 Vitepress

由于字重问题，以下使用 noto sc 等字体进行替换 bold 和 semibold。

- `package.json`（bun 版本）：

```json
{
  "type": "module",
  "license": "BSD-2-Clause",
  "dependencies": {
	"vitepress": "1.6.4",
	"noto-sans-sc": "37.0.0",
	"lxgw-wenkai-screen-web": "1.521.0"
  },
  "scripts": {
    "docs:dev": "vitepress dev docs",
    "docs:build": "vitepress build docs",
    "docs:preview": "vitepress preview docs"
  }
}
```

- `.vitepress/theme/index.js`：

```js
import DefaultTheme from 'vitepress/theme-without-fonts'; //不使用默认字体
import 'lxgw-wenkai-screen-web/lxgwwenkaigbscreen/result.css'; // 导入霞鹜文楷屏幕阅读版
import 'lxgw-wenkai-screen-web/lxgwwenkaimonogbscreen/result.css'; // 导入霞鹜文楷屏幕阅读版
import 'noto-sans-sc/all.css'; // 导入 noto，霞鹜文楷加粗后辨识度不高，且无 bold 字重
import './custom.css'; // 导入自定义 CSS

export default DefaultTheme // 若无自定义 vue

// 若存在自定义 vue，下面的自定义 vue 为 Layout.vue。如果你不知道这是什么，请使用上面那行
/* 
import Layout from './Layout.vue';


export default {
  ...DefaultTheme,
  Layout,
};*/
```

- `.vitepress/theme/custom.css`：

```css
/* 导入 LXGW WenKai Screen*/
:root {
  --vp-font-family-base: 'LXGW WenKai GB Screen';
  --vp-font-family-default: 'Noto Sans SC';
  --vp-font-family-mono: 'LXGW WenKai Mono GB Screen';
  /* 定义一个 semibold 使用的字体栈，与 strong 相同 */
  --vp-font-family-semibold: var(--vp-font-family-default);
  /* 定义 semibold 的字重，通常对应 600 */
  --vp-font-weight-semibold: 500;
}

/* normal 字重文字使用 LXGW WenKai Screen */
body,
p,
span {
  font-family: var(--vp-font-family-base);
  font-weight: normal;
}

/* 当需要粗体（bold）时，加粗 */
strong, b {
  font-family: var(--vp-font-family-default);
  font-weight: 700;
}

/* 为 semibold 定义样式 */
.semibold {
  font-family: var(--vp-font-family-semibold);
  font-weight: var(--vp-font-weight-semibold);
}
```


## 链接

### 使用 CDN

目前已作为 npm 包上传到 npmjs，可以使用 npm 包的镜像链接引用。

#### 使用 JsDelivr 对 npm 包的 CDN

```
https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/style.css
```

也可指定版本号，将链接中的 `$VERSION` 替换为目标版本号，如 `1.315` 或 `v1.315` 均可。目前仅只提供 `v1.315` 之后的版本。

```
https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web@VERSION/style.css
```

#### 使用 cdnjs 的 CDN

目前已提交至 [cdnjs 仓库](https://cdnjs.com/libraries/lxgw-wenkai-screen-web)，可以使用 cdnjs 提供的 cdn 链接。此方法必须指定版本号，将链接中的 `$VERSION` 替换为 npm 包的目标版本号。具体版本号可以查询 [npmjs](https://www.npmjs.com/package/lxgw-wenkai-screen-web?activeTab=versions) 或 [cdnjs](https://cdnjs.com/libraries/lxgw-wenkai-screen-web) 的页面。目前仅只提供 `v1.315` 之后的版本。

```
https://cdnjs.cloudflare.com/ajax/libs/lxgw-wenkai-screen-web/$VERSION/style.css
```

#### 使用 npmmirror

阿里提供的 npm 镜像

使用方法：获取文件内容 `/${pkg}/${versionOrTag}/files/${path}`

如： `https://registry.npmmirror.com/lxgw-wenkai-screen-web/latest/files/style.css`

如果想获取特定版本，只需将 `latest` 修改为特定的 npm 包版本号，如

`https://registry.npmmirror.com/lxgw-wenkai-screen-web/1.315.1/files/style.css`


#### 使用公益镜像

渺软公益 CDN

回源 jsDelivr，参考 jsDelivr：`https://jsd.onmicrosoft.cn/npm/lxgw-wenkai-screen-web/style.css`

回源 UNPKG，参考 UNPKG：`https://npm.onmicrosoft.cn/lxgw-wenkai-screen-web/style.css`
