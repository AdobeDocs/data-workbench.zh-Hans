---
description: 修改 ExpPartialMatch 参数（可选）
title: 修改 ExpPartialMatch 参数（可选）
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# 修改 ExpPartialMatch 参数（可选）{#modifying-the-exppartialmatch-parameter-optional}

{{eol}}

如果要启用对照实验将整个网站或网站的整个子目录重新映射到其他位置，可以在 [!DNL txlogd.conf] 文件到“on”。 默认值为“off”。

以下是ExpPartialMatch参数的示例：

[!DNL ExpPartialMatch off]

将此参数设置为“on”时要非常小心，因为这可能会导致无意中重新映射整个网站。
