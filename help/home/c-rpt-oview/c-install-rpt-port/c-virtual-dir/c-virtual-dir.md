---
description: 要配置Report Portal，必须将其应用程序文件映射到虚拟目录。
title: 将报表门户页面映射到虚拟目录
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 18%

---

# 将报表门户页面映射到虚拟目录{#map-the-report-portal-pages-to-virtual-directories}

要配置Report Portal，必须将其应用程序文件映射到虚拟目录。

虚拟目录定义浏览器客户端用于在IIS应用程序服务器上查找物理资源的地址。 要访问[!DNL Report Portal]，客户端将其浏览器指向您分配给门户的虚拟目录。

分配给[!DNL Report Portal]的虚拟目录的名称必须与上一部分步骤3中用于VSVirtualPortalName文件夹的名称相匹配。 例如，如果要使用“门户”作为[!DNL Report Portal]的名称，则必须将门户的文件映射到名为“门户”的虚拟目录。 以下示例显示客户端用来访问名为myWebServer的服务器上分配给虚拟目录[!DNL VisualReportPortal]的[!DNL Report Portal]的URI:

[!DNL http://myWebServer/VisualReportPortal]

以下过程描述如何将[!DNL Report Portal]映射到IIS 5.0、6.0和7.0或更高版本上的虚拟目录。

请按照您所使用的IIS版本的一组过程操作：

* [将报表门户映射到虚拟目录 (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [将报表门户映射到虚拟目录 (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [编辑会话配置文件](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
