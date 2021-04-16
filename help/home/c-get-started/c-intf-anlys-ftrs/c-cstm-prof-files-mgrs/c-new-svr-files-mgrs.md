---
description: “服务器文件管理器”显示Data Workbench服务器安装目录中的所有目录，包括配置和查找文件。
title: 创建服务器文件管理器
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# 创建服务器文件管理器{#create-a-server-files-manager}

“服务器文件管理器”显示Data Workbench服务器安装目录中的所有目录，包括配置和查找文件。

您可能希望访问[!DNL Server Files Manager]的一部分，而无需导航其整个目录结构或只显示几个子目录来满足特定需求。 例如，您可能希望创建一个单独的[!DNL Server Files Manager]，该仅显示“访问控制”和“用户”子目录，以便管理您的用户及其访问权限。

您创建的每个管理器都必须有一个[!DNL .vw]文件。 可以将[!DNL Server Files.vw]文件用作模板。

有关[!DNL Server Files Manager]的详细信息，请参阅[服务器文件管理器](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)。

**创建服务器文件管理器**

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Menu]**&#x200B;目录，然后单击&#x200B;**[!UICONTROL Admin]**&#x200B;目录。 [!DNL Server Files.vw]文件位于此处。
1. 在&#x200B;*用户档案名称*&#x200B;列中，右键单击[!DNL Server Files.vw]文件的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 文件的复选标记显示在[!DNL User]列中。
1. 右键单击[!DNL User]列中[!DNL Server Files.vw]文件的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 将打开[!DNL Server Files.vw]文件。
1. 要删除目录，请右键单击[!DNL Server Files Manager]的上边框，然后单击&#x200B;**[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*。
1. 要添加目录，请右键单击[!DNL Server Files Manager]的上边框，单击&#x200B;**[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**。

   在URI字段中键入目录的URI，然后单击&#x200B;**[!UICONTROL OK]**。

   >[!NOTE]
   >
   >您可以在URI字段中指定多个目录。 例如，如果键入 [!DNL Profiles\Marketing\]，则服务器文件管理器包含Marketing子目录，但用户档案目录中没有其他子目录。

1. 右键单击[!DNL Server Files Manager]顶部边框，然后单击&#x200B;**[!UICONTROL Save]**。
1. 要创建新管理器，请更改[!DNL File Name]字段中的文件名，然后单击&#x200B;**[!UICONTROL Save]**。 要覆盖现有管理器，请单击&#x200B;**[!UICONTROL Save]**。
1. （可选）要使更改对工作用户档案的所有用户可用，请右键单击[!DNL User]列中[!DNL .vw]文件的复选标记。

   然后，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
