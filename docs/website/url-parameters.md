---
title: URL 参数
---

# URL 参数


!!! note "注释"
    ## 这里只有“隐藏”的 URL 参数
    TurboWarp 会自动存储加速模式、60 FPS、高清画笔等设置，但一些高级选项仍需手动应用，此页面仅记录这些高级选项。


## Username {#username}

`username`参数用于控制`用户名`块返回的值。

https://turbowarp.org/443603478?username=ExampleUsername

## 云主机 {#cloud_host}

`cloud_host`参数用于设置 TurboWarp 要连接的云变量服务器，例如：

https://turbowarp.org/12785898?cloud_host=wss://clouddata.turbowarp.org

`ws://`或`wss://`的协议是可选的，但我们建议您这样加上它。`wss://clouddata.turbowarp.org`是 TurboWarp 默认使用的云变量服务器，因此这个示例实际上并不会改变任何内容。不安全的 ws:// 服务器可能无法正常工作，因为 TurboWarp 使用的是 HTTPS 协议。

TurboWarp 不支持连接到 Scratch 的云服务器，因为它需要验证用户凭证。

## 自定义扩展 {#extension}

`extension`参数从一个 URL 加载自定义扩展。详见[自定义扩展](/development/custom-extensions.md)。

<!-- 因可能存在被删除的情况而注释掉 -->
<!--
## `scale` {#scale}

控制全屏模式下玩家的最大相对缩放比例。

https://turbowarp.org/fullscreen?scale=2
-->

## 禁用编译器 {#nocompile}

`nocompile`参数用于关闭编译器。除非你知道自己在做什么，否则请不要加上这个参数。

https://turbowarp.org/?nocompile

## 作品 URL {#project_url}

!!! warning inline end "注意啦！"
    这需要一个 .sb3 文件下载直链！

`project_url`参数让 TurboWarp 从任意一个 URL 下载 Scratch 作品，请勿将其与常规 Scratch 网站的作品 ID 一起使用。

https://turbowarp.org/?project_url=packager.turbowarp.org/example.sb3

如果未指定协议，则默认使用“https”。通常 http:// 协议的 URL 出于安全原因无法使用。请注意，该 URL 需要是下载直链，并且必须支持 CORS（`Access-Control-Allow-Origin： *`）。[GitHub Pages](https://pages.github.com/) 会自动完成此操作，并且已知运行良好。
