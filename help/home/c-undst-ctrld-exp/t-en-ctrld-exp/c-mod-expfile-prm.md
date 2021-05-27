---
description: ExpFile参数指向实验配置文件的位置，该文件用于定义您的实验。
solution: Analytics,Analytics
title: 修改 ExpFile 参数
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# 修改 ExpFile 参数{#modifying-the-expfile-parameter}

ExpFile参数指向实验配置文件的位置，该文件用于定义您的实验。

通过设置此参数，可以运行实验。 有关创建实验配置文件的步骤，请参阅[配置和部署实验](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。

以下是ExpFile参数的示例：

```
ExpFile /home/experiment.txt
```

此制表符分隔的文本文件([!DNL .txt])可以位于[!DNL Sensor]文件夹中的任意位置，并且可以具有任何方便的名称。

确保记录实验目录的位置和您指定的配置文件的名称，因为您需要使用此名称和此目录中保存实验配置文件（将在本指南的后面部分进行说明）。

>[!NOTE]
>
>如果在安装[!DNL Sensor]的Web群集中的每台计算机上未设置相同的参数，则对照实验将不起作用。

此条目可以进行预配置，并持续保留在[!DNL Sensor]配置文件中，不会产生不良影响。 如果[!DNL Sensor]未找到指定的实验配置文件名或该文件名为空（即存在但没有内容），则[!DNL Sensor]不进行实验，在HTTP服务器上记录错误事件，并在所有其他方面继续正常运行。
