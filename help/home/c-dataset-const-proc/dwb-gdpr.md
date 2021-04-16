---
description: AdobeData Workbench提供工具和流程，使您的数据符合一般数据保护规定(GDPR)。
title: Data Workbench 支持 GDPR
exl-id: fdc43567-0c57-4851-9073-e295258a8074
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

---

# Data Workbench 支持 GDPR

AdobeData Workbench提供工具和流程，使您的数据符合[!DNL General Data Protection Regulations](GDPR)的要求。

与所有Adobe Analytics解决方案一样，Data Workbench在处理Adobe Analytics数据馈送时提供分析变量的清理、删除和标签，从而为GDPR提供支持。 为支持GDPR实施，Adobe允许您根据您与Adobe的协议中规定的公司权限设置GDPR流程。 请参阅[Adobe Analytics和GDPR以了解详细信息](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html)。

GDPR规定确定负责GDPR启用的不同方的角色和义务（请参阅[GDPR和您的业务](https://www.adobe.com/privacy/general-data-protection-regulation.html)）。

* 您的组织充当&#x200B;**数据控制者**，根据您的需求和限制确定个人数据的上下文和保留。 Adobe然后代表您处理和存储此数据。
* Adobe充当&#x200B;**数据处理者**，根据您与Adobe的协议提供实施GDPR要求的软件和服务。
* 在将Data Workbench与GDPR服务集成并符合GDPR标准后，访问站点（**数据主体**）的访客可以由Adobe（数据处理者）行使其“被遗忘权”。 要实现被遗忘的权利，您作为访客控制者可以从UI或API将受挑战的AdobeID上传到。 有关详细信息（包括[提交访问和删除请求](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html)部分），请参阅[Adobe Analytics GDPR Workflow](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html)文档。

>[!NOTE]
>
>对于其他访客源，您的组织将负责清除来自其他日志源（如CRM、POS、IVR和其他原始数据源）的受质疑的数据ID。 可通过&#x200B;_为每个数据源_&#x200B;提供一组完整的替换文件来提供对组织的支持，这些文件是当前服务容器需要支持或维护的。

## 升级DWB以实施GDPR

Consulting将就适当的服务包为您提供建议，以便使现有实施符合要求。 请联系您的客户成功经理(CSM)以获取更多信息。

如果需要：

* [升级到最新](https://docs.adobe.com/content/help/zh-Hans/data-workbench/using/release-notes/release-notes.html) 版本的Data Workbench。为获得最高的安全性，DWB 6.7版中新增了集成GDPR所需的证书和安全功能。
* 如果使用旧版TSV分析事件日志，请升级到[Avro数据馈送](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)。
* 如果将旧版UCP（统一客户流程）与转换结合使用来更新现有日志，请升级到当前流程。 更新后的进程会直接生成一个主控的查找文件，用于跨源映射访客ID。
* 实现数据流标准化以适应GDPR服务。
* 建立自定义范围的服务包以管理其他日志源，如CRM、POS、IVR和其他原始数据源。
* 确认Analytics合同中25个月或更长的默认数据保留期。
