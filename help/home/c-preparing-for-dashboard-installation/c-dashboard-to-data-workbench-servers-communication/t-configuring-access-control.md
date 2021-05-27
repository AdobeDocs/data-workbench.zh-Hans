---
description: 功能板需要特定的只读权限才能访问和显示您的Data Workbench数据。 不需要写入权限。
title: 配置访问控制
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 6%

---

# 配置访问控制{#configuring-access-control}

功能板需要特定的只读权限才能访问和显示您的Data Workbench数据。 不需要写入权限。

配置访问控制涉及在FSU上编辑[!DNL Access Control.cfg]文件，并添加新组以授予Data Workbench功能板的权限：

1. 编辑[!DNL AccessControl.cfg]文件（最好使用Data Workbench工作站）。
1. 创建名为&#x200B;*Insight Dashboard Access*&#x200B;的新群组。
1. 在此组成员下，添加为此目的向您提供的正确CN(示例：CN:INSIGHT-USER01)。 请联系Adobe客户关怀，获取此CN。
1. 在此组的只读访问权限下，修改列表以反映以下内容：

* /配置文件/$
* /配置文件/
* /地址
* /状态/
* /用户/$

1. 从读写访问部分删除所有项目，因为功能板不需要写权限。
1. 将对[!DNL AccessControl.cfg]文件所做的更改保存到服务器，以便权限生效。
