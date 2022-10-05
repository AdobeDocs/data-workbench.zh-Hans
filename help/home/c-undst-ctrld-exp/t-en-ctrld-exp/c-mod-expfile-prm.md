---
description: ExpFile参数指向实验配置文件的位置，该文件用于定义您的实验。
solution: Analytics
title: 修改 ExpFile 参数
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# 修改 ExpFile 参数{#modifying-the-expfile-parameter}

{{eol}}

ExpFile参数指向实验配置文件的位置，该文件用于定义您的实验。

通过设置此参数，可以运行实验。 有关创建实验配置文件的步骤，请参阅 [配置和部署实验](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

以下是ExpFile参数的示例：

```
ExpFile /home/experiment.txt
```

此制表符分隔的文本文件( [!DNL .txt])可位于 [!DNL Sensor] 文件夹，并且可以使用任何方便的名称。

确保记录实验目录的位置和您指定的配置文件的名称，因为您需要使用此名称和此目录中保存实验配置文件（将在本指南的后面部分进行说明）。

>[!NOTE]
>
>如果未在Web群集中的每台计算机上(其中 [!DNL Sensor] 安装时，对照实验不起作用。

此条目可以进行预配置，并保留在 [!DNL Sensor] 不断配置文件，且没有不良影响。 如果未找到指定的实验配置文件名 [!DNL Sensor] 或为空（即存在但没有内容）， [!DNL Sensor] 不进行实验，在HTTP服务器上记录错误事件，并在所有其他方面继续正常运行。
