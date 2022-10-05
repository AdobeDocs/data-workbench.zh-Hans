---
description: 有关UNIX和Windows的传感器发送器启动命令的信息。
title: 传感器发送器命令行选项
uuid: 8d077d76-a709-494e-a176-07ca3e761662
exl-id: f4b27859-8fab-42cd-bad0-b32f87764668
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 6%

---

# 传感器发送器命令行选项{#sensor-transmitter-command-line-options}

{{eol}}

有关UNIX和Windows的传感器发送器启动命令的信息。

## UNIX的启动命令 {#section-e8e7a6e62971499ba5f633d896590949}

要在UNIX主干上启动传感器发送器，请使用以下命令：

```
txlogd -f configFileName
```

其中configFileName是发送器配置文件(txlogd.conf)的完全限定名称。

默认情况下，发送器作为后台进程（守护进程）运行，并将操作消息写入syslog。

以下是txlogd命令行开关的完整列表：

| 交换机 | 描述 |
|---|---|
| -f | 指定配置文件的完全限定名称(txlogd.conf)。 如果未指定此开关，则发送器将在当前目录中查找txlogd.conf。 |
| -n | 以交互模式启动发送器（不作为后台进程）。 |
| -i | 以交互模式启动发送器，并将调试输出定向到stdout。 |
| -d | 将发送器作为后台进程启动，并将调试输出定向到当前目录中的txlogd-debug.log。 |
| -c | 启动发送器并创建磁盘队列文件（如果不存在）。 如果磁盘队列已存在，则忽略此参数。 |
| -x | 启动发送器，并在发送磁盘队列中的最后一个数据包后，使其退出。 您可以使用此选项来排出队列，以准备管理操作，如创建新队列文件。 |

## Windows的启动命令 {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

要启动传感器并将其注册为Windows系统上的服务，请使用以下命令：

```
txlog /regserver
```
