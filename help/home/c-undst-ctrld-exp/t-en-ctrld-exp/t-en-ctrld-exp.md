---
description: 要启用受控试验，对Web或应用程序服务器具有管理员访问权限的人员必须在安装了传感器的Web群集中的每个Web或应用程序服务器上修改传感器配置文件（通常使用txlogd.conf命名）中的ExpFile参数。
solution: Analytics,Analytics
title: 启用对照实验
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 4%

---

# 启用对照实验{#enabling-controlled-experimentation}

要启用受控试验，对Web或应用程序服务器具有管理员访问权限的人员必须在安装了传感器的Web群集中的每个Web或应用程序服务器上修改传感器配置文件（通常使用txlogd.conf命名）中的ExpFile参数。

此外，可以修改此文件中的两个其他参数，以实现测试工具（ExpCookieURL参数）或重新映射网站的大部分（ExpPartialMatch参数）。 本章提供了有关这些参数的详细信息。

**编辑txlogd.conf文件**

如果您具有管理员访问权限，请完成以下步骤。 如果您没有管理员访问权限，请与系统架构师联系以请求更改，并向他们提供以下步骤。

1. 导览至安装[!DNL Sensor]的Web群集中的Web或应用程序服务器上的[!DNL Sensor]安装文件夹。
1. 使用文本编辑器打开[!DNL Sensor]配置文件（通常使用[!DNL txlogd.conf]命名），并编辑[修改ExpFile参数](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)中指示的文件。

   (在[修改ExpCookieURL参数（可选）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)和[修改ExpPartialMatch参数（可选）](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e)中也可选。)

1. 保存并关闭该文件。
1. 对安装[!DNL Sensor]的Web群集中的每台Web服务器或应用程序服务器重复此过程。
