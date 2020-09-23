---
description: 'null'
solution: Analytics,Analytics
title: 修改 ExpPartialMatch 参数（可选）
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 14%

---


# 修改 ExpPartialMatch 参数（可选）{#modifying-the-exppartialmatch-parameter-optional}

如果要启用受控实验将整个网站或网站的整个子目录重新映射到另一个位置，可在文件中将ExpPartialMatch参数 [!DNL txlogd.conf] 设置为“on”。 默认值为“off”。

以下是ExpPartialMatch参数的示例：

[!DNL ExpPartialMatch off]

将此参数设置为“on”时请务必小心，因为这可能会导致无意中重新映射整个网站。
