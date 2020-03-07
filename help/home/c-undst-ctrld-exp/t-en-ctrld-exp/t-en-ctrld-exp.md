---
description: 要启用受控试验，对Web或应用程序服务器具有管理员访问权限的人员必须在安装了传感器的Web群集中的每台Web或应用程序服务器上修改传感器配置文件（通常使用txlogd.conf命名）中的ExpFile参数。
solution: Insight,Analytics
title: 启用受控试验
topic: Data workbench
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 启用受控试验{#enabling-controlled-experimentation}

要启用受控试验，对Web或应用程序服务器具有管理员访问权限的人员必须在安装了传感器的Web群集中的每台Web或应用程序服务器上修改传感器配置文件（通常使用txlogd.conf命名）中的ExpFile参数。

此外，可以修改此文件中的两个其他参数，以实现测试工具（ExpCookieURL参数）或重新映射网站的大部分（ExpPartialMatch参数）。 本章提供了有关这些参数的详细信息。

**编辑txlogd.conf文件**

如果您有管理员访问权限，请完成以下步骤。 如果您没有管理员访问权限，请与系统架构师联系以请求更改，并为它们提供以下步骤。

1. 导航到Web [!DNL Sensor] 服务器上的安装文件夹或安装了Web群集中的应用程序服 [!DNL Sensor] 务器上。
1. 使用文 [!DNL Sensor] 本编辑器打开配置文件(通常使用命 [!DNL txlogd.conf]名)并编辑文件，如修改ExpFile参数 [中所示](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)。

   (也可以在修改 [ExpCookieURL参数（可选）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) 和修 [改ExpPartialMatch参数（可选）中进行选择](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e)。)

1. 保存并关闭该文件。
1. 对安装了Web群集的每台Web服务器或应用程序服务器重复 [!DNL Sensor] 此过程。
