---
description: 要更改传感器与之通信的目标工作台服务器（数据服务器），您必须在安装传感器的每个Web服务器上编辑txlogd.conf文件。
solution: Analytics
title: 更改目标 Data Workbench 服务器
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 6%

---


# 更改目标 Data Workbench 服务器{#changing-the-target-data-workbench-server}

要更改传感器与之通信的目标工作台服务器（数据服务器），您必须在安装传感器的每个Web服务器上编辑txlogd.conf文件。

**更改为目标[!DNL data workbench server]**

1. 停止原始目标服务器和新目标服务器。
1. 将最新文件从 [!DNL .vsl] 原始目标服务器复制到新目标服务器。 在以后的步骤中重新启动新目标服务器时，这会导致所有新 [!DNL Sensor] 都附加到当前现有文件，而 [!DNL .vsl] 不是创建新文 [!DNL .vsl] 件。 为此，请完成以下步骤：

   1. 在原始目标服务器上，浏览到安 [!DNL \Logs] 装目录中的 [!DNL data workbench server] 文件夹。

   1. 复制文件夹中 [!DNL .vsl] 的最新文件。
   1. 在新的目标服务器上，浏览至安 [!DNL \Logs] 装目录中的 [!DNL data workbench server] 文件夹，然后将文 [!DNL .vsl] 件粘贴到此文件夹中。

1. 在安装了某台Web服务 [!DNL Sensor] 器上，打开并编辑文 [!DNL txlogd.conf] 件。 为此，请完成以下步骤：

   1. 浏览到安 [!DNL Sensor] 装目录，在文本 [!DNL txlogd.conf] 编辑器中打开文件。

   1. 找到ServerAddress参数并对其进行更改，以反映新目标服务器的地址。
   1. 保存并关闭该文件。

1. 对安装的所有其余Web服务器重复步骤2 [!DNL Sensor] -3。
1. 重新启动原始目标服务器（如果仍要使用）和新目标服务器。
1. 数据将开始传输到您指定的新目标服务器。
