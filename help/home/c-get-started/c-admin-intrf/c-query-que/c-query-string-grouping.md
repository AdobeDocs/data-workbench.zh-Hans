---
description: 查询字符串分组允许您将大量的字段集成在一起。
title: 查询字符串分组
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
exl-id: 4052cf7e-abdf-4e16-9f42-521c4e719786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 84%

---

# 查询字符串分组{#query-string-grouping}

{{eol}}

查询字符串分组允许您将大量的字段集成在一起。

查询字符串分组特定于每个配置文件，但在如下示例显示的转换中也可正常工作。

1. 通过添加自定义配置文件( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg])，然后添加转换类型 *BuildNameValuePair* 作为参数。

   ```
   2 = BuildNameValuePair:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to build)
             Name = string: Custom Events 
             Output = string: x-event-list       
   ```

1. 通过添加自定义配置文件 ([!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg])，然后添加转换类型 *ExtractNameValuePairs* 作为参数，可创建一个新文件，用于将压缩数据提取到需要使用的字段。

   ```
   2 = ExtractNameValuePairs:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Field = string: x-event-list 
         Name = string: Custom Events 
         Output Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to extract) 
             Name = string: Custom Events 
             Output = string: x-event-list   
   ```

## 其他用户 {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

如果您有许多自定义 eVar、prop 和变量字段，那么在日志处理过程中，您可以在一个报表中构建名称值对来合并字段。例如，您可以在合并字段中构建命名-值对，以减小 [!DNL tempDB] 文件大小。

![](assets/query_string_grouping.png)
