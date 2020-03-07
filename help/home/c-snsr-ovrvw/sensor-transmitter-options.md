---
description: 有关UNIX和Windows的传感器发射器启动命令的信息。
title: 传感器发射器命令行选项
uuid: 8d077d76-a709-494e-a176-07ca3e761662
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 传感器发射器命令行选项{#sensor-transmitter-command-line-options}

有关UNIX和Windows的传感器发射器启动命令的信息。

## UNIX的启动命令 {#section-e8e7a6e62971499ba5f633d896590949}

要在UNIX干上启动传感器发射器，请使用以下命令：

```
txlogd -f configFileName
```

其中configFileName是发射机配置文件(txlogd.conf)的完全限定名称。

默认情况下，发射器作为后台进程（守护程序）运行，并将操作消息写入syslog。

以下是文本的命令行开关的完整列表：

| 交换机 | 描述 |
|---|---|
| -f | 指定配置文件的完全限定名称(txlogd.conf)。 如果不指定此交换机，则发射器将在当前目录中查找txlogd.conf。 |
| -n | 以交互模式（而非后台进程）启动发射器。 |
| -i | 以交互模式启动发射器，并将调试输出定向到停止。 |
| -d | 将发射器作为后台进程启动，并将调试输出定向到当前目录中的txlogd-debug.log。 |
| -c | 启动发射器并创建磁盘队列文件（如果它不存在）。 如果磁盘队列已存在，则忽略此参数。 |
| -x | 启动发送器并使其在发送磁盘队列中的最后一个分组后退出。 在准备管理操作（如创建新队列文件）时，可以使用此选项排出队列。 |

## Windows的启动命令 {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

要启动传感器并将其注册为Windows系统上的服务，请使用以下命令：

```
txlog /regserver
```

