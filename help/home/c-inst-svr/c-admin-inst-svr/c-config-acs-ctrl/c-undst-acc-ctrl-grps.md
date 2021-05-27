---
description: 有五个预建的访问控制组可用，但您可以根据需要创建和管理其他组。
title: 了解访问控制组
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 8%

---

# 了解访问控制组{#understanding-access-control-groups}

有五个预建的访问控制组可用，但您可以根据需要创建和管理其他组。

您可以定义每个访问控制组的成员，以及每个组具有只读或读写访问权限的目录。

预定义的组定义如下：

| 群组 | 描述 |
|---|---|
| 管理员 | 允许访问所有目录和文件。 默认IP地址为127.0.0.1（本地主机）。 |
| 传感器 | 仅允许访问[!DNL Sensor]用于传输数据的文件。 |
| 用户 | 允许对[!DNL Insight]用户执行基本分析任务所需的元素进行只读访问。 |
| 高级用户 | 允许对[!DNL Insight]用户执行基本分析任务所需的元素进行只读访问，并允许对[!DNL Profiles]文件夹进行读写访问以修改配置文件。 |
| 群集服务器 | 允许访问指定为群集服务器的[!DNL Insight Servers]。 |
| 报表服务器 | 允许访问连接到[!DNL Insight Server]的[!DNL Report]计算机。 |

访问控制组的成员使用其IP地址或SSL证书信息来定义。

如果SSL证书不可用，则可以使用IP地址定义组成员。 典型的[!DNL Insight]安装包含SSL证书，而对[!DNL Sensor(s)]使用证书是可选的。 对于[!DNL Insight Server]，使用IP地址而不是SSL证书来定义群集服务器。

以下代码可用于定义群组成员：

| 访问类型代码 | 定义 |
|---|---|
| O | 组织 |
| CN | 通用名称 |
| L | 区域 |
| ST | 州或省 |
| C | 国家/地区 |
| 区 | 组织单位 |
| 电子邮件 | 电子邮件地址 |
