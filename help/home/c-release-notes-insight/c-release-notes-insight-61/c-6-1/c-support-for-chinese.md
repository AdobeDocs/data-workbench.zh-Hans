---
description: Data Workbench 客户端应用程序现在支持简体中文。
solution: Analytics
title: 简体中文本地化
topic: Data workbench
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 简体中文本地化{#simplified-chinese-localization}

Data Workbench 客户端应用程序现在支持简体中文。

**安装简体中文版**：

在配置 [!DNL Insight.exe] 和支持文件之前，必须退出客户端应用程序。

1. 创建一个用于传入命令行设置的 [!DNL insight.exe] 文件快捷方式。

   ```
   Insight.exe -zh-cn
   ```

1. 将 [!DNL Insight.cfg] 配置为支持单字节和双字节字体字符。

   Data Workbench 目前支持英语和简体中文。您可以选择以下字体以支持这两种语言：

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. 重新启动 [!DNL Insight.exe].

