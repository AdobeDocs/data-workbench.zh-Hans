---
description: 第一步是在功能板服务器上启用IIS角色。
solution: Analytics
title: 启用IIS
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 启用IIS{#enabling-iis}

第一步是在功能板服务器上启用IIS角色。

1. 在下 **[!UICONTROL Administrative Tools]**&#x200B;面，打开 **[!UICONTROL Server Manager]**。
1. 右键单击窗口左侧部分的“角色”菜单项 **[!UICONTROL Server Manager]** 目。
1. 选择 **[!UICONTROL Add Roles]**。
1. 选 **[!UICONTROL Web Server (IIS)]** 择并继续 **[!UICONTROL Add Roles Wizard]**。 确保启用了以下角色服务：

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
   | 记录工具 |
   | 请求监视器 |
   | 描摹 |
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
