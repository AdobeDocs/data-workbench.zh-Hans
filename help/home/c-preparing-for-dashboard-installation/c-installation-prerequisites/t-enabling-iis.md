---
description: 第一步是在功能板服务器上启用IIS角色。
title: 启用 IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# 启用 IIS{#enabling-iis}

{{eol}}

第一步是在功能板服务器上启用IIS角色。

1. 在 **[!UICONTROL Administrative Tools]**，打开 **[!UICONTROL Server Manager]**.
1. 右键单击 **[!UICONTROL Server Manager]** 窗口。
1. 选择 **[!UICONTROL Add Roles]**。
1. 选择 **[!UICONTROL Web Server (IIS)]** 继续 **[!UICONTROL Add Roles Wizard]**. 确保启用以下角色服务：

   | 常见HTTP功能 |
   |---|
   | 静态内容 |
   | 默认文档 |
   | 目录浏览 |
   | HTTP错误 |
   | HTTP重定向 |

   | 应用程序开发 |
   |---|
   | ASP.NET |
   | .NET扩展性 |
   | ISAPI扩展 |
   | ISAPI过滤器 |

   | 运行状况和诊断 |
   |---|
   | HTTP日志记录 |
   | 日志记录工具 |
   | 请求监视器 |
   | 跟踪 |
   | 自定义日志记录 |

   | 安全性 |
   |---|
   | 基本身份验证 |
   | Windows身份验证 |
   | URL身份验证 |
   | 请求筛选 |
   | IP和域限制 |

   | 管理工具 |
   |---|
   | IIS管理控制台 |
   | IIS管理脚本和工具 |
   | 管理服务 |

1. 按照向导完成安装。
