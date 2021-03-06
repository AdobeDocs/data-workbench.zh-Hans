---
description: 实施中包含的文件夹和文件名称都显示在“配置文件管理器”的左侧。
title: 配置文件管理器
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 33%

---


# 配置文件管理器{#profile-manager}

实施中包含的文件夹和文件名称都显示在“配置文件管理器”的左侧。

构成您的应用程序的配置文件在[!DNL Profile Manager]中显示为单个列。 这些配置文件包括多个继承配置文件和一个工作配置文件。

>[!NOTE]
>
>工作配置文件（数据集配置文件或特定于角色的配置文件）是您在打开Data Workbench时加载的配置文件。

复选标记（及其颜色）指示每个文件所在的Data Workbench服务器和Data Workbench计算机上的配置文件文件夹，文件是否存在多个副本，以及这些副本是否具有相同的修改日期和时间。 这些文件在配置文件下载期间在Data Workbench服务器和Data Workbench计算机之间同步。

以下是HBX实施的示例[!DNL Profile Manager]:

![](assets/client-prof.png)

从[!DNL Profile Manager]菜单中，可以打开任何其他管理器（例如[!DNL Dimensions Manager]或[!DNL Reports Manager]），这些管理器仅显示[!DNL Profile Manager]的特定部分。 您还可以创建新的配置文件管理器。请参阅 [创建新的配置文件管理器](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

特定列中某文件名旁边的复选标记指示具有该名称的文件位于以该列命名的文件夹中（配置文件）。在[!DNL Profile Manager]中向右移动时，文件优先于左侧的文件，即每个继承的配置文件都基于[!DNL Profile Manager]左侧的配置文件构建。 例如，如果在[!DNL Base]配置文件（列）和[!DNL User]配置文件（列）中有一个名称相同且位置相同的文件，则会使用[!DNL User]配置文件中的文件，而不是[!DNL Base]配置文件中的文件。

## 搜索用户档案{#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

在Data Workbench5.5中，添加了搜索字段，以在[!DNL Profile Manager]中查找所需的用户档案。

![](assets/client-prof2.png)

[!DNL Profile Manager]中显示以下类型的列：

* *继承配置文件名称*&#x200B;列，包含每个配置文件文件夹中存在的文件的复选标记。继承配置文件包括由 Adobe 提供的内部配置文件，以及您创建并维护的任何特定于公司或角色的配置文件。在以上示例中，内部配置文件包括“基本”、“流量”、“值”、“营销”等。内部[!DNL Base]配置文件(包含运行Adobe应用程序所需的基本构建块和配置信息)随每个实施一起提供。 其他内部配置文件包含与特定类型的信息（例如 Web 流量或营销）相关的元素（工作区、量度、派生维度等）。Adobe 仅提供适合您所分析的数据类型以及适合贵行业的配置文件。

   >[!NOTE]
   >
   >默认情况下，内部用户档案(由Adobe提供的用户档案)无法更改。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。如果要构建新应用程序并且需要更改内部配置文件，则必须更改[!DNL Insight.cfg]文件中的Modify Internal Profiles（修改内部配置文件）参数。 有关更多信息，请参阅[Insight配置参数](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。 在执行这一操作之前，请联系 Adobe 咨询服务部门。

* *工作配置文件名称*&#x200B;列（始终为倒数第二列），包含当前工作配置文件的文件夹中存在的文件的复选标记。在以上示例中，工作配置文件是“数据集”。您的工作配置文件既可以是数据集配置文件，也可以是特定于角色的配置文件。该文件夹中的文件优先于所有继承配置文件文件夹中具有相同名称的任意文件。
* [!DNL User]列（始终是最后一列）在User\*profile name*文件夹中包含作为本地文件存在的文件和文件夹的复选标记。 User文件夹的目录结构与工作配置文件的目录结构相似，每个User\*profile name*文件夹都包含该特定配置文件的工作区、量度、维度和配置文件的本地副本。 这些本地副本优先于所有继承或工作配置文件文件夹中具有相同名称的任意文件。[!DNL User]列中的文件创建并仅保存到User\*配置文件名称*文件夹，或者它们位于内部或工作配置文件以及User\*配置文件名称*文件夹中。 每一个文件夹中的文件可能相同、也可能不同，可能具有相同的修改日期和时间，也可能没有。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 为避免仅在本地更改您的Data Workbench集，服务器会忽略[!DNL profile.cfg]文件的本地副本以及User\*profile name*文件夹的Dataset或Export文件夹中的任何文件。 已忽略的文件在[!DNL User]列中由红色背景标识，在上下文菜单中由“在用户目录中已忽略”警告标识。 要实施在这些文件的本地副本中所做的更改，必须将其保存到工作配置文件中，以便它们能够与Data Workbench服务器同步。 有关将文件保存到工作配置文件的步骤，请参阅[将文件发布到工作配置文件](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。
      >    
      >    
   * 如果列中显示连字符 (-) 而不是复选标记，则这标识空（零字节）文件。Data Workbench将零字节文件视为不存在，这样您就可以使用它们将配置文件中包含的文件隐藏到左侧。 请参阅[使用空（零字节）文件隐藏文件](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491)。


## 确定文件版本{#section-225d732246b94cbe87acdfa9c881d6af}

如上节所述，[!DNL Profile Manager]中的复选标记采用颜色编码，以便您能够轻松识别文件所在的位置以及文件的多个副本是否在不同时间被修改。

如果某文件或折叠目录与左侧的文件或目录完全相同，则其复选标记的颜色与该列中文件或目录的颜色相同。如果它与左侧的任何文件或目录不同，或者该文件或目录仅存在于[!DNL User]列中，则复选标记为白色。

![](assets/vis_ProfMgr_LocalFiles.png)

上例中显示的[!DNL Profile Manager]表示：

* [!DNL A New Metric.metric]文件的白色复选标记仅显示在[!DNL User]列中，表示您只拥有该文件的本地副本，该副本尚未发布（或上传）到Data Workbench服务器，以供其他Data Workbench用户访问。

* [!DNL Average Score.metric]文件名的复选标记显示在Movies和[!DNL User]列中。 [!DNL User]列中的复选标记与“影片”列中的复选标记颜色相同，表示文件的本地副本与Movies文件夹中的文件具有相同的修改日期和时间。

* [!DNL Average Score Error.metric]文件名的复选标记显示在Movies和[!DNL User]列中。 [!DNL User]列中的复选标记为白色，表示文件的本地副本的修改日期或时间与Movies文件夹中的文件不同。

