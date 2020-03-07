---
description: 卸载Insight Server、Transform或Repeater的说明。
solution: Insight
title: 卸载软件
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 卸载软件{#uninstalling-your-software}

卸载Insight Server、Transform或Repeater的说明。

## 卸载Insight Server Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. 取消注册 [!DNL Insight Server] Windows服务。

   1. 打开命令提示符，然后导航到您安装的文件夹中的bin子目录 [!DNL Insight Server]。

      示例：[!DNL C:\Adobe\Server\bin]

   1. 在命令提示符下，执行以下命令以在Microsoft Windows下停止并取消注册它为服务：

      ```
      InsightServer64.exe /unregserver
      ```

1. 删除安 [!DNL Insight Server] 装目录。

## 卸载转换 {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. 请按照以下步骤更新 [!DNL profile.cfg] 您所使用的每个配置文件的文件 [!DNL Transform]。

   1. 打开 [!DNL Profile Manager].
   1. 右键单击旁边的复选标记， [!DNL profile.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 The [!DNL profile.cfg] window appears.

   1. 在窗口 [!DNL profile.cfg] 中，从“目录” [!DNL Transform] 矢量中删除配置文件条目。

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在列 [!DNL Profile Manager]中，右键单击列中的复 [!DNL profile.cfg] 选 [!DNL User] 标记，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

1. 从安装目 [!DNL Transform] 录中的文 [!DNL Profiles] 件夹中删除 [!DNL Insight Server] 该文件夹。

## 卸载Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. 取消注册 [!DNL Repeater] Windows服务。

   1. 打开命令提示符，然后导航到您安装的文件夹中的bin子目录 [!DNL Repeater]。

      示例：[!DNL D:\Adobe\Repeater\bin]

   1. 在命令提示符下，执行以下命令以在Microsoft Windows下停止并取消注册它为服务：

      ```
      InsightServer64.exe /unregserver
      ```

1. 删除安 [!DNL Repeater] 装目录。

