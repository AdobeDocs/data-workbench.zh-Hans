---
description: 配置Insight Server、Repeater或Transform管理警报的说明。
title: 管理警报配置设置
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# 管理警报配置设置{#administrative-alerts-configuration-settings}

配置Insight Server、Repeater或Transform管理警报的说明。

在以下文件中完成参数：

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 类别 </td> 
   <td colname="col2"> 类别的名称。 类别为“默认”。 请参阅此表中的错误类别。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 错误类别 </td> 
   <td colname="col2"> 允许您将错误与错误分类文件一起分类。 每个错误类别可以有自己的收件人集和自己的节流延迟。 例如，您可以创建一个限制延迟为0的关键类别，这样每个关键错误都会立即通过电子邮件发送给收件人列表中指定的收件人。 与错误分类文件中的子字符串不匹配的错误将分配给默认类别。 要添加新类别，请右键单击数字，然后单击<span class="uicontrol">新增</span> &gt; <span class="uicontrol">错误类别</span>。 您还可以使用右键单击操作复制或删除它们。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分类文件出错 </td> 
   <td colname="col2"> <p>要用于对每个警报进行分类的文件的名称。 使用记事本创建此文件。 此文件的每行应有三列，以制表符分隔。 第一列是要在错误中匹配的字符串。 ^号与开头匹配，$与字符串结尾匹配；所有其他字符都是字面匹配的。 第二列是匹配错误的类别，位于“错误”类别。 第三条是替代消息，它以发送的电子邮件中的实际错误消息为前缀。 如果未指定文件，则所有错误均分类为“默认”。 </p> <p>要查看此文件的示例，请参阅Lookups目录中的<span class="filepath"> Error 类别s.txt </span>文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> From </td> 
   <td colname="col2"> <p>在电子邮件的“from”参数中显示的地址。 </p> <p>示例：<span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小磁盘空间(MB) </td> 
   <td colname="col2"> 当服务器使用的任何目录中的可用磁盘存储低于此值时，服务器会生成电子邮件警报。 默认值为 1000。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器警报超时（分钟） </td> 
   <td colname="col2"> <p>服务器在此时间窗口内未从已配置且先前连接的<span class="wintitle">传感器</span>接收到任何数据时，会生成电子邮件警报。 默认值为 15。 </p> <p> <p>注意： <span class="wintitle">传感器</span>警报超时仅在与<span class="wintitle">传感器</span>的现有连接断开时有效。 如果服务器的服务停止并重新启动，而<span class="wintitle">传感器</span>未连接，则服务器不会生成电子邮件警报。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器地址 </td> 
   <td colname="col2"> <p>传出电子邮件的SMTP服务器地址。 </p> <p>示例：<span class="filepath"> mail.mycompany.com </span></p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器密码 </td> 
   <td colname="col2"> <p>用于登录到SMTP服务器的口令。 除非需要登录才能发送邮件，否则此参数是可选的。 </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器用户 </td> 
   <td colname="col2"> <p>用于登录到SMTP服务器的用户ID/名称。 除非需要登录才能发送邮件，否则此参数是可选的。 </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 节流延迟（秒） </td> 
   <td colname="col2"> 要发送电子邮件的类别中两个错误之间必须经历的最小秒数。 值为0会立即发送电子邮件。 </td> 
  </tr> 
 </tbody> 
</table>
