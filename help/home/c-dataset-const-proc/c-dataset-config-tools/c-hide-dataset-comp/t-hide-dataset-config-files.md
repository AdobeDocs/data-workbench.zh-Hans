---
description: 如果您不希望从内部配置文件或其他继承配置文件中继承配置文件（也就是说，您希望在数据集构建期间忽略文件中的说明），但又不想要修改文件，则可以创建一个同名的空（零字节）文件，并将该文件存储在其他配置文件中。
solution: Analytics
title: 隐藏数据集配置文件
topic: Data workbench
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 隐藏数据集配置文件{#hiding-dataset-configuration-files}

如果您不希望从内部配置文件或其他继承配置文件中继承配置文件（也就是说，您希望在数据集构建期间忽略文件中的说明），但又不想要修改文件，则可以创建一个同名的空（零字节）文件，并将该文件存储在其他配置文件中。

**将数据集配置文件设为零字节**

1. In the [!DNL Profile Manager], open the necessary folders and subfolders to locate the file that you want to zero-byte.
1. Right-click the check mark next to the name of the file and click **[!UICONTROL Make Local]**.
1. 在文本编辑器（例如记事本）中打开本地文件，然后删除其内容。
1. 保存并关闭该文件。
1. In the [!DNL Profile Manager], save the zero-byte file to a profile to the right of the profile in which the original file resides. （您要使零字节文件优先于原始文件。）

   In the [!DNL Profile Manager], a hyphen (-), instead of a check mark, in a column identifies the zero-byte file as shown in the example below.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

当您重新处理数据集时，数据集不包含原始文件所定义的数据集组件。

>[!NOTE]
>
>如果将配置文件设置为零字节，该配置文件定义了在可视化或度量定义中使用的扩展维度，则Data Workbench会分别为该可视化或度量生成错误。

您还可以使用零字节文件将量度、维度或过滤器移到配置文件中的其他位置，或隐藏菜单项。有关信息，请参阅《Data Workbench 用户指南》**。
