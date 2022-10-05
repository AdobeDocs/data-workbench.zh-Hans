---
description: AdobeData Workbench提供了一些工具和流程来为您的数据做好准备，以遵守《通用数据保护条例》(GDPR)。
title: Data Workbench 支持 GDPR
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 4%

---

# Data Workbench 支持 GDPR

{{eol}}

AdobeData Workbench提供了一些工具和流程来使您的数据符合 [!DNL General Data Protection Regulations] (GDPR)。

与所有Adobe Analytics解决方案一样，Data Workbench在处理Adobe Analytics数据馈送时，会提供分析变量的清理、删除和标签功能，从而为GDPR提供支持。 为支持GDPR实施，Adobe允许您根据与Adobe签署的协议中规定的贵公司权限，设置GDPR流程。 请参阅 [Adobe Analytics和GDPR以了解更多信息](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=zh-Hans).

GDPR法规确定了负责实施GDPR的不同各方的角色和义务(请参阅 [GDPR与您的业务](https://www.adobe.com/cn/privacy/general-data-protection-regulation.html))。

* 贵组织充当 **数据控制器** 以根据您的需求和限制确定个人数据的上下文和保留。 Adobe然后代表您处理和存储此数据。
* Adobe充当 **数据处理器** 根据您与Adobe的协议，提供用于实施GDPR要求的软件和服务。
* 在将Data Workbench与GDPR服务集成并符合GDPR标准后，访问网站( **数据主体**)可以由数据处理者Adobe行使其“被遗忘权”。 为了实现被遗忘权，您作为数据控制者可以将受挑战的访客ID上传到UI或API中Adobe。 请参阅 [Adobe Analytics GDPR工作流程](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-workflow.html?lang=en) 文档，包括 [提交访问和删除请求](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html) 中。

>[!NOTE]
>
>对于其他数据源，贵组织将负责从其他日志源（如CRM、POS、IVR和其他原始数据源）中清除受挑战的访客ID。 自定义范围的服务包将可用于通过 _为每个数据源提供完整的替换文件集_ 需要持续的服务容器来支持或维护。

## 升级DWB以实施GDPR

咨询团队将就适当的服务包为您提供建议，以使现有实施符合要求。 请联系您的客户成功经理(CSM)以了解更多信息。

如果需要：

* [升级到最新版本](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) Data Workbench。 为获得最高的安全性，DWB 6.7版本中添加了GDPR集成所需的新证书和安全功能。
* 如果使用旧版TSV Analytics事件日志，请升级到 [Avro数据馈送](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* 如果将旧版UCP（统一客户流程）与转换结合使用来更新现有日志，请升级到当前流程。 更新后的进程会直接生成一个主控的查找文件，用于跨源映射访客ID。
* 标准化数据流量以适应GDPR服务。
* 建立自定义范围的服务包以管理其他日志源，如CRM、POS、IVR和其他原始数据源。
* 在Analytics合同中确认默认数据保留期为25个月或更长。
