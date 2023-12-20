# LXGW WenKai / 霞鹜文楷 网络字体仓库

## 仓库仍在完善，但可以初步使用
## 简介
[LXGW WenKai / 霞鹜文楷](https://github.com/lxgw/LxgwWenKai) 是一款开源中文字体，基于 FONTWORKS 出品字体 Klee One 衍生。字体详情请参阅原字体仓库。

为使其更适合进行网络分发，本仓库利用[中文网字计划](https://chinese-font.netlify.app/)开发的[字体分包工具](https://github.com/KonghaYao/cn-font-split)对原字体进行分包，并在 Github Action 中自动进行。

为方便使用，本仓库的版本号将与字体原仓库版本号一致。目前只提供了 `v1.315` 及之后的版本。

## 使用
### 自行部署
可以直接 Fork 本仓库并启用 Github Pages，亦可直接克隆本仓库到服务端、对象存储等，同时可以对自己的部署启用 CDN。

### 使用 JsDelivr 的 CDN
#### 最新版本
```
https://cdn.jsdelivr.net/gh/CMBill/lxgw-wenkai-screen-web/style.css
```

#### 特定版本 
将链接中的 `$VERSION` 替换为目标版本号，如 `1.315` 或 `v1.315` 均可。目前仅只提供 `v1.315` 之后的版本。
```
https://cdn.jsdelivr.net/gh/CMBill/lxgw-wenkai-screen-web@VERSION/style.css
```
例如请求 `v1.315` 版本的字体：
```
https://cdn.jsdelivr.net/gh/CMBill/lxgw-wenkai-screen-web@1.315/style.css
```

### 直接使用本仓库链接
只提供最新版本

```
https://cmbill.github.io/lxgw-wenkai-web/style.css
```
