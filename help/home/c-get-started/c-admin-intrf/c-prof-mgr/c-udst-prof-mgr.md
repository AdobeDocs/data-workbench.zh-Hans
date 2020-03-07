---
description: 实施中包含的文件夹和文件名称都显示在“配置文件管理器”的左侧。
solution: Analytics
title: 配置文件管理器
topic: Data workbench
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置文件管理器{#profile-manager}

实施中包含的文件夹和文件名称都显示在“配置文件管理器”的左侧。

The profiles that make up your application are displayed as the individual columns in the [!DNL Profile Manager]. 这些配置文件包括多个继承配置文件和一个工作配置文件。

>[!NOTE]
>
>您的工作配置文件（数据集配置文件或特定于角色的配置文件）是打开Data Workbench时加载的配置文件。

复选标记（及其颜色）指示每个文件所在的Data Workbench Server和Data Workbench计算机上的配置文件文件夹，文件是否存在多个副本，以及这些副本是否具有相同的修改日期和时间。 在配置文件下载过程中，这些文件在Data Workbench Server和Data Workbench计算机之间进行同步。

Following is a sample [!DNL Profile Manager] for a HBX implementation:

![](assets/client-prof.png)

从菜 [!DNL Profile Manager] 单中，您可以打开任何其他管理器(例如，或 [!DNL Dimensions Manager][!DNL Reports Manager])，这些管理器仅显示其特定部分 [!DNL Profile Manager]。 您还可以创建新的配置文件管理器。请参阅 [创建新的配置文件管理器](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

特定列中某文件名旁边的复选标记指示具有该名称的文件位于以该列命名的文件夹中（配置文件）。As you move to the right in the [!DNL Profile Manager], the files take precedence over those to the left, that is, each inherited profile builds on the profiles to its left in the [!DNL Profile Manager]. For example, if you have a file of the same name and in the same location in the [!DNL Base] profile (column) and in the [!DNL User] profile (column), the file in the [!DNL User] profile is used instead of the file in the [!DNL Base] profile.

## 搜索配置文件 {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

With Data Workbench 5.5, a search field has been added to find required profiles in the [!DNL Profile Manager].

![](assets/client-prof2.png)

The following types of columns appear in the [!DNL Profile Manager]:

* *继承配置文件名称*&#x200B;列，包含每个配置文件文件夹中存在的文件的复选标记。继承配置文件包括由 Adobe 提供的内部配置文件，以及您创建并维护的任何特定于公司或角色的配置文件。在以上示例中，内部配置文件包括“基本”、“流量”、“值”、“营销”等。The internal [!DNL Base] profile, which contains the basic building blocks and configuration information needed to run your Adobe application, is provided with every implementation. 其他内部配置文件包含与特定类型的信息（例如 Web 流量或营销）相关的元素（工作区、量度、派生维度等）。Adobe 仅提供适合您所分析的数据类型以及适合贵行业的配置文件。

   >[!NOTE]
   >
   >默认情况下，内部配置文件（由Adobe提供的配置文件）无法更改。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。If you are building a new application and need to change an internal profile, you must change the Modify Internal Profiles parameter in the [!DNL Insight.cfg] file. See [Insight Configuration Parameters](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) for more information. 在执行这一操作之前，请联系 Adobe 咨询服务部门。

* *工作配置文件名称*&#x200B;列（始终为倒数第二列），包含当前工作配置文件的文件夹中存在的文件的复选标记。在以上示例中，工作配置文件是“数据集”。您的工作配置文件既可以是数据集配置文件，也可以是特定于角色的配置文件。该文件夹中的文件优先于所有继承配置文件文件夹中具有相同名称的任意文件。
* The [!DNL User] column, which is always the last column, contains check marks for files and folders that reside as local files in the User\*profile name* folder. “用户”文件夹的目录结构模仿工作配置文件的目录结构，每个“用户\*配置文件名称*”文件夹都包含该特定配置文件的工作区、度量、维度和配置文件的本地副本。 这些本地副本优先于所有继承或工作配置文件文件夹中具有相同名称的任意文件。The files in the [!DNL User] column were either created and saved to only the User\*profile name* folder, or they reside in an internal or working profile as well as in the User\*profile name* folder. 每一个文件夹中的文件可能相同、也可能不同，可能具有相同的修改日期和时间，也可能没有。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * To avoid changing your dataset only locally, the Data Workbench server ignores the local copies of the [!DNL profile.cfg] file and any files in the Dataset or Export folders in the User\*profile name* folder. Ignored files are identified by a red background in the [!DNL User] column and an “Ignored in User directory” warning in the context menu. 要实现在这些文件的本地副本中所做的更改，必须将这些更改保存到工作配置文件中，以便它们可以与Data Workbench Server同步。 有关将文件保存到工作配置文件的步骤，请参阅将文 [件发布到工作配置文件](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)。
      >    
      >    
   * 如果列中显示连字符 (-) 而不是复选标记，则这标识空（零字节）文件。Data Workbench将零字节文件视为不存在，这样您就可以使用它们将配置文件中包含的文件隐藏到左侧。 See [Hiding Files Using Empty (Zero-byte) Files](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## 确定文件版本 {#section-225d732246b94cbe87acdfa9c881d6af}

As mentioned in the previous section, the check marks in the [!DNL Profile Manager] are color-coded so that you can easily identify where a file resides and whether the multiple copies of a file were modified at different times.

如果某文件或折叠目录与左侧的文件或目录完全相同，则其复选标记的颜色与该列中文件或目录的颜色相同。If it is different from any file or directory to its left, or the file or directory exists only in the [!DNL User] column, the check mark is white.

![](assets/vis_ProfMgr_LocalFiles.png)

The [!DNL Profile Manager] shown in the example above indicates the following:

* A white check mark for the [!DNL A New Metric.metric] file appears only in the [!DNL User] column, which indicates that you have only a local copy of that file—it has not been published (or uploaded) to the Data Workbench server for other Data Workbench users to access.

* Check marks for the [!DNL Average Score.metric] file name appear in the Movies and [!DNL User] columns. The check mark in the [!DNL User] column is the same color as the check mark in the Movies column, which indicates that the local copy of the file has the same Modified date and time as the file in the Movies folder.

* Check marks for the [!DNL Average Score Error.metric] file name appear in the Movies and [!DNL User] columns. The check mark in the [!DNL User] column is white, which indicates that the local copy of the file has a different Modified date or time than the file in the Movies folder.

