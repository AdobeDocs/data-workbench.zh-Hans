---
description: 使用单个用户和用户组帐户控制对报告门户中的访问权限和权限。
solution: Analytics
title: 编辑Email.asp文件
topic: Data workbench
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 编辑Email.asp文件{#edit-the-email-asp-file}

使用单个用户和用户组帐户控制对报告门户中的访问权限和权限。

每次添加新帐户或编辑现有帐户时，都会向您为该帐户指定的电子邮件地址发送确认电子邮件(请参阅 [Working with Accounts](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d))，并复制到您在文件中指定的电子邮件地址 [!DNL email.asp] 。

>[!NOTE]
>
>只有在您为帐户指定了电子邮件地址并正确配置了文件后，才会向帐户用户发送通知电子 [!DNL email.asp] 邮件。 如果不希望为帐户发送通知电子邮件，请将帐户的电子邮件字段留空。

该文件位于文件夹 `\*PortalName*\PortalASP` 中。

1. 在运行IIS的计算机上，在文本编辑 [!DNL email.asp] 器（如记事本）中打开文件。
1. 设置以下变量：

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 对于此变量。.. </th> 
   <th colname="col2" class="entry"> 提供此信息 . . . </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>发送消息时所通过的SMTP服务器的DNS名称或IP地址。 </p> <p>例如： <span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> SMTP服务器监听连接的端口。 这通常是端口25。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sendusing </td> 
   <td colname="col2"> <p>指示消息的发送方式。 值包括： </p> <p>1 —— 使用本地安装的SMTP服务发送消息。 如果SMTP服务安装在运行脚本的计算机上，则使用此值。 </p> <p>2 —— 使用网络上的SMTP服务发送消息。 如果运行脚本的计算机上未安装SMTP服务，请使用此值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2">SMTP服务器发出响 <span class="wintitle"> 应</span> ，报告在超时连接之前应等待的时间。 </td> 
  </tr> 
 </tbody> 
</table>

1. 对于和 [!DNL NewUserEmail()] 函数， [!DNL UpdateUserEmail()] 请设置以下变量：

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 对于此变量。.. </th> 
      <th colname="col2" class="entry"> 提供此信息 . . . </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> 从 </td> 
      <td colname="col2">要显示在确认电子邮件的“发件人”标题行中的文本。 此值可能与CC值相 <span class="wintitle"> 同</span> 。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>可选。应接收有关新帐户和已更改用户帐户的所有消息副本的个人或别名的有效电子邮件地址。 您可以通过用逗号（无空格）分隔地址来指定多个电子邮件地址。 </p> <p>例如： <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>注意： 收件人会收到包含用户密码的电子邮件副本。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 主题 </td> 
      <td colname="col2"> 要显示在确认电子邮件的主题标题行中的文本。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>门户的实际路径。 </p> <p>例如： <span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 正文 </td> 
      <td colname="col2"> <p>自动生成的电子邮件中包含的文本。 </p> <p>例如，以下是发送的用于提供登录信息的电子邮件中包含的默认文本： 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">您的Web门户登录信息提供如下： </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>用户名：用户名 </p><p>新密码：口令 </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>您可以使用以下URL访问门户： </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">登录门户后，可以在“管理员”选项卡上更改 <span class="wintitle"> 密码</span> 。 </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 保存并关闭该文件。
