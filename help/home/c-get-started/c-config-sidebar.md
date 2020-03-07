---
description: 侧栏提供对常用功能的访问，并且当您在工作区之间移动时还会保留可视化。
solution: Analytics
title: 配置提要栏
topic: Data workbench
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置提要栏{#configure-the-sidebar}

侧栏提供对常用功能的访问，并且当您在工作区之间移动时还会保留可视化。

管理员可以自定义侧栏，使其适合不同的用户组，然后通过配置文件部署侧栏。

侧栏最适合帮您跟踪过滤器和本地覆盖。如果您不想使用侧栏，可以将其隐藏。

## Add visualizations to the sidebar {#section-666f70a405db4f8d8eaffa567ffcac06}

1. 启动Data Workbench。
1. 在提要栏中，单 **[!UICONTROL Add]** 击> *&lt;**[!UICONTROL item]**>*。 For example, [!DNL Selections Panel], [!DNL Filters Panel], or [!DNL Table].

   Data Workbench的标准安装中提供以下提要栏面板。 您的特定配置文件中可能提供了更多项目：

   * **选择面板：** 让您了解当前工作区中哪些选择处于活动状态。 只要 [!DNL Selections Panel] 您做出新选择，就会更新。 您可以通过单击来清除选择 **[!UICONTROL x]**。 See [Making Selections in Visualizations](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) for information about how to select data.
   * **滤镜面板：** 使加载和应用保存的过滤器变得很容易。 您可以加载多个过滤器，并且可以通过单击过滤器旁边的复选框来单独启用或禁用每个过滤器。请参阅 [过滤器编辑器](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **本地覆盖面板：** 此面板显示配置文件中存在的指标、维度和过滤器，这些指标、维度和过滤器已在您的个人配置文件副本中进行修改。 这有助于提示您，在您的客户端和其他用户的客户端中显示数据的方式可能有所不同。When you save changes in a metric, dimension, or filter to the server, the override is removed from the [!DNL Local Overrides panel]. If you click an override and then click **[!UICONTROL Revert to Server]**, the local override is removed and the item reverts to the shared version.
   * **量度图例：** 添加量度图例。 [!DNL Metric legends] 允许您查看与配置文件相关的基准指标和与数据集相关的统计信息(或与当前选择相关的基准指标（如果已做出选择）)。 请参阅 [度量图例](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b)。
   * **颜色图例：** 添加颜色图例。 You can color-code visualizations by metrics, such as Conversion and Retention, and use them in almost every [!DNL Workspace]. 将业务量度与颜色链接在一起更便于发现异常情况、例外和趋势。请参阅[颜色图例](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)。
   * **文本注释：** 添加备注面板。 [!DNL Text annotations] 是可在其中输入任意文本以向其中添加描述性信息或注释的窗口 [!DNL Workspace]。 See [Working with Text Annotations](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **表：** 添加表。 表格可以跨一个或多个数据维度显示一个或多个量度。请参阅 [表格](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **打开：** 打开保存的文件。

## 打开侧栏面板 {#section-cbc8e57491854274a577d47a48c306b8}

可以从保存的位置或从剪贴板中打开侧栏可视化文件。

1. 在提要栏中，单击 **[!UICONTROL Add]** > **[!UICONTROL Open]**。
1. Click **[!UICONTROL File]** to locate the [!DNL .vw] file of the panel you want to add, or click **[!UICONTROL Last Closed Window]**, which pulls the visualization from the clipboard.

   Additionally, you can click **[!UICONTROL From Clipboard]** to paste a visualization that has been copied to the clipboard. 请参阅[复制侧栏面板](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1)。

## 复制侧栏面板 {#section-720ae057632a4b8dbb94412e06a370b1}

1. Right-click the panel’s top border, then click **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. 要粘贴面板，请单击 **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**。

## 保存侧栏面板 {#section-fb19936b12704fb0a4c592abb579db1d}

On an sidebar panel, right click in the title bar and click **[!UICONTROL Save]**.

同样，可以打开保存的侧栏可视化。Data Workbench saves the visualization as a [!DNL .vw] file at the location you specify.

## Revert to the Default Sidebar {#section-4d14b8771ad747bba799876267f24831}

在提要栏中，单击 **[!UICONTROL Options]** > **[!UICONTROL Revert]**。

When you close Data Workbench, the system saves the current sidebar configuration in the [!DNL sidebar.vw] file in the user profile. When you open Data Workbench, the system loads the [!DNL sidebar.vw] file from the user profile, rather than a parent profile.

可以还原到默认或以前保存的侧栏，该操作会从用户配置文件中删除侧栏并从父侧栏中重新加载侧栏。Administrators can replace the default (parent) sidebar with a local sidebar by uploading it from the [!DNL Profile Manager].

## Customize the More Status Panel File {#section-8d502f3b59cc4331966edec05e896ce1}

系统管理员可以在中构建公式 [!DNL More Status Panel.vw]。 这会在度量值和维值周围放置上下文单词，并在提要栏中显示 [!DNL More Status panel] 结果。

To display the [!DNL More Status panel] in the sidebar, click the arrows shown in the following example.

![](assets/more_status_panel_arrows.png)

以下过程显示一个简单示例，说明如何创建一个告诉您数据集中天数的自定义状态：

1. 在中， [!DNL Profile Manager]单 **击[!UICONTROL Sidebar\]**。

1. In the [!DNL Base_5_3*] column, make a local copy of the [!DNL More Status Panel.vw] file.

   To do so, right-click the file check mark and click **[!UICONTROL Make Local]**.

1. 在记 [!DNL More Status Panel.vw] 事本中或 [!DNL .vw] 在记事 [!DNL Editor] 本中打开文件。

   ![](assets/more_status_panel_file.png)

1. 填写 [!DNL Context] 和 [!DNL Items] 字段 [!DNL Editor]。 See [Query Language Syntax](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) for guidelines about syntax.

1. 保存文件。

   上例中的值产生如下所示的状态公式：

   ![](assets/more_status_panel.png)

