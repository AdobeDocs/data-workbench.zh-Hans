---
description: 侧栏提供对常用功能的访问，并且当您在工作区之间移动时还会保留可视化。
title: 配置边栏
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 36%

---

# 配置边栏{#configure-the-sidebar}

侧栏提供对常用功能的访问，并且当您在工作区之间移动时还会保留可视化。

管理员可以自定义侧栏，使其适合不同的用户组，然后通过配置文件部署侧栏。

侧栏最适合帮您跟踪过滤器和本地覆盖。如果您不想使用侧栏，可以将其隐藏。

## 向提要栏{#section-666f70a405db4f8d8eaffa567ffcac06}添加可视化

1. 启动Data Workbench。
1. 在提要栏中，单击&#x200B;**[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*。 例如，[!DNL Selections Panel]、[!DNL Filters Panel] 或 [!DNL Table]。

   标准安装中提供了以下侧栏面板。 您的特定配置文件中可能提供了更多项目：

   * **选择面板：** 允许您了解当前工作区中处于活动状态的选择。每当您做出新选择时，[!DNL Selections Panel]都会更新。 单击&#x200B;**[!UICONTROL x]**&#x200B;可清除选择。 有关如何选择数据的信息，请参阅可视化](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746)中的[进行选择。
   * **过滤器面** 板：可轻松加载和应用保存的过滤器。您可以加载多个过滤器，并且可以通过单击过滤器旁边的复选框来单独启用或禁用每个过滤器。请参阅 [过滤器编辑器](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **本地覆盖面** 板：此面板显示在用户档案中存在的量度、维度和过滤器已在用户档案的个人副本中修改。这有助于提示您，在您的客户端和其他用户的客户端中显示数据的方式可能有所不同。将量度、维度或过滤器中的更改保存到服务器时，将从[!DNL Local Overrides panel]中删除该覆盖。 如果单击覆盖，然后单击&#x200B;**[!UICONTROL Revert to Server]**，则删除本地覆盖，项恢复为共享版本。
   * **量度图例：** 添加量度图例。[!DNL Metric legends] 允许您查看与用户档案相关的基线量度和与数据集(或与当前选定内容（如果已进行了选择）相关的统计信息。请参阅[量度图例](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b)。
   * **颜色图例：** 添加颜色图例。您可以按“转换”和“保留”等指标对可视化进行颜色编码，并且几乎每[!DNL Workspace]都可使用这些可视化。 将业务量度与颜色链接在一起更便于发现异常情况、例外和趋势。请参阅[颜色图例](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)。
   * **文本注释：** 添加注释面板。[!DNL Text annotations] 是可在其中输入任意文本以向添加描述性信息或注释的窗口 [!DNL Workspace]请参阅[使用文本注释](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777)。
   * **表：** 添加表。表格可以跨一个或多个数据维度显示一个或多个量度。请参阅[表](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f)。
   * **打开：** 打开保存的文件。

## 打开侧栏面板{#section-cbc8e57491854274a577d47a48c306b8}

可以从保存的位置或从剪贴板中打开侧栏可视化文件。

1. 在提要栏中，单击&#x200B;**[!UICONTROL Add]** > **[!UICONTROL Open]**。
1. 单击&#x200B;**[!UICONTROL File]**&#x200B;以找到要添加的面板的[!DNL .vw]文件，或单击&#x200B;**[!UICONTROL Last Closed Window]**，将可视化从剪贴板拉出。

   此外，您还可以单击&#x200B;**[!UICONTROL From Clipboard]**&#x200B;粘贴已复制到剪贴板的可视化。 请参阅[复制侧栏面板](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1)。

## 复制侧栏面板  {#section-720ae057632a4b8dbb94412e06a370b1}

1. 右键单击面板的上边框，然后单击&#x200B;**[!UICONTROL Copy]** > **[!UICONTROL Window]**。
1. 要粘贴面板，请单击&#x200B;**[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**。

## 保存侧栏面板 {#section-fb19936b12704fb0a4c592abb579db1d}

在侧栏面板上，右键单击标题栏，然后单击&#x200B;**[!UICONTROL Save]**。

同样，可以打开保存的侧栏可视化。Data Workbench在您指定的位置将可视化另存为[!DNL .vw]文件。

## 还原到默认侧栏{#section-4d14b8771ad747bba799876267f24831}

在提要栏中，单击&#x200B;**[!UICONTROL Options]** > **[!UICONTROL Revert]**。

关闭Data Workbench时，系统会将当前侧栏配置保存在用户用户档案的[!DNL sidebar.vw]文件中。 打开Data Workbench时，系统从用户用户档案加载[!DNL sidebar.vw]文件，而不是从父用户档案加载。

可以还原到默认或以前保存的侧栏，该操作会从用户配置文件中删除侧栏并从父侧栏中重新加载侧栏。管理员可以从[!DNL Profile Manager]上载默认（父级）侧栏，将其替换为本地侧栏。

## 自定义更多状态面板文件{#section-8d502f3b59cc4331966edec05e896ce1}

系统管理员可以在[!DNL More Status Panel.vw]中构建公式。 这会在量度和维度值周围放置上下文词，并在提要栏中的[!DNL More Status panel]中显示结果。

要在提要栏中显示[!DNL More Status panel]，请单击以下示例中显示的箭头。

![](assets/more_status_panel_arrows.png)

以下过程显示一个简单示例，说明如何创建一个告诉您数据集中天数的自定义状态：

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Sidebar\]**。

1. 在[!DNL Base_5_3*]列中，制作[!DNL More Status Panel.vw]文件的本地副本。

   为此，请右键单击文件复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。

1. 在[!DNL .vw] [!DNL Editor]或记事本中打开[!DNL More Status Panel.vw]文件。

   ![](assets/more_status_panel_file.png)

1. 填写[!DNL Editor]中的[!DNL Context]和[!DNL Items]字段。 有关语法的准则，请参见[查询语言语法](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)。

1. 保存文件。

   上例中的值产生如下所示的状态公式：

   ![](assets/more_status_panel.png)
