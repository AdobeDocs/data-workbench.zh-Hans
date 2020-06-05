---
description: Adobe Data Workbench提供多种工具和流程，使您的数据符合一般数据保护规定(GDPR)。
solution: Analytics
title: 面向GDPR的数据工作台支持
topic: Data workbench
translation-type: tm+mt
source-git-commit: 279e71f3da3f0ebc29091e88b87666a22a36a8d6
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---


# 面向GDPR的数据工作台支持

Adobe Data Workbench提供各种工具和流程，使您的数据符合( [!DNL General Data Protection Regulations] GDPR)的要求。

与所有Adobe Analytics解决方案一样，Data Workbench在处理Adobe Analytics的数据馈送时提供分析变量的清理、删除和标签，从而为GDPR提供支持。 为支持GDPR实施，Adobe允许您根据您与Adobe协议中规定的公司权限设置GDPR流程。 请参 [阅Adobe Analytics和GDPR以了解更多信息](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)。

GDPR规定确定负责GDPR实施的不同方的角色和义务(请参 [阅GDPR和您的业务](https://www.adobe.com/cn/privacy/general-data-protection-regulation.html))。

* 您的组织充当数 **据管理者** ，根据您的需求和限制确定个人数据的上下文和保留。 然后，Adobe代表您处理和存储这些数据。
* Adobe充当数据处理 **者** ，根据您与Adobe的协议，提供实施GDPR要求的软件和服务。
* 在将Data Workbench与GDPR服务集成并符合GDPR标准后，访问网站(数 **据主体**)的访客可以行使其“被数据处理者Adobe遗忘的权利”。 要实现遗忘权，您作为访客控制者可以从UI或API将受挑战的数据ID上传到Adobe。 有关详 [细信息](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) ，请参阅Adobe Analytics GDPR工作流文档 [，包括提交](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) 访问和删除请求部分。

>[!NOTE]
>
>对于其他数据源，您的组织将负责清理来自其他日志源（如CRM、POS、IVR和其他原始数据源）的受挑战访客ID。 通过为每个数据源提供完整的替换文件集，可以使用自定义范围的服 _务包为组织提供支持_ ，这些数据源需要持续的服务容器来支持或维护。

## 升级DWB以实施GDPR

Consulting将就适当的服务包为您提供建议，使现有实施符合要求。 请联系您的客户成功经理(CSM)以获取更多信息。

如果需要：

* [升级到最新版Data](https://docs.adobe.com/content/help/zh-Hans/data-workbench/using/release-notes/release-notes.html) Workbench。 为获得最高的安全性，DWB 6.7版本中新增了集成GDPR所需的证书和安全功能。
* 如果使用旧版TSV分析事件日志，请升级到 [Avro数据源](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)。
* 如果将旧版UCP（统一客户流程）与转换结合使用来更新现有日志，请升级到当前流程。 更新后的进程直接生成主查找文件，用于跨源映射访客ID。
* 实现数据流标准化以适应GDPR服务。
* 建立自定义范围的服务包以管理其他日志源，如CRM、POS、IVR和其他原始数据源。
* 确认Analytics合同中的默认数据保留期为25个月或更长。
