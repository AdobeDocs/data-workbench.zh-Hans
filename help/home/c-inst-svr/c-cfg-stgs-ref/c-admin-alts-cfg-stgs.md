---
description: 为Insight Server、Repeater或Transform配置管理警报的说明。
solution: Insight
title: 管理警报配置设置
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 管理警报配置设置{#administrative-alerts-configuration-settings}

为Insight Server、Repeater或Transform配置管理警报的说明。

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
   <td colname="col2"> 类别的名称。 “默认”类别为必填项。 请参阅此表中的错误类别。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 错误类别 </td> 
   <td colname="col2"> 允许您将错误与错误分类文件一起分类。 每个“错误类别”可以有其自己的“收件人”集和自己的“节流延迟”。 例如，您可以创建一个“关键”类别，其限制延迟为0，这样，每个关键错误都会通过电子邮件立即发送到“收件人”列表中指定的收件人。 与“错误分类文件”中的子字符串不匹配的错误将分配给“默认”类别。 要添加新类别，请右键单击某个数字，然后单击“添加新 <span class="uicontrol"> 建” </span> &gt;“错 <span class="uicontrol"> 误类别” </span>。 您还可以使用右键单击操作复制或删除它们。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 错误分类文件 </td> 
   <td colname="col2"> <p>要用于对每个警报分类的文件的名称。 使用记事本创建此文件。 此文件每行应有三列，各列之间用制表符分隔。 第一列是要在错误中匹配的字符串。 ^符号与开头匹配，$与字符串的结尾匹配；所有其他字符都是字面匹配的。 第二列是匹配错误的类别，该类别位于“错误类别”中。 第三条是替代消息，该消息在发送的电子邮件中的实际错误消息前面加上。 如果未指定文件，则所有错误都归为“默认”。 </p> <p>要查看此文件的示例，请参阅Lookups目 <span class="filepath"> 录中的Error Categories.txt </span> 文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 从 </td> 
   <td colname="col2"> <p>电子邮件“发件人”参数中显示的地址。 </p> <p>示例： <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小磁盘空间(MB) </td> 
   <td colname="col2"> 当服务器使用的任何目录中的可用磁盘存储低于此值时，服务器会生成电子邮件警报。 默认值为 1000。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器警报超时（分钟） </td> 
   <td colname="col2"> <p>服务器在此时间窗口内未从已配置和先前连接的传感器收到任何数据时，会生成 <span class="wintitle"> 电 </span> 子邮件警报。 默认值为 15。 </p> <p> <p>注意： 传感 <span class="wintitle"> 器警报超时仅在与传感器的现有连接断开时 </span> 才 <span class="wintitle"></span> 有效。 如果服务器的服务停止并重新启动，而传感器 <span class="wintitle"> 未连 </span> 接，则服务器不会生成电子邮件警报。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器地址 </td> 
   <td colname="col2"> <p>发出电子邮件的SMTP服务器地址。 </p> <p>示例： <span class="filepath"> mail.mycompany.com </span></p> <p>使用上述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器口令 </td> 
   <td colname="col2"> <p>登录SMTP服务器的口令。 除非发送邮件需要登录，否则此参数是可选的。 </p> <p>使用上述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器用户 </td> 
   <td colname="col2"> <p>用于登录到SMTP服务器的用户ID/名称。 除非发送邮件需要登录，否则此参数是可选的。 </p> <p>使用上述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 节流延迟（秒） </td> 
   <td colname="col2"> 该类别中两个错误之间必须经历的最小秒数，才能发送电子邮件。 值为0会立即发送电子邮件。 </td> 
  </tr> 
 </tbody> 
</table>

