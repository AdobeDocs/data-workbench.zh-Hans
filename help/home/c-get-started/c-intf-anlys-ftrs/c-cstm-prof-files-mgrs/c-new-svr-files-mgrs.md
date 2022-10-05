---
description: “服务器文件管理器”显示Data Workbench服务器安装目录中的所有目录，包括配置和查找文件。
title: 创建服务器文件管理器
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# 创建服务器文件管理器{#create-a-server-files-manager}

{{eol}}

“服务器文件管理器”显示Data Workbench服务器安装目录中的所有目录，包括配置和查找文件。

您可能想要访问 [!DNL Server Files Manager] 无需导航其整个目录结构或仅显示几个子目录来满足特定需求。 例如，您可能想要创建一个单独的 [!DNL Server Files Manager] “访问控制”和“用户”子目录，以便管理用户及其访问权限。

您创建的每个管理器都必须具有 [!DNL .vw] 文件。 您可以使用 [!DNL Server Files.vw] 文件。

有关 [!DNL Server Files Manager]，请参阅 [服务器文件管理器](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**创建服务器文件管理器**

1. 在 [!DNL Profile Manager]，请单击 **[!UICONTROL Menu]** 目录，然后 **[!UICONTROL Admin]** 目录访问Advertising Cloud的帮助。 的 [!DNL Server Files.vw] 文件位于此处。
1. 在 *配置文件名称* 列中，右键单击 [!DNL Server Files.vw] 文件，单击 **[!UICONTROL Make Local]**. 文件的复选标记将显示在 [!DNL User] 列。
1. 右键单击 [!DNL Server Files.vw] 文件 [!DNL User] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 的 [!DNL Server Files.vw] 文件。
1. 要删除目录，请右键单击 [!DNL Server Files Manager] 单击 **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. 要添加目录，请右键单击 [!DNL Server Files Manager]，单击 **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   在URI字段中键入目录的URI，然后单击 **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >您可以在URI字段中指定多个目录。 例如，如果您在 [!DNL Profiles\Marketing\]，则服务器文件管理器包含Marketing子目录，但Profiles目录内没有其他子目录。

1. 右键单击 [!DNL Server Files Manager] 单击 **[!UICONTROL Save]**.
1. 要创建新管理器，请在 [!DNL File Name] 字段，然后单击 **[!UICONTROL Save]**. 要覆盖现有管理器，请单击 **[!UICONTROL Save]**.
1. （可选）若要使更改对工作配置文件的所有用户可用，请右键单击 [!DNL .vw] 文件 [!DNL User] 列。

   然后，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
