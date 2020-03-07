---
description: 该功能板需要特定的只读权限才能访问和显示您的数据工作台数据。 不需要写权限。
solution: Analytics
title: 配置访问控制
topic: Data workbench
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置访问控制{#configuring-access-control}

该功能板需要特定的只读权限才能访问和显示您的数据工作台数据。 不需要写权限。

配置访问控制涉及在FSU [!DNL Access Control.cfg] 上编辑文件，并添加一个新组以授予Data Workbench控制面板的权限：

1. 编辑文 [!DNL AccessControl.cfg] 件（最好使用Data Workbench工作站）。
1. 创建一个名为 *Insight Dashboard Access的新用户组*。
1. 在此用户组的成员下，添加为此目的提供给您的正确CN(示例：CN:INSIGHT-USER01)。 请与Adobe客户关怀部门联系以获取此CN。
1. 在此组的只读访问权限下，修改列表以反映以下内容：

* /配置文件/$
* /配置文件/
* /地址
* /状态/
* /用户/$

1. 从读写访问部分删除任何项目，因为功能板不需要写权限。
1. 将对文件所做的更改保 [!DNL AccessControl.cfg] 存到服务器，以便获得生效的权限。
