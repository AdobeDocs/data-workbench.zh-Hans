---
description: 卸载Insight Server、转换或中继器的说明。
title: 卸载软件
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# 卸载软件{#uninstalling-your-software}

{{eol}}

卸载Insight Server、转换或中继器的说明。

## 卸载Insight ServerAdobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. 取消注册 [!DNL Insight Server] Windows服务。

   1. 打开命令提示符，然后导航到安装文件夹中的bin子目录 [!DNL Insight Server].

      示例：[!DNL C:\Adobe\Server\bin]

   1. 在命令提示符下，执行以下命令以在Microsoft Windows下停止并取消注册为服务：

      ```
      InsightServer64.exe /unregserver
      ```

1. 删除 [!DNL Insight Server] 安装目录。

## 卸载转换 {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. 请按照以下步骤更新 [!DNL profile.cfg] 文件 [!DNL Transform].

   1. 打开 [!DNL Profile Manager].
   1. 右键单击旁边的复选标记 [!DNL profile.cfg] 单击 **[!UICONTROL Make Local]**. 此文件的复选标记将显示在 [!DNL User] 列。

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 的 [!DNL profile.cfg] 窗口。

   1. 在 [!DNL profile.cfg] 窗口，删除 [!DNL Transform] 目录矢量中的用户档案条目。

   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

   1. 在 [!DNL Profile Manager]，右键单击的复选标记 [!DNL profile.cfg] 在 [!DNL User] 列，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. 删除 [!DNL Transform] 文件夹 [!DNL Profiles] 文件夹中 [!DNL Insight Server] 安装目录。

## 卸载中继器 {#section-2f94141d956749d88f549dbea26e5272}

1. 取消注册 [!DNL Repeater] Windows服务。

   1. 打开命令提示符，然后导航到安装文件夹中的bin子目录 [!DNL Repeater].

      示例：[!DNL D:\Adobe\Repeater\bin]

   1. 在命令提示符下，执行以下命令以在Microsoft Windows下停止并取消注册为服务：

      ```
      InsightServer64.exe /unregserver
      ```

1. 删除 [!DNL Repeater] 安装目录。
