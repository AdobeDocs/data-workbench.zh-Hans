---
description: 第一步是在您的仪表板服务器上启用IIS角色。
title: 启用 IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# 启用 IIS{#enabling-iis}

第一步是在您的仪表板服务器上启用IIS角色。

1. 在&#x200B;**[!UICONTROL Administrative Tools]**&#x200B;下，打开&#x200B;**[!UICONTROL Server Manager]**。
1. 右键单击&#x200B;**[!UICONTROL Server Manager]**&#x200B;窗口左侧部分的“Roles”（角色）菜单项。
1. 选择 **[!UICONTROL Add Roles]**。
1. 选择&#x200B;**[!UICONTROL Web Server (IIS)]**&#x200B;并继续使用&#x200B;**[!UICONTROL Add Roles Wizard]**。 确保已启用以下角色服务：

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
   | .NET可扩展性 |
   | ISAPI扩展 |
   | ISAPI过滤器 |

   | 运行状况和诊断 |
   |---|
   | HTTP日志记录 |
   | 日志记录工具 |
   | 请求监视器 |
   | 描摹 |
   | 自定义日志 |

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
