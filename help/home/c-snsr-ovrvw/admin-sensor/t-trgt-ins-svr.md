---
description: 要更改传感器与之通信的Data Workbench Server（目标服务器），您必须在安装传感器的每个Web服务器上编辑txlogd.conf文件。
title: 更改目标 Data Workbench 服务器
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 6%

---

# 更改目标 Data Workbench 服务器{#changing-the-target-data-workbench-server}

{{eol}}

要更改传感器与之通信的Data Workbench Server（目标服务器），您必须在安装传感器的每个Web服务器上编辑txlogd.conf文件。

**更改为目标[!DNL data workbench server]**

1. 同时停止原始目标服务器和新目标服务器。
1. 复制最新 [!DNL .vsl] 从原始目标服务器到新目标服务器的文件。 在稍后的步骤中重新启动新目标服务器时，这会导致所有新 [!DNL Sensor] 要附加到当前现有数据中的数据 [!DNL .vsl] 文件，而不是创建新 [!DNL .vsl] 文件。 为此，请完成以下步骤：

   1. 在原始目标服务器上，浏览到 [!DNL \Logs] 文件夹 [!DNL data workbench server] 安装目录。

   1. 复制最新 [!DNL .vsl] 文件。
   1. 在新目标服务器上，浏览到 [!DNL \Logs] 文件夹 [!DNL data workbench server] 安装目录并粘贴 [!DNL .vsl] 文件到此文件夹。

1. 在其中一台Web服务器上， [!DNL Sensor] ，打开并编辑 [!DNL txlogd.conf] 文件。 为此，请完成以下步骤：

   1. 浏览到 [!DNL Sensor] 安装目录并打开 [!DNL txlogd.conf] 文件。

   1. 找到ServerAddress参数并对其进行更改，以反映新目标服务器的地址。
   1. 保存并关闭该文件。

1. 在其上的所有其余Web服务器上重复步骤2-3 [!DNL Sensor] 已安装。
1. 重新启动原始目标服务器（如果仍要使用）和新目标服务器。
1. 数据将开始传输到您指定的新目标服务器。
