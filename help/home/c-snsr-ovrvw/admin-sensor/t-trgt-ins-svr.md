---
description: 要更改传感器与之通信的Data Workbench Server（目标服务器），您必须在安装传感器的每台Web服务器上编辑txlogd.conf文件。
solution: Insight
title: 更改目标Data Workbench Server
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 更改目标Data Workbench Server{#changing-the-target-data-workbench-server}

要更改传感器与之通信的Data Workbench Server（目标服务器），您必须在安装传感器的每台Web服务器上编辑txlogd.conf文件。

**更改为目标[!DNL data workbench server]**

1. 停止原始目标服务器和新目标服务器。
1. 将最新文件从 [!DNL .vsl] 原始目标服务器复制到新目标服务器。 在以后的步骤中重新启动新目标服务器时，这会导致所有新数据附加到当前的现有 [!DNL Sensor] 文件，而 [!DNL .vsl] 不是创建新文 [!DNL .vsl] 件。 为此，请完成以下步骤：

   1. 在原始目标服务器上，浏览到安 [!DNL \Logs] 装目录中的文 [!DNL data workbench server] 件夹。

   1. 复制文件夹中 [!DNL .vsl] 的最新文件。
   1. 在新目标服务器上，浏览至安装目 [!DNL \Logs] 录中的文件 [!DNL data workbench server] 夹，然后将文件粘 [!DNL .vsl] 贴到此文件夹。

1. 在安装了Web服务器之 [!DNL Sensor] 一上，打开并编辑文 [!DNL txlogd.conf] 件。 为此，请完成以下步骤：

   1. 浏览到安 [!DNL Sensor] 装目录，并在文本编 [!DNL txlogd.conf] 辑器中打开文件。

   1. 找到ServerAddress参数并对其进行更改，以反映新目标服务器的地址。
   1. 保存并关闭该文件。

1. 在安装的所有其余Web服务器上重复第2-3 [!DNL Sensor] 步。
1. 重新启动原始目标服务器（如果仍要使用它）和新的目标服务器。
1. 数据将开始传输到您指定的新目标服务器。
