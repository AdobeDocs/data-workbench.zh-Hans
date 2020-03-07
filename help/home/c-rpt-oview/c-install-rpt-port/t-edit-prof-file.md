---
description: 要指定要在Report Portal中可用的配置文件，必须配置profiles.xml文件。
solution: Analytics
title: 编辑Profiles.xml文件
topic: Data workbench
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 编辑Profiles.xml文件{#edit-the-profiles-xml-file}

要指定要在Report Portal中可用的配置文件，必须配置profiles.xml文件。

文 [!DNL profiles.xml] 件位于您指定用于输出的文件夹中。 默认情况下，它位于\*PortalName*\PortalFiles\Output folder中。

**向profiles.xml文件添加配置文件名称**

1. 在运行IIS的计算机上，在文本编辑 [!DNL profiles.xml] 器（如记事本）中打开文件。
1. 为门户中的每个组件添加 [!DNL Profile] 配置文件元素和标记，如下例所示：

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
