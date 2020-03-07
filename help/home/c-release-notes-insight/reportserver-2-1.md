---
description: Data Workbench Report Portal 的安全更新。
title: DWB Report Portal 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWB Report Portal 2.1{#dwb-report-portal}

Data Workbench Report Portal 的安全更新。

**重要安全更新**

现在，Report Portal 的哈希算法更加强大，并支持加盐。如果您要升级到 Report Portal 2.1，请在 users.mdb 数据库中添加一个字段大小为 20 个字符的新文本字段 PasswordSalt。要存储密码盐，需要使用此字段。
