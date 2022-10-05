---
description: 使用单个用户和群组帐户控制报表门户中的访问权限和权限。
title: 编辑 Email.asp 文件
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
exl-id: e984f12f-362a-4dee-9af3-6d7a38a178a4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 5%

---

# 编辑 Email.asp 文件{#edit-the-email-asp-file}

{{eol}}

使用单个用户和群组帐户控制报表门户中的访问权限和权限。

每次您添加新帐户或编辑现有帐户时，系统都会向您为该帐户指定的电子邮件地址发送确认电子邮件(请参阅 [使用帐户](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d))并复制到您在 [!DNL email.asp] 文件。

>[!NOTE]
>
>仅当您为帐户指定了电子邮件地址并正确配置了 [!DNL email.asp] 文件。 如果您不希望为帐户发送通知电子邮件，请将帐户的电子邮件字段留空。

此文件位于 `\*PortalName*\PortalASP` 文件夹。

1. 在运行IIS的计算机上，打开 [!DNL email.asp] 文件（如记事本）。
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
   <td colname="col2"> <p>发送消息的SMTP服务器的DNS名称或IP地址。 </p> <p>例如： <span class="filepath"> mail.hq.omniture.com</span></p> </td>
  </tr>
  <tr>
   <td colname="col1"> smtpserverport </td>
   <td colname="col2"> SMTP服务器侦听连接的端口。 这通常是端口25。 </td>
  </tr>
  <tr>
   <td colname="col1"> sendusing </td>
   <td colname="col2"> <p>指示消息的发送方式。 值包括： </p> <p>1 — 使用本地安装的SMTP服务发送消息。 如果在运行脚本的计算机上安装了SMTP服务，则使用此值。 </p> <p>2 — 使用网络上的SMTP服务发送消息。 如果运行脚本的计算机上未安装SMTP服务，则使用此值。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> smtpconnectiontimeout </td>
   <td colname="col2">时间 <span class="wintitle"> 报表</span> 应当等待SMTP服务器的响应，然后再超时连接。 </td>
  </tr>
 </tbody>
</table>

1. 对于 [!DNL NewUserEmail()] 和 [!DNL UpdateUserEmail()] 函数中，请设置以下变量：

   <table id="table_91C5E36B84A94C4097EE5993592BE587">
   <thead>
   <tr>
      <th colname="col1" class="entry"> 对于此变量。.. </th>
      <th colname="col2" class="entry"> 提供此信息 . . . </th>
   </tr>
   </thead>
   <tbody>
   <tr>
      <td colname="col1"> From </td>
      <td colname="col2">您希望在确认电子邮件的“发件人”标题行中显示的文本。 此值可能与 <span class="wintitle"> CC</span> 值。 </td>
   </tr>
   <tr>
      <td colname="col1"> CC </td>
      <td colname="col2"> <p>可选。应接收有关新用户帐户和已更改用户帐户的所有消息副本的人员或别名的有效电子邮件地址。 您可以指定多个电子邮件地址，方法是用逗号分隔地址（无空格）。 </p> <p>例如： <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>注意：收件人将收到包含用户密码的电子邮件副本。 </p> </p> </td>
   </tr>
   <tr>
      <td colname="col1"> 主题 </td>
      <td colname="col2"> 您希望在确认电子邮件的主题标题行中显示的文本。 </td>
   </tr>
   <tr>
      <td colname="col1"> WebPath </td>
      <td colname="col2"> <p>门户的实际路径。 </p> <p>例如： <span class="filepath"> https://portal.omniture.com/Example</span></p> </td>
   </tr>
   <tr>
      <td colname="col1"> 正文 </td>
      <td colname="col2"> <p>自动生成的电子邮件中包含的文本。 </p> <p>例如，以下是发送的电子邮件中包含的默认文本，用于提供登录信息：
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">您的Web门户登录信息如下所示： </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>用户名：用户名 </p><p>新密码：密码 </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>您可以使用以下URL访问门户： </p><p><span class="filepath"> https://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">登录到门户后，您可以在 <span class="wintitle"> 管理员</span> 选项卡。 </li>
      </ul></p> </td>
   </tr>
   </tbody>
   </table>

1. 保存并关闭该文件。
