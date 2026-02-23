---
title: 嵌入
---

# 嵌入

!!! info "信息"
    这个页面是关于[TurboWarp 打包器](https://turbowarp.org/)的。如果你只想知道如何嵌入 Scratch 作品到网站，查看[另一个嵌入页面](/website/embedding/).


你可以将 TurboWarp 打包器输出的结果嵌入到别的网站：

```html
<iframe src="项目的路径.html" width="480" height="360" allowtransparency="true" frameborder="0" scrolling="no" allowfullscreen></iframe>
```

根据你使用的环境、存储项目的位置以及你是咋命名的，`src` 的属性会有不同。

 - 如果你是用 “HTML 文件”（单个），你只需要填入HTML文件的路径。
 - 如果你是用 “Zip 压缩包”，则需要解压zip并选择 `index.html`文件的路径。

如果你启用了控制按钮（开始 暂停 终止 全屏那几个），给`height`加上48来避免舞台错误的缩小。