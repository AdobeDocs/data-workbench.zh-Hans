---
description: 要指定要在报表门户中可用的用户档案，必须配置用户档案.xml文件。
title: 编辑 Profiles.xml 文件
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 11%

---

# 编辑 Profiles.xml 文件{#edit-the-profiles-xml-file}

要指定要在报表门户中可用的用户档案，必须配置用户档案.xml文件。

[!DNL profiles.xml]文件位于您指定用于输出的文件夹中。 默认情况下，它驻留在\*PortalName*\PortalFiles\Output folder中。

**向用户档案.xml文件添加用户档案名称**

1. 在运行IIS的计算机上，在文本编辑器（如记事本）中打开[!DNL profiles.xml]文件。
1. 为门户中的每个[!DNL Profile]添加用户档案元素和标签，如下例所示：

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. 保存并关闭该文件。
