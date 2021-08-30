---
description: Data Workbench6.7中的新增功能、修复和已知问题。
title: Data Workbench 6.7 发行说明
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
exl-id: e5ec3224-66d1-47a6-9bf3-8be9f6568b8d
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 36%

---

# Data Workbench 6.7 发行说明{#data-workbench-release-notes}

Data Workbench6.7中的新增功能、修复和已知问题。

## Data Workbench 6.7 发行说明 {#topic-7655534554ac4a4b816af1bd73b06aad}

Data Workbench6.7中的新增功能、修复和已知问题。

## 版本6.7中的新增功能 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Data Workbench 工作站的新身份验证模型（IMS 集成）**

Data Workbench 工作站当前支持通过用户名和密码进行用户身份验证。通过这个新方法，管理员可以创建和管理他们自己的用户帐户，这样就不必联系客户关怀。

有关更多信息，请参阅[用户自助设置](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html)。

**平面文件查找**

Data Workbench 工作站当前支持通过用户名和密码进行用户身份验证。通过这个新方法，管理员可以创建和管理他们自己的用户帐户，这样就不必联系客户关怀。

平面文件查找以前将整个文件加载到内存缓冲区中，这会增加内存使用率并给其他子系统带来性能问题。此类文件当前可在 Windows 中进行内存映射和缓存，通过将 ** 中的 Memory Mapped Lookup Files 设置为 [!DNL MemorySettings.cfg]true 可优化内存使用率。

有关更多信息，请参阅[用户自助设置](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html)。

**内存使用率**

现在，可以通过将[!DNL MemorySettings.cfg]中的&#x200B;*Use Large Pages*&#x200B;设置为false，来禁用“大页面使用情况”。 请参阅[监控内存使用率](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html)以获取更多信息。

**安全加密**

添加了对 ECDHE 和 DHE 的支持

[!DNL User List.cfg]中的电子邮件支持

在[!DNL User List.cfg]中添加了对“电子邮件”属性的支持。 有关更多信息，请参阅[组成员的用户管理](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html?lang=en)。

**帮助菜单**

帮助菜单当前显示“打开证书”目录的快捷键。

**`TargetBulkUpload`导出**

将在导出跟踪文件和 `targetbulkuploadexportname.log.completed` 文件的末尾提供 URL，以跟踪受阻批次的记录。

已提供新文件 [!DNL TargetBulkUpload.cfg]，可用来配置最大超时间隔（以分钟为单位）。在 [!DNL Server\Admin\Export\]中找到该文件。

## 修复 {#section-160baf6ea04c45a993777ee4260691ed}

* 修复了促销活动点进维度显示夸大值的问题。
* 修复了从报表服务器生成excel文件时出现的问题。
* RC4密码现在默认处于禁用状态。
* 修复了在向值图例表中添加维度元素时导致Data Workbench工作站崩溃的问题。
* 修复了对AAM的Data Workbench导出导致超时的问题。
* 修复了当没有足够访问权限的用户将工作区保存到服务器时导致Data Workbench工作站崩溃的问题。
* 修复了[!DNL report.cfg]中的日期格式不正确或未本地化的问题。
* 修复了AVRO信息源中的移动设备行和产品行显示混淆信息的问题。
* 修复了导致[!DNL order.txt]和`*.1ad`文件在`*.1cd`中无法排序的问题。

* 运行聚类时，对于期望最大化算法，“提交到服务器”选项已被禁用。
* 修复了`TargetBulkUpload`可执行文件停滞且无法完全运行的问题。

## 已知问题 {#section-d76322bdac5043f087ab303dc68b8fff}

* 注销时，将清理[!DNL user cache.db]文件。
* 不支持包含“+”或“%”字符的IMS用户电子邮件地址。
* 在连接状态出现错误时，用户无法注销。 作为解决方法，请在脱机模式下注销。
* 某些具有高分辨率和高DPI的硬件上无法正确呈现IMS登录窗口。 作为解决方法，请右键单击[!DNL Insight.exe]并导航到&#x200B;**[!UICONTROL Properties]** > **[!UICONTROL Compatability]**，然后选中&#x200B;**[!UICONTROL Override high DPI scaling behavior]**&#x200B;框。

## 升级要求 {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. 在Insight Server上更新[!DNL trust_ca_cert.pem]，该服务器是构建包的一部分。
1. 通过从[https://aap.adobe.com](https://aap.adobe.com)下载新证书来更新服务器和报表服务器的证书。
1. 要自动更新工作站和报表服务器，请通过从许可证服务器下载工作站和报表服务器来手动更新[!DNL trust_ca_cert.pem]。
1. 传感器的自动更新功能需要5.0版才能与Insight Server版本6.70通信。此外，必须从许可证服务器下载传感器的[!DNL trust_ca_cert.pem]以手动更新。

## 系统更新 {#section-c1b4949ea734440aa62658ac313261db}

新文件包括：

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

已更新的文件包括：

1. [!DNL trust_ca_cert.pem] ，以访问所有组件。
1. [!DNL Access Control.cfg] 以支持IMS配置。
1. [!DNL Base\Context\meta.cfg] 用于在  [!DNL Report.cfg]

1. [!DNL Insight.cfg]的新增内容，用于支持IMS身份验证的代理：

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

请参阅 Data Workbench 5.3 至 5.52 的[已存档发行说明](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html)。
