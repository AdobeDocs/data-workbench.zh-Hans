---
description: 页面叠加仅在 Site 应用程序中配置，但它们可以为其他应用程序进行配置。
title: 配置页面叠加
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
exl-id: 4e0dfce8-def2-49f3-93e8-41d82922fb88
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 62%

---

# 配置页面叠加{#configure-a-page-overlay}

{{eol}}

页面叠加仅在 Site 应用程序中配置，但它们可以为其他应用程序进行配置。

有关为其他应用程序配置页面叠加的信息，请联系 Adobe 咨询服务部门。

页面叠加可视化是一种用于 HTML 链接分析的工具。当您为特定页面请求叠加时，Data Workbench会像在Web浏览器中一样拍摄实际页面的快照，并根据您定义的正则表达式列表解析表示链接的HTML代码。 对于选定页面上的每个链接，软件将尝试通过搜寻该列表来查找正则表达式模式匹配，直至找到第一个匹配项为止。如果存在匹配项，则链接会在页面叠加中突出显示。

仅当您向包含页面叠加的工作区添加了颜色图例之后，页面叠加才会显示数据。

>[!NOTE]
>
>配置页面叠加需要仔细配置，如果链接未正确映射到数据，则可能会产生误导性结果。 为特定网站配置页面叠加所涉及的工作，取决于链接在网站网页的 HTML 代码中的呈现方式。

页面叠加其本身对用户有着暗示“人们该单击此处”的心理模式作用。如果支持可视化的数据不匹配这种模式，则产生混淆的可能性是很高的。

在 [!DNL Site] 中，链接通常表示“下一个 URI”或“下一个链接”维度中的元素，但您可以将链接映射到任何对分析有益的维度。有关为其他维度配置页面叠加的信息，请联系 Adobe 咨询服务部门。

>[!NOTE]
>
>不建议将页面维度用于页面叠加。 用户可以重命名“页面”维度的元素，从而更改页面叠加功能所依赖的链接语法。

若要为 [!DNL Site] 配置页面叠加，您必须编辑两个文件：

* **[!DNL Page Overlay.vw]:** 此文件是用于创建页面叠加可视化的模板文件。 在要为其配置页面叠加的配置文件中必须至少存在一个模板文件。
* **[!DNL Page Overlay Link Templates.cfg]:** 当页面叠加可视化加载页面时，它会自动识别页面中的链接及其目标。 若要将这些链接关联到数据中的元素，必须在该文件中定义一组正则表达式。

   您可以定义多个正则表达式来与维度的元素匹配。定义表达式的顺序很重要。当您为特定页面请求叠加时，Data Workbench会像在Web浏览器中一样拍摄实际页面的快照，并根据您定义的正则表达式列表解析表示链接的HTML代码。 对于选定页面上的每个链接，软件将尝试通过搜寻该列表来查找正则表达式模式匹配，直至找到第一个匹配项为止。与维度元素匹配的第一个表达式便是所使用的表达式。因此，最好首先列出具有最具体匹配模式的正则表达式，其后再列出是较具体的表达式。如果存在匹配项，则链接会在页面叠加可视化中突出显示。

**为 Site** 配置页面叠加

1. I

   n [!DNL Profile Manager]，导航到 **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >“Dimension元素”目录包含右键单击某个维度元素时显示的上下文菜单项。 例如，打开一个 URI 表格，然后选择一个 URI 元素。右键单击该 URI，即会显示“页面叠加”。

1. 在URI文件夹中，右键单击 [!DNL Page Overlay.vw] 文件，单击 **[!UICONTROL Make Local]**. 此文件的复选标记将显示在 [!DNL User] 列。
1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 指定域（如果需要，还指定浏览器高度）。

   ```
   window = simpleBorderWindow:
     client = scrollWindow:
       client = PageOverlay:
         URI Template = string: https://%Domain%%Element%
         URI Parameters = map:
           Domain = string: domain name
           Element = ref: Element/Name
         Dim = ref: wdata/model/dim/URI
         Dim Element = ref: Element/Name
         Level = ref: wdata/model/dim/Page View
         Group = ref: wdata/model/dim/Session
         Browser Height = int: browser height
     pos = v3d: (518, 202, 0)
     size = v3d: (810, 610, 0)
     titleBar = editor:
       size = v3d: (61, 19, 0)
       text = string:
   ```

1. 保存文件。
1. 要使此更改对工作配置文件的所有用户可用，请在 [!DNL Profile Manager]，右键单击 [!DNL .vw] 文件 [!DNL User] 列，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >您可以为其他站点或子域创建其他模板文件。 您创建的每个模板都会显示在 [!DNL Page Overlay menu].

1. 在的 [!DNL Profile Manager]，右键单击 [!DNL Page Overlay Link Templates.cfg] 文件，单击 **[!UICONTROL Make Local]**.

   此文件的复选标记将显示在 [!DNL User] 列。

1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. 右键单击 **[!UICONTROL Link Templates]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
1. 根据需要编辑 LinkRegex 矢量的参数：

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 对于该参数... </th>
   <th colname="col2" class="entry"> 提供此信息... </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>维度 </p> </td>
   <td colname="col2"> <p>链接所表示的维度（通常为“下一个 URI”维度）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>表达式 </p> </td>
   <td colname="col2"> <p>正则表达式，用于选择 HTML 链接的相关部分以从维度中查找下一个元素。正则表达式必须完全匹配，并且使用括号对所需的输出模式进行分组。有关正则表达式的详细信息，请参阅《数据集配置指南》<i></i>。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Output Pattern（输出模式） </p> </td>
   <td colname="col2"> <p>正则表达式的输出模式，用于提取 Dimension（维度）参数的结果元素。 </p> </td>
  </tr>
 </tbody>
</table>

以下示例文件显示了三个正则表达式：

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. 要保存文件，请右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.
1. 若要使此更改对工作配置文件的所有用户可用，请右键单击 [!DNL Page Overlay Link Templates.cfg] 在 [!DNL User] 列，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
