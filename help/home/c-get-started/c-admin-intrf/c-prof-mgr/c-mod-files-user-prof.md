---
description: 您可以使用“配置文件管理器”下载要修改的文件。
title: 在用户配置文件中修改本地文件
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 48%

---

# 在用户配置文件中修改本地文件{#modify-local-files-in-the-user-profile}

您可以使用“配置文件管理器”下载要修改的文件。

您可能要下载一个文件，以使用该文件的原始版本覆盖您现有的本地文件，或者打开、查看并修改无法从工作区菜单访问的文件。

**下载文件**

1. 在[!DNL Profile Manager]中，打开必要的文件夹和子文件夹以找到要下载的文件。
1. 右键单击文件名称旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。

   >[!NOTE]
   >
   >配置([!DNL .cfg])、维度([!DNL .dim])和量度([!DNL .metric])文件可以直接在用户档案文件夹中编辑并保存到服务器，而无需将它们本地化并分别保存到服务器。 只需右键单击文件名称旁的复选标记，然后单击工作站&#x200B;**中的&#x200B;**[!UICONTROL Open]**>**。

将文件下载到本地计算机后，[!DNL User]列中会显示一个复选标记，指示文件的本地副本驻留在计算机上的User\*用户档案 name*文件夹中。 请注意，复选标记的颜色与&#x200B;*配置文件名称*&#x200B;列中的复选标记相同。这表示本地文件与&#x200B;*配置文件名称*&#x200B;文件夹中的文件具有相同的修改日期和时间。

**修改文件**

1. 右键单击[!DNL User]列中文件名旁边的复选标记。
1. 单击以下菜单选项之一，具体选择取决于您希望如何编辑文件：

   * **[!UICONTROL Open]** >  **[!UICONTROL in workstation]** if you are editing a  [!DNL .vw] file or  [!DNL .cfg] file in a workspace

   * **打开** > **in vw。编辑器**（如果您正在编辑.vw文件以添加新参数）。

   * **[!UICONTROL Open]** >  **[!UICONTROL In Notepad]** if you opening a text file or need to add new parameters to a  [!DNL .cfg] file.

   * **[!UICONTROL Open]** >  **[!UICONTROL folder]** if you want to open the file is where the file on your computer

1. 根据需要编辑文件，然后保存该文件。

在[!DNL Profile Manager]中，请注意，您所编辑文件的[!DNL User]列中的复选标记已更改颜色。 这表示本地文件现在不同于&#x200B;*配置文件名称*&#x200B;文件夹中的版本。如有必要，可以将文件的修改版本发布到配置文件，以供使用此配置文件的其他用户使用。
