# LXGW WenKai Screen / 霞鹜文楷屏幕阅读版 网络字体仓库

> 其他版本霞鹜文楷字体的网络字体仓库：
>   - [霞鹜文楷 / LXGW WenKai](https://github.com/CMBill/lxgw-wenkai-web)：原版。
>   - [霞鹜文楷 GB / LXGW WenKai GB](https://github.com/CMBill/lxgw-wenkai-gb-web)：调整字形和笔形，符合 G 源字形规范。包含《通用规范汉字表》8105 个汉字。
>   - [霞鹜文楷 TC / LXGW WenKai TC](https://github.com/CMBill/lxgw-wenkai-tc-web)：繁体中文版。

## 简介
[LXGW WenKai Screen / 霞鹜文楷屏幕阅读版](https://github.com/lxgw/LxgwWenKai-Screen) 是 [霞鹜文楷](https://github.com/lxgw/LxgwWenKai) 的屏幕舒适阅读版本，更适合 PC 及 Android 手机屏幕显示。字体详情请参阅原字体仓库。

为使原字体更适合进行网络分发，本仓库使用 Github Action，利用[中文网字计划](https://chinese-font.netlify.app/)开发的[字体分包工具](https://github.com/KonghaYao/cn-font-split)对原字体分包，网页加载时只需获取所使用的文字所在的分包，大幅降低所需加载的大小，提升网页加载速度。

为方便使用，本仓库的版本号将与字体原仓库版本号一致。目前只提供了 `v1.315` 及之后的版本。

## 使用
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
| LXGW WenKai Screen R       | `LXGW WenKai Screen R`       | `normal`      |
| LXGW WenKai GB Screen      | `LXGW WenKai GB Screen`      | `normal`      |
| LXGW WenKai GB Screen R    | `LXGW WenKai GB Screen R`    | `normal`      |
| LXGW WenKai Mono Screen    | `LXGW WenKai Mono Screen`    | `normal`      |
| LXGW WenKai Mono GB Screen | `LXGW WenKai Mono GB Screen` | `normal`      |

如果只需某一特定的字体，也可只引用其对应分包的 CSS 文件，将如下表格中 `repositoryURL` 替换为仓库的链接即可。

| 字体                       | 链接                                                            |
| -------------------------- | --------------------------------------------------------------- |
| LXGW WenKai Screen         | `https://repositoryURL/fonts/lxgwwenkaiscreen/result.css`       |
| LXGW Wenkai Screen R       | `https://repositoryURL/fonts/lxgwwenkaiscreenr/result.css`      |
| LXGW Wenkai GB Screen      | `https://repositoryURL/fonts/lxgwwenkaigbscreen/result.css`     |
| LXGW WenKai GB Screen R    | `https://repositoryURL/fonts/lxgwwenkaigbscreenr/result.css`    |
| LXGW WenKai Mono Screen    | `https://repositoryURL/fonts/lxgwwenkaimonoscreen/result.css`   |
| LXGW WenKai Mono GB Screen | `https://repositoryURL/fonts/lxgwwenkaimonogbscreen/result.css` | 

例如若只需调用 LXGW WenKai Mono Screen，则只需引入：
```
https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/fonts/lxgwwenkaimonoscreen/result.css
``` 

### 自行部署
如果下方提供的链接连接效果不甚理想，建议自行部署并配合自己的 CDN 使用。可以直接 Fork 本仓库并启用 Github Pages，使用时将下方链接修改为自己的仓库地址即可，亦可直接克隆本仓库到服务端、对象存储等。

### 使用 CDN
#### 作为 npm 包
目前已作为 npm 包上传到 npmjs，可以使用 npm 包的镜像引用

```
https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web/style.css
```

也可指定版本号，将链接中的 `$VERSION` 替换为目标版本号，如 `1.315` 或 `v1.315` 均可。目前仅只提供 `v1.315` 之后的版本。

```
https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web@VERSION/style.css
```

例如请求 `v1.315` 版本的字体：
```
https://cdn.jsdelivr.net/npm/lxgw-wenkai-screen-web@1.315/style.css
```

#### 使用 JsDelivr 对 GitHub 仓库的 CDN
```
https://cdn.jsdelivr.net/gh/CMBill/lxgw-wenkai-screen-web/style.css
```

也可指定版本号，将链接中的 `$VERSION` 替换为目标版本号，如 `1.315` 或 `v1.315` 均可。目前仅只提供 `v1.315` 之后的版本。
```
https://cdn.jsdelivr.net/gh/CMBill/lxgw-wenkai-screen-web@VERSION/style.css
```

### 直接使用本仓库链接
只提供最新版本

```
https://cmbill.github.io/lxgw-wenkai-screen-web/style.css
```
