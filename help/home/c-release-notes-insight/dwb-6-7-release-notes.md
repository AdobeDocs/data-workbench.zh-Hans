---
description: Data Workbench 6.7中的新增功能、修复和已知问题。
title: Data Workbench 6.7 发行说明
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.7 发行说明{#data-workbench-release-notes}

Data Workbench 6.7中的新增功能、修复和已知问题。

## Data Workbench 6.7 发行说明 {#topic-7655534554ac4a4b816af1bd73b06aad}

Data Workbench 6.7中的新增功能、修复和已知问题。

## 6.7版的新增功能 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Data Workbench 工作站的新身份验证模型（IMS 集成）**

Data Workbench 工作站当前支持通过用户名和密码进行用户身份验证。通过这个新方法，管理员可以创建和管理他们自己的用户帐户，这样就不必联系客户关怀。

有关更多信息，请参阅[用户自助设置](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html)。

**平面文件查找**

Data Workbench 工作站当前支持通过用户名和密码进行用户身份验证。通过这个新方法，管理员可以创建和管理他们自己的用户帐户，这样就不必联系客户关怀。

平面文件查找以前将整个文件加载到内存缓冲区中，这会增加内存使用率并给其他子系统带来性能问题。此类文件当前可在 Windows 中进行内存映射和缓存，通过将 *中的* Memory Mapped Lookup Files[!DNL MemorySettings.cfg] 设置为 true 可优化内存使用率。

有关更多信息，请参阅[用户自助设置](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html)。

**内存使用**

Large Page usage can now be disabled by setting *Use Large Pages* to false in [!DNL MemorySettings.cfg]. 请参阅[监控内存使用率](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html)以获取更多信息。

**安全加密**

添加了对 ECDHE 和 DHE 的支持

Email support in [!DNL User List.cfg]

Added support for Email attribute in [!DNL User List.cfg]. 有关更多信息，请参阅[组成员的用户管理](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html)。

**帮助菜单**

帮助菜单当前显示“打开证书”目录的快捷键。

**`TargetBulkUpload`导出&#x200B;**

将在导出跟踪文件和 `targetbulkuploadexportname.log.completed` 文件的末尾提供 URL，以跟踪受阻批次的记录。

已提供新文件 [!DNL TargetBulkUpload.cfg]，可用来配置最大超时间隔（以分钟为单位）。该文件位于[!DNL Server\Admin\Export\]中。

## 修复 {#section-160baf6ea04c45a993777ee4260691ed}

* 修复了“营销活动点进率”维度显示夸大值的问题。
* 修复了从报表服务器生成Excel文件的问题。
* RC4密码现在默认处于禁用状态。
* 修复了在将维元素添加到值图例表时导致Data Workbench工作站崩溃的问题。
* 修复了Data Workbench到AAM导出导致超时的问题。
* 修复了在没有足够访问权限的用户将工作区保存到服务器时导致Data Workbench工作站崩溃的问题。
* 修复了日期格式不正确或未 [!DNL report.cfg] 本地化的问题。
* 修复了AVRO源中移动和产品行显示混淆信息的问题。
* 修复了阻止在中排序和文件 `*.1cd` 的 `*.1ad` 问题 [!DNL order.txt]。

* 在运行聚类时，“提交到服务器”选项对于“期望最大化”算法已禁用。
* 修复了可执行文件 `TargetBulkUpload` 停滞和无法完全运行的问题。

## 已知问题 {#section-d76322bdac5043f087ab303dc68b8fff}

* 注销时，文件 [!DNL user cache.db] 会被清除。
* 不支持包含“+”或“%”字符的IMS用户电子邮件地址。
* 在连接状态出错期间，用户无法注销。 作为解决方法，请在脱机模式下注销。
* IMS登录窗口在某些分辨率和高DPI的硬件上无法正常显示。 作为解决方法，请右键单击并 [!DNL Insight.exe] 导航到 **[!UICONTROL Properties]** > **[!UICONTROL Compatability]**，然后选中该框 **[!UICONTROL Override high DPI scaling behavior]**。

## 升级要求 {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. 在作 [!DNL trust_ca_cert.pem] 为构建包一部分的Insight Server上更新。
1. 从https://aap.adobe.com下载新证书，以更新服务器和报告服务器的证 [书](https://aap.adobe.com)。
1. 要自动更新工作站和报告服务器，请通过从许 [!DNL trust_ca_cert.pem] 可证服务器下载工作站和报告服务器来手动更新它们。
1. 传感器的自动更新功能需要5.0版才能与Insight Server版本6.70通信。此外，传感器必须 [!DNL trust_ca_cert.pem] 通过从许可证服务器下载来手动更新。

## 系统更新 {#section-c1b4949ea734440aa62658ac313261db}

新文件包括：

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

已更新的文件包括：

1. [!DNL trust_ca_cert.pem] 所有组件。
1. [!DNL Access Control.cfg] 支持IMS配置。
1. [!DNL Base\Context\meta.cfg] 在Adobe Cloud中支持“开始日期”和“结束日期”格式 [!DNL Report.cfg]

1. 支持IMS [!DNL Insight.cfg] 身份验证代理的附加功能：

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

请参阅 Data Workbench 5.3 至 5.52 的[已存档发行说明](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html)。
