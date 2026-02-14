---
title: 介绍自定义扩展
---

# 介绍自定义扩展

自定义扩展是一种通过使用 JavaScript 在 TurboWarp 中添加新积木的方法。

在本教程中，我们将介绍如何创建一个自定义扩展。这些页面可以通过侧边栏或每页底部的链接进行导航。我们假设您会完整阅读每个页面，并在进入下一页之前完成列出的练习（如果有）。

!!! info "信息"
    **我们刚刚彻底重写了这份完整的教程。**

    它采用了完全不同的结构和风格，我们希望这样会更易于理解。不过，这个教程仍可能存在一些错误和遗漏之处。[请告诉我您的看法](https://scratch.mit.edu/users/GarboMuffin/#comments)，谢谢！

当人们提到“扩展”时，他们所指的可能有以下几种情况：

| |能够访问 Scratch 内部结构|能够通过 URL 加载 |
|:-:|:-:|:-:|
|原版核心扩展（画笔、翻译等）|✅|❌|
|沙盒·自定义扩展|❌|✅|
|非沙盒·自定义扩展|✅|✅|

这些部分中的文档仅涉及自定义扩展。虽然核心扩展有许多共同的特性，但开发它们的过程却大不相同。请参考[快速入门](../getting-started.md)作为构建核心扩展的起点。

我们将[在稍后](./unsandboxed.md)讨论沙盒扩展与非沙盒扩展之间的区别。

## 兼容性

自定义扩展与 Scratch 不兼容，使用自定义扩展的作品无法上传至 Scratch 网站。不过，这些作品可以通过 [TurboWarp 打包器](https://packager.turbowarp.org/) 进行打包。

## 预备知识

自定义扩展的开发需要具备编写 JavaScript 的知识。如果您还不会 JavaScript，请先学习它。您最常用的搜索引擎可以帮助您找到学习的相关资源。如果您不了解诸如`“1”`和 `1` 之间的区别这类内容，那么开发扩展程序将会非常困难。作为志愿者，我们没有太多时间来帮助您学习 JavaScript —— 为此，我们感到抱歉。

扩展可以通过网站或桌面应用来开发。

我们假定您会用浏览器或桌面应用内置的开发者工具。通常，可以通过右键点击 > 检查元素来打开该界面。在桌面应用中，可以通过按 Ctrl+Shift+I（在 macOS 系统上为 Option+Command+I）来打开该界面。如果无法借助开发者来编写 JavaScript 代码，那将会非常麻烦，我们也无法提供帮助。

## Tutorial structure

This tutorial is follows a fundamentals-up approach. We're going to start with the most basic extensions imaginable that are effectively useless and gradually build up to things that are more useful.

We know that some of you will be eager to start sharing your extensions around, but **we ask that you read through this whole tutorial before publishing your extensions or submitting them to us** so that the extensions you share are actually useful.

## Prepare a development environment

In recent versions of TurboWarp, there are several ways to develop extensions.

### Files (simplest)

Recent versions of the TurboWarp website and desktop app have an option in the custom extension menu to load extensions either from local files or from copied and pasted JavaScript code. This will be the easiest way to develop extensions as it can be done on any computer with just a text editor.

### Local HTTP Server (recommended)

However, if possible, you should use a local HTTP server that lets TurboWarp fetch your extension from your computer. This speeds up the process because you don't have to select/paste the JavaScript code in TurboWarp every time you make changes. There are a lot of options for installing one of these. If you have Python installed, you already have one:

```bash
cd path/to/where/you/will/store/your/extensions
python3 -m http.server 8080
```

This starts a local HTTP server on http://localhost:8080/ in whatever folder you ran that command in.

We will [eventually](./better-development-server) introduce the official development server, but we recommend starting with the most primitive setup possible for now.

For now, you should use a port **other than 8000**. We will talk more about this later, but currently we want the extensions you write to run in the sandbox. Extensions that run outside of the sandbox have some extra responsibilities that we will discuss [later](./unsandboxed).

To test that your server works, create a file called `hello-world.js` and put any text in it. Make sure you're able to read the contents of the file in your browser by visiting a link like [http://localhost:8080/hello-world.js](http://localhost:8080/hello-world.js).

## Next steps

Next, let's [make your first extension](./hello-world).
