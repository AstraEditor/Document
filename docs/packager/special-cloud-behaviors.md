---
slug: /packager/special-cloud-behaviors
hide_table_of_contents: true
---

# 特殊的云变量

!!! info "信息"
    这个页面是关于 [TurboWarp 打包器](https://turbowarp.org/)的。

默认禁用的“特殊的云变量”设置会更改特定命名的云变量的行为，来给你的项目解锁新的兼容性。这是基于[HTMLifier 中的类似功能](https://github.com/SheepTester/htmlifier/wiki/Special-cloud-behaviours)，该功能可以在“云变量”部分启用。

要创建这些，只需像平常一样创建一个云变量，但给它赋予下面指定的特定名称。例如，要使用 `☁ url` 变量，就创建一个名为 `url` 的变量并将其标记为云变量。

启用特殊云行为将覆盖这些变量的任何其他设置，因此像 `☁ username` 这样的变量将永远不会在本地存储或与其他用户同步。

## ☁ url {#url}

`☁ url` 变量会设为页面的链接，改变这个变量啥用没有。

## ☁ redirect {#redirect}

当 `☁ redirect` 设为一个链接，当前标签页将跳转到到这个 URL。

## ☁ open link {#open-link}

当`☁ open link` 设为一个链接，项目将尝试用该URL打开一个新标签页。请注意，由于大多数浏览器内置了弹窗拦截器，这并不总是可靠的。

## ☁ username {#username}

当 `☁ username` 修改时, 积木区中侦测类的 `用户名` 积木的值将会改变。

## ☁ pasted {#pasted}

当用户使用像 Ctrl+V 这样的快捷键将文本粘贴到页面上时，文本会存储在 `☁ pasted` 中。

## ☁ set clipboard {#set-clipboard}

当`☁ set clipboard`的值被更改时，页面将尝试将文本存储到用户的剪贴板中。这可能并不总是有效。

## ☁ room id {#room-id}

当 `☁ room id` 的值改变时，用于同步云变量的项目 ID 也会随之改变。例如，如果项目的原始 ID 是 1234，并且 `☁ room id` 被设置为 `xyz`，那么新的项目 ID 将是 `1234-xyz`。要将项目 ID 重置为原始 ID，请将 `☁ room id` 的值设置为空字符串。

这对于为云变量项目添加服务器选择器来说非常有用，无需创建一堆额外的变量。只有拥有相同room id 的人，他们之间的变量才会同步。重新连接到云变量服务器可能需要几秒钟的时间，云变量才能再次开始工作。

room id 不影响本地存储的云变量。

## ☁ eval {#eval}

!!! warning "注意啦"
    此选项需要启用“不安全的特殊云行为”。

    不安全的云行为允许打包后的项目在通常执行项目的“沙盒”之外执行任意代码。根据您打包的目标环境，这将使项目能够完全控制您的计算机，包括安装病毒的能力。

    如果您不信任正在打包的项目，或者不使用此功能，请关闭此选项。


当 `☁ eval` 的值改变时，它的值将被作为 JavaScript 代码来执行。

如果 JavaScript 成功执行，其输出将存储在 `☁ eval output` 中。

如果执行 JavaScript 时出错，错误信息将存储在 `☁ eval error` 中。

如果 JavaScript 返回一个 [Promise](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise)，那么当这个 promise 成功时，其解决的值会被存入 `☁ eval output`；如果 promise 失败，错误信息会被存入 `☁ eval error`。请注意，设置 `☁ eval` 总是一个瞬时过程，因此输出变量可能不会立即更新。

## 更多信息和讨论 {#further-information}

请参阅 https://github.com/TurboWarp/packager/issues/48
