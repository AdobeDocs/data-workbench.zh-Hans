---
description: 侧栏提供对常用功能的访问，并且当您在工作区之间移动时还会保留可视化。
title: 配置边栏
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 36%

---

# 配置边栏{#configure-the-sidebar}

{{eol}}

侧栏提供对常用功能的访问，并且当您在工作区之间移动时还会保留可视化。

管理员可以自定义侧栏，使其适合不同的用户组，然后通过配置文件部署侧栏。

侧栏最适合帮您跟踪过滤器和本地覆盖。如果您不想使用侧栏，可以将其隐藏。

## 向侧栏中添加可视化 {#section-666f70a405db4f8d8eaffa567ffcac06}

1. 启动Data Workbench。
1. 在侧栏中，单击 **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. 例如，[!DNL Selections Panel]、[!DNL Filters Panel] 或 [!DNL Table]。

   标准安装中提供了以下侧栏面板Data Workbench。 您的特定配置文件中可能提供了更多项目：

   * **选择面板：** 让您了解当前工作区中哪些选项处于活动状态。 的 [!DNL Selections Panel] 当您进行新选择时，会进行更新。 您可以通过单击 **[!UICONTROL x]**. 请参阅 [在可视化中进行选择](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) 以了解有关如何选择数据的信息。
   * **过滤器面板：** 可轻松加载和应用保存的过滤器。 您可以加载多个过滤器，并且可以通过单击过滤器旁边的复选框来单独启用或禁用每个过滤器。请参阅 [过滤器编辑器](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **本地覆盖面板：** 此面板会显示配置文件中存在的哪些量度、维度和过滤器已在配置文件的个人副本中进行了修改。 这有助于提示您，在您的客户端和其他用户的客户端中显示数据的方式可能有所不同。将量度、维度或过滤器中的更改保存到服务器后，将从 [!DNL Local Overrides panel]. 如果单击覆盖，然后单击 **[!UICONTROL Revert to Server]**，则会删除本地覆盖，并且项目将还原为共享版本。
   * **量度图例：** 添加量度图例。 [!DNL Metric legends] 让您能够查看与配置文件相关的基线量度和与数据集相关的统计信息(或与当前选定内容相关的统计信息（如果已经进行了选择）。 请参阅 [量度图例](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **颜色图例：** 添加颜色图例。 您可以按量度（如“转化”和“维系”）对可视化图表进行颜色编码，并且几乎可以在每个量度中使用 [!DNL Workspace]. 将业务量度与颜色链接在一起更便于发现异常情况、例外和趋势。请参阅[颜色图例](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)。
   * **文本批注：** 添加注释面板。 [!DNL Text annotations] 是可在其中输入任意文本以向其添加描述性信息或注释的窗口 [!DNL Workspace]. 请参阅 [使用文本批注](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **表：** 添加表。 表格可以跨一个或多个数据维度显示一个或多个量度。请参阅 [表格](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **打开：** 打开保存的文件。

## 打开侧栏面板 {#section-cbc8e57491854274a577d47a48c306b8}

可以从保存的位置或从剪贴板中打开侧栏可视化文件。

1. 在侧栏中，单击 **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. 单击 **[!UICONTROL File]** 查找 [!DNL .vw] 要添加的面板的文件，或单击 **[!UICONTROL Last Closed Window]**，可从剪贴板中提取可视化图表。

   此外，您还可以单击 **[!UICONTROL From Clipboard]** 粘贴已复制到剪贴板的可视化。 请参阅[复制侧栏面板](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1)。

## 复制侧栏面板 {#section-720ae057632a4b8dbb94412e06a370b1}

1. 右键单击面板的上边框，然后单击 **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. 要粘贴面板，请单击 **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## 保存侧栏面板 {#section-fb19936b12704fb0a4c592abb579db1d}

在侧栏面板上，右键单击标题栏，然后单击 **[!UICONTROL Save]**.

同样，可以打开保存的侧栏可视化。Data Workbench将可视化另存为 [!DNL .vw] 文件。

## 还原到默认侧栏 {#section-4d14b8771ad747bba799876267f24831}

在侧栏中，单击 **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

关闭Data Workbench时，系统会在 [!DNL sidebar.vw] 文件。 打开Data Workbench时，系统会加载 [!DNL sidebar.vw] 文件，而不是父配置文件。

可以还原到默认或以前保存的侧栏，该操作会从用户配置文件中删除侧栏并从父侧栏中重新加载侧栏。管理员可以通过从 [!DNL Profile Manager].

## 自定义更多状态面板文件 {#section-8d502f3b59cc4331966edec05e896ce1}

系统管理员可以在 [!DNL More Status Panel.vw]. 这会在量度和维度值周围放置上下文词语，并在 [!DNL More Status panel] 中。

显示 [!DNL More Status panel] 在侧栏中，单击以下示例中显示的箭头。

![](assets/more_status_panel_arrows.png)

以下过程显示一个简单示例，说明如何创建一个告诉您数据集中天数的自定义状态：

1. 在 [!DNL Profile Manager]，单击 **[!UICONTROL Sidebar\]**.

1. 在 [!DNL Base_5_3*] 列中，创建本地副本 [!DNL More Status Panel.vw] 文件。

   为此，请右键单击文件复选标记，然后单击 **[!UICONTROL Make Local]**.

1. 打开 [!DNL More Status Panel.vw] 文件 [!DNL .vw] [!DNL Editor] 或在记事本中。

   ![](assets/more_status_panel_file.png)

1. 完成 [!DNL Context] 和 [!DNL Items] 字段 [!DNL Editor]. 请参阅 [查询语言语法](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) 有关语法的准则。

1. 保存文件。

   上例中的值产生如下所示的状态公式：

   ![](assets/more_status_panel.png)
