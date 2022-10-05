---
description: XSL样式表的代码示例。
title: 示例 XSL 样式表
uuid: cac5c5ad-b0ec-45d8-901d-e39ce1f6d61a
exl-id: 688b0ce5-999b-4cfc-9228-146450132aee
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '20'
ht-degree: 40%

---

# 示例 XSL 样式表{#sample-xsl-style-sheet}

{{eol}}

XSL样式表的代码示例。

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="https://www.w3.org/1999/XSL/Transform">
<xsl:template match="/">
  <html>
  <body>
    <h2>Reports</h2>
    <xsl:for-each select="REPORTS/REPORT">
    <a>
    <xsl:attribute name="href">
    <xsl:value-of select="PATH"/>
    </xsl:attribute>
    <xsl:value-of select="NAME"/>
    </a><p/>
    </xsl:for-each>
  </body>
  </html>
</xsl:template>
</xsl:stylesheet>
```
