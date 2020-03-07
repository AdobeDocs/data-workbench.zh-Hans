---
description: 'null'
solution: Insight,Analytics
title: 修改ExpPartialMatch参数（可选）
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改ExpPartialMatch参数（可选）{#modifying-the-exppartialmatch-parameter-optional}

如果要允许受控实验将整个网站或网站的整个子目录重新映射到另一个位置，则可以将文件中的ExpPartialMatch参数 [!DNL txlogd.conf] 设置为“on”。默认值为“off”。

以下是ExpPartialMatch参数的示例：

[!DNL ExpPartialMatch off]

将此参数设置为“on”时请务必小心，因为这可能会导致无意中重新映射整个网站。
