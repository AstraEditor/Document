---
slug: /packager/dynamic-stage-resize
hide_table_of_contents: true
---

# 动态舞台大小

!!! info "信息"
    这个页面是关于[TurboWarp打包器的](https://turbowarp.org/)。

动态舞台大小会根据显示的宽高比和分辨率来改变舞台的大小。

舞台不会进行缩放，修改的是[舞台大小](website/settings/custom-stage-size/)。举个例子，如果用户启用了全屏在分辨率为1920x1080的显示器上，舞台大小也会调整为1920x1080。如果用户调整窗口大小为1x1,所以你应该添加一个最小大小检查。

大多数项目都没能正确处理它，如果你要让项目兼容的话：

 - 首先，让它完全兼容[自定义舞台大小](website/settings/custom-stage-size/)（有关信息请查看这个页面）
 - 之后，将你的舞台大小检测逻辑改为每帧运行，并确保始终更新项目的位置（这个方法效率低且奇怪，但速度足够快，是目前最好的选择）