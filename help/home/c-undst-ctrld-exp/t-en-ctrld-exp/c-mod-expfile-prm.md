---
description: ExpFile参数指向实验配置文件的位置，该文件定义了您的实验。
solution: Insight,Analytics
title: 修改ExpFile参数
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改ExpFile参数{#modifying-the-expfile-parameter}

ExpFile参数指向实验配置文件的位置，该文件定义了您的实验。

通过设置此参数，您可以运行实验。 有关创建实验配置文件的步骤，请参 [阅配置和部署实验](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。

以下是ExpFile参数的示例：

```
ExpFile /home/experiment.txt
```

此制表符分隔的文本文件( [!DNL .txt])可以位于文件夹中的任 [!DNL Sensor] 何位置，并可以具有任何方便的名称。

请确保记录实验目录的位置和您指定的配置文件的名称，因为您需要使用此名称和此目录中保存实验配置文件（将在本指南的后面进行说明）。

>[!NOTE]
>
>如果未在安装了Web群集的每台计算机上以相同方式设置此参 [!DNL Sensor] 数，则无法进行受控试验。

此条目可以预配置，并持续保 [!DNL Sensor] 留在配置文件中，不会产生任何不良影响。 如果未找到指定的实验配置文件名称，或者它为空（即，它存在但没有内容），则不进行实验，在HTTP服务器上记录错误事件，并在所有其他方面继续正常运行。 [!DNL Sensor][!DNL Sensor]
