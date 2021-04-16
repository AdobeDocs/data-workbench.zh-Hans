---
description: 要更改传感器与之通信的Data Workbench Server(目标服务器)，您必须在安装传感器的每个Web服务器上编辑txlogd.conf文件。
title: 更改目标 Data Workbench 服务器
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 6%

---

# 更改目标 Data Workbench 服务器{#changing-the-target-data-workbench-server}

要更改传感器与之通信的Data Workbench Server(目标服务器)，您必须在安装传感器的每个Web服务器上编辑txlogd.conf文件。

**更改为目标[!DNL data workbench server]**

1. 停止原始目标服务器和新目标服务器。
1. 将最新[!DNL .vsl]文件从原始目标服务器复制到新目标服务器。 在以后的步骤中重新启动新的目标服务器时，这会导致所有新[!DNL Sensor]数据附加到当前的现有[!DNL .vsl]文件，而不是创建新的[!DNL .vsl]文件。 为此，请完成以下步骤：

   1. 在原始目标服务器上，浏览至[!DNL data workbench server]安装目录中的[!DNL \Logs]文件夹。

   1. 复制文件夹中最新的[!DNL .vsl]文件。
   1. 在新的目标服务器上，浏览至[!DNL data workbench server]安装目录中的[!DNL \Logs]文件夹，然后将[!DNL .vsl]文件粘贴到此文件夹。

1. 在安装了[!DNL Sensor]的某个Web服务器上，打开并编辑[!DNL txlogd.conf]文件。 为此，请完成以下步骤：

   1. 浏览至[!DNL Sensor]安装目录，并在文本编辑器中打开[!DNL txlogd.conf]文件。

   1. 找到ServerAddress参数并更改它以反映新目标服务器的地址。
   1. 保存并关闭该文件。

1. 对安装[!DNL Sensor]的所有其余Web服务器重复步骤2-3。
1. 重新启动原始目标服务器（如果仍要使用）和新的目标服务器。
1. 数据将开始传输到您指定的新目标服务器。
