---
description: 有五个预建访问控制组可用，但您可以根据需要创建和管理其他组。
solution: Insight
title: 了解访问控制组
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解访问控制组{#understanding-access-control-groups}

有五个预建访问控制组可用，但您可以根据需要创建和管理其他组。

您可以定义每个访问控制组的成员以及每个组具有只读或读写访问权限的目录。

预定义的组定义如下：

| 群组 | 描述 |
|---|---|
| 管理员 | 允许访问所有目录和文件。 默认IP地址为127.0.0.1（本地主机）。 |
| 传感器 | 仅允许访问用于传输数据 [!DNL Sensor] 的文件。 |
| 用户 | 允许对用户执行基本分析任务所需的元 [!DNL Insight] 素进行只读访问。 |
| 高级用户 | 允许对用户执行基本分析任务所需的元素进行只读访 [!DNL Insight] 问，并允许对文件夹进行读写访问以修改 [!DNL Profiles] 配置文件。 |
| 群集服务器 | 允许访问指 [!DNL Insight Servers] 定为群集服务器的服务器。 |
| 报告服务器 | 允许访问 [!DNL Report] 连接到的计算机 [!DNL Insight Server]。 |

访问控制组的成员使用其IP地址或SSL证书信息进行定义。

如果SSL证书不可用，则可以使用IP地址定义组成员。 典型的安装 [!DNL Insight] 包括SSL证书，而证书的使用是可选 [!DNL Sensor(s)] 的。 对于 [!DNL Insight Server]群集服务器，使用IP地址而不是SSL证书来定义。

以下代码可用于定义用户组成员：

| 访问类型代码 | 定义 |
|---|---|
| O | 组织 |
| CN | 通用名称 |
| L | 区域 |
| ST | 州或省 |
| C | 国家/地区 |
| OU | 组织股 |
| 电子邮件 | 电子邮件地址 |

