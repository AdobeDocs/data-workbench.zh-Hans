---
description: 修改 ExpPartialMatch 参数（可选）
title: 修改 ExpPartialMatch 参数（可选）
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# 修改 ExpPartialMatch 参数（可选）{#modifying-the-exppartialmatch-parameter-optional}

如果要启用控制实验将整个网站或网站的整个子目录重新映射到另一个位置，则可以将[!DNL txlogd.conf]文件中的ExpPartialMatch参数设置为“on”。 默认为“off”。

以下是ExpPartialMatch参数的示例：

[!DNL ExpPartialMatch off]

将此参数设置为“on”时请务必小心，因为这可能会导致无意中重新映射整个网站。
