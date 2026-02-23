---
slug: /packager/offline
hide_table_of_contents: true
sidebar_label: 离线打包器
---

# 离线打包器

这里有些方法可以让你离线的使用 [TurboWarp 打包器](https://packager.turbowarp.org/) 在一些情况下 (举个例子，你的学校 Ban 掉了 turbowarp.org).

我们计划大约每个月更新一次离线打包器。

像 Electron、NW.js 或 WKWebView 这样的大型可执行文件 *不会* 包含在离线打包器中，而是会根据需要单独下载。打包器会在您首次下载后尝试离线缓存这些文件，因此它们应该只需下载一次。通常，即使您的学校屏蔽了 turbowarp.org，这些下载也仍然可以工作。

## 桌面应用 {#desktop}

你可以下载 [TurboWarp 桌面版](https://desktop.turbowarp.org/), 其中包含一个离线版本的打包器。您可以通过点击右上角的"(?)"按钮，然后选择打包器来访问它。

内置的打包器会自动加载您在编辑器中打开的项目。

## HTML 单文件 {#html}

如果您不能或不想下载桌面应用，您也可以从 GitHub 下载独立的 HTML 版本。请访问 https://github.com/TurboWarp/packager/releases ，在最新版本的“Assets”(资源)中下载“turbowarp-packager-standalone-x.x.x.html”。您可以直接在浏览器中打开这个 HTML 文件。

这个 HTML 文件不包含任何更新检查器。您需要自行检查和处理更新。

## 网页应用 {#pwa}

https://packager.turbowarp.org/ 是一个网页应用，它在加载一次后会尝试离线运行。这仍是实验性功能，我们不建议依赖于此。
