---
description: 必须以特定方式配置报表集，才能生成通过报表门户正确显示的报表。
solution: Analytics
title: 自定义Report Portal用户界面
topic: Data workbench
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 自定义Report Portal用户界面{#customize-the-report-portal-user-interface}

必须以特定方式配置报表集，才能生成通过报表门户正确显示的报表。

用户界面设 [!DNL Report Portal] 计为显示输出目录中显示的、在文件中列出的每个报告集文件夹的选项卡，以及必须添加到要显示的文件的内置 [!DNL profiles.xml][!DNL Admin][!DNL TopNavigation.xml] 选项卡。 有关显示内置选项卡的详细信息，请 [!DNL Admin] 参阅将输 [出文件夹链接到用户……中的选项卡。](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [确保您的报表集与报表门户兼容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [将输出文件夹链接到用户……中的选项卡](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## 确保您的报表集与报表门户兼容 {#section-2b141e5d198a4bbea455699126c24706}

报告集为定义计划作业 [!DNL Report]。 它包含两项：

* 一个文件夹，它定义要作为报告生成的工 [!DNL Report] 作区集合。
* 配置文件( [!DNL Report.cfg])。

除其他事项外，文 [!DNL Report.cfg] 件还会告 [!DNL Report] 诉何时生成报告以及保存输出文件的位置。 报表集位于Data Workbench Server上的“报表”文件夹中。 配置文件可显示任意数量的报表集。

要确保与之兼容， [!DNL Report Portal]您的报表集必须满足以下要求：

* 报告集的输出目录必须包含已配置的文 [!DNL profiles.xml] 件。
* 每个报表集都必须包含一个名为“*ReportSetName* Summary”的顶级报表，其中 *ReportSetName* 与报表集的名称匹配。 例如，下面显示了 [!DNL Profile Manager] 两个报表集，“主页”和“流量”。请注意，每个报告集都定义一个摘要报告( [!DNL Home Summary.vw] 分别 [!DNL Traffic Summary.vw]定义和)。

![](assets/rptPort_scrn_RptSets.png)

在 [!DNL Report Portal]中，摘要报告显示在报告集的选项卡上。 摘要报告可包含您选择的任何工作区、窗口或可视化。

* 摘要报告必须是报告集顶级文件夹中的唯一报告。 所有其他报告都必须放在子文件夹中。 如果将其他报告放在顶级文件夹中，则无法通过门户查看它们。

## 将输出文件夹链接到用户界面中的选项卡 {#section-3f6bc47d37ed448e871f4f685f46acee}

要指定要显示的选项卡， [!DNL Report Portal] 必须为每个配置文件配 [!DNL TopNavigation.xml] 置一个文件。 此文件决定哪些报表集在特定配置文件的用户界面中显示为选项卡，以及这些选项卡的顺序。 文 [!DNL TopNavigation.xml] 件位于\*PortalName*\PortalFiles\Core\TopNav\*profileName*文件夹中。

**编辑TopNavigation.xml文件**

1. 在运行IIS的计算机上，在文本编辑 [!DNL TopNavigation.xml] 器（如记事本）中打开文件。
1. 编辑元素 `<TopNav>` 列表，以便定义要显示其输出的报表集的名称 [!DNL Report Portal] 和顺序，如下例所示：

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <TOPNAV_ELEMENTS>
   <TOPNAV>
       <NAME>Monthly Web</NAME>
     </TOPNAV>
     <TOPNAV>
       <NAME>Weekly Web</NAME>
     </TOPNAV>
   <TOPNAV> 
         <NAME>Admin</NAME> 
     </TOPNAV>
   </TOPNAV_ELEMENTS>
   ```

   >[!NOTE]
   >
   >该选 [!DNL Admin] 项卡是一个内置选项卡，它提供其他功能。 如果未将其包含在文件中， [!DNL TopNavigation.xml] 则不显示此选项卡，且其功能不可用。

1. 在\*PortalName*\PortalFiles\Core\TopNav\ folder文件夹中，为您的下一个配置文件创建一个文件夹。
1. 从第一个 [!DNL TopNavigation.xml] 配置文件文件夹复制文件并将其粘贴到新文件夹中。
1. Edit the [!DNL TopNavigation.xml] as necessary, then save the file.
1. 对门户中可用的所有其他配置文件重复步骤3-5。

