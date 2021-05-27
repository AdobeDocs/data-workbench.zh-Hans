---
description: 必须以特定方式配置报表集，才能生成通过报表门户正确显示的报表。
title: 自定义报表门户的用户界面
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# 自定义报表门户的用户界面{#customize-the-report-portal-user-interface}

必须以特定方式配置报表集，才能生成通过报表门户正确显示的报表。

[!DNL Report Portal]的用户界面设计为针对输出目录中显示并列在[!DNL profiles.xml]文件中的每个报表集文件夹以及内置的[!DNL Admin]选项卡显示一个选项卡，必须将其添加到要显示的[!DNL TopNavigation.xml]文件中。 有关显示内置[!DNL Admin]选项卡的更多信息，请参阅[将输出文件夹关联到用户……中的选项卡。](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)。

![](assets/report_portal_home.png)

* [确保您的报表集与报表门户兼容……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [将输出文件夹链接到用户中的选项卡……](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## 确保报表集与报表门户{#section-2b141e5d198a4bbea455699126c24706}兼容

报表集为[!DNL Report]定义计划作业。 它包含两项：

* 一个文件夹，用于定义希望[!DNL Report]生成为报表的工作区集合。
* 配置文件([!DNL Report.cfg])。

除其他外，[!DNL Report.cfg]文件会告知[!DNL Report]何时生成报告以及保存输出文件的位置。 报表集位于Data Workbench Server上的“报表”文件夹中。 用户档案可显示任意数量的报表集。

要确保与[!DNL Report Portal]兼容，您的报表集必须满足以下要求：

* 报表集的输出目录必须包含已配置的[!DNL profiles.xml]文件。
* 每个报表集必须包含一个名为“*ReportSetName*&#x200B;摘要”的顶级报表，其中&#x200B;*ReportSetName*&#x200B;与报表集的名称匹配。 例如，以下[!DNL Profile Manager]显示两个报表集：“Home”和“Traffic”。 请注意，每个报表集都定义一个摘要报表（分别为[!DNL Home Summary.vw]和[!DNL Traffic Summary.vw]）。

![](assets/rptPort_scrn_RptSets.png)

在[!DNL Report Portal]中，摘要报告显示在报表集的选项卡上。 摘要报表可以包含您选择的任何工作区、窗口或可视化。

* 摘要报表必须是报表集顶级文件夹中的唯一报表。 所有其他报表都必须放在子文件夹中。 如果将其他报表放置在顶级文件夹中，则无法通过门户查看这些报表。

## 将输出文件夹链接到用户界面{#section-3f6bc47d37ed448e871f4f685f46acee}中的选项卡

要指定要显示[!DNL Report Portal]的选项卡，必须为每个配置文件配置一个[!DNL TopNavigation.xml]文件。 此文件决定在特定用户档案的用户界面中哪些报表集显示为选项卡，以及这些选项卡的顺序。 [!DNL TopNavigation.xml]文件位于\*PortalName*\PortalFiles\Core\TopNav\*profileName*文件夹中。

**编辑TopNavigation.xml文件**

1. 在运行IIS的计算机上，在文本编辑器（如记事本）中打开[!DNL TopNavigation.xml]文件。
1. 编辑`<TopNav>`元素列表，以便定义您希望[!DNL Report Portal]显示其输出的报表集的名称和顺序，如以下示例所示：

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
   >[!DNL Admin]选项卡是一个内置选项卡，可提供额外的功能。 如果未将其包含在[!DNL TopNavigation.xml]文件中，则不会显示此选项卡，且其功能不可用。

1. 在\*PortalName*\PortalFiles\Core\TopNav\ folder中，为您的下一个配置文件创建一个文件夹。
1. 复制第一个配置文件文件夹中的[!DNL TopNavigation.xml]文件，并将其粘贴到新文件夹中。
1. 根据需要编辑[!DNL TopNavigation.xml]，然后保存文件。
1. 对门户中可用的所有其他配置文件重复步骤3-5。
