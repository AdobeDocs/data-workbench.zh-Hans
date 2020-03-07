---
description: XSL样式表的代码示例。
solution: Analytics
title: 示例XSL样式表
topic: Data workbench
uuid: cac5c5ad-b0ec-45d8-901d-e39ce1f6d61a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 示例XSL样式表{#sample-xsl-style-sheet}

XSL样式表的代码示例。

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
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

