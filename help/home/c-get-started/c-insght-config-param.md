---
description: 在 Insight.cfg 文件中设置参数，以指定您的网络连接和 Data Workbench 配置设置。
title: 配置参数
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 71%

---

# 配置参数{#configuration-parameters}

{{eol}}

在 Insight.cfg 文件中设置参数，以指定您的网络连接和 Data Workbench 配置设置。

下面的示例专门列出了默认情况下 [!DNL Insight.cfg] 文件包含的参数。

**新布局视图**

![](assets/config_tree_new_layout.png)

**原始布局视图**

![](assets/cfg_Workstation_AddServer.png)

某些适用于新 [!DNL Insight.cfg] 文件的参数或许不能在您的 [!DNL Insight.cfg] 文件版本中使用。如果需要其中一个参数，必须将其添加到 [!DNL Insight.cfg] 文件使用 [!DNL Add Custom Key]，方法是右键单击参数，然后指定名称和类型。 您还可以通过打开 [!DNL .cfg] 文件(位于Data Workbench安装目录中)。

下面的示例涵盖了 [!DNL Insight.cfg] 文件中的所有参数，您可以将该示例作为添加参数项的模型：

```
Licensing = serverInfo:
  Proxy Address = string: 
  Proxy Port = int: 8080
  Proxy User Name = string: 
  Proxy Password = string: 
Servers = vector: 1 items
  0 = serverInfo: 
    Address = string: VS02
    Name = string: Insight Server
    Port = int: 443
    Proxy Address = string: 
    Proxy Password = string: 
    Proxy Port = int: 8080
    Proxy User Name = string: 
    SSL Client Certificate = string: Named User.pem
    SSL Server Common Name = string: VS02
    Use Address File = bool: false
    Use SSL = bool: true
Color Set = int: 0
Default to Online = bool: false
Fonts = vector: 0 items
Gamma = float: 1.6
Maximum Sample Size (MB) = double: 0
Network Location = string: 
Unhide All = bool: false
Unlock = bool: false
Update Software = bool: true
User Folder = string: User\\
Toolbar Icons = bool: false
```

下表按照字母顺序介绍了可用的 [!DNL Insight.cfg] 文件参数。

<table id="table_4465713A08B649E280A3B4840E829518"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>地址 </p> </td> 
   <td colname="col2"> <p>Data Workbench服务器计算机的主机名或数字IP地址。 </p> <p>示例：<span class="filepath">vsServer.mycompany.com or 192.168.1.90</span> </p> <p>如果未指定 <span class="wintitle">Address</span>（地址），则在 Use Address File（使用地址文件）设置为 false 时，<span class="keyword">客户端</span>会使用 SSL Server Common Name（SSL 服务器通用名称）参数中指定的通用名称。 </p> <p> <p>注意：如果将 Use Address File（使用地址文件）参数设置为 true，则在<span class="keyword">客户端</span>上打开首个配置文件后，可能会删除在 Address（地址）参数中输入的文本。然后，Network Location（网络位置）参数设置确定群集地址文件中的哪些地址可以用来连接到主服务器。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Color Set（颜色集） </p> </td> 
   <td colname="col2"> <p>指定<span class="keyword">客户端应用程序</span>的背景颜色。选项如下所示： </p> <p>0 = 黑色 </p> <p>1 = 白色 </p> <p>2 = 单色 </p> <p>默认值为 0，黑色。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default Online Level（默认联机级别） </p> </td> 
   <td colname="col2"> <p>可选。允许您使Data Workbench实例在每次打开时默认作为流、脱机或联机工作。 选项包括 Streaming（流）、Online（联机）或 Offline（脱机）。Data Workbench的默认配置是脱机工作。 </p> <p> <p>注意：在决定默认联机工作之前，请确保权衡 <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> 脱机工作和联机工作</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fonts（字体） </p> </td> 
   <td colname="col2"> <p>可选。该矢量列出<span class="keyword">客户端</span>在渲染基于 UTF8 的 unicode 特殊字符时应使用的字体。列表中字体的数量不受限制。 </p> <p>第一种字体应始终为 Lucida Sans Console。如果 <span class="filepath"> Insight.cfg</span> 文件，Data Workbench仅使用Lucida Sans Console来显示文本。 </p> <p> Data Workbench使用列表中的第一种字体来渲染所有字符，直到遇到无法渲染的字符。 它便会使用列表中的第二种字体来渲染该字符。如果该字体未呈现字符，则Data Workbench会使用列表中的第三种字体来呈现该字符，依此类推，直到该字体到达字体列表的结尾。 如果矢量中未列出正确的字体，则Data Workbench将显示字符的十六进制值。 </p> <p> <p>注意：运行Data Workbench时，请勿更改此参数。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma（伽马） </p> </td> 
   <td colname="col2"> Data Workbench显示的Gamma设置。 默认值为 1.6。Adobe 不建议更改此值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Licensing（许可） </p> </td> 
   <td colname="col2"> <p>可选。仅当您通过代理服务器联系 Adobe 的许可证服务器时，才需要修改 Licensing（许可）矢量中的参数。 </p> <p>节标识符，用于使您的<span class="keyword">客户端</span>可以通过代理服务器联系 Adobe 许可证服务器的参数。展开 Licensing（许可）节点并填完以下参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy Address（代理地址） </p> </td> 
   <td colname="col2"> <p>可选。<span class="keyword">客户端</span>在访问 Adobe 许可证服务器时必须使用的代理服务器的地址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy Port（代理端口） </p> </td> 
   <td colname="col2"> <p>可选。代理服务器的端口。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy User Name（代理用户名） </p> </td> 
   <td colname="col2"> <p>可选。代理服务器的用户名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy Password（代理密码） </p> </td> 
   <td colname="col2"> <p>可选。与 Proxy User Name（代理用户名）相关联的密码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximum Sample Size (MB)（最大采样大小 (MB)） </p> </td> 
   <td colname="col2"> <p>指定在单台计算机上运行的<span class="keyword">客户端</span>所使用的数据缓存中允许的最大大小。 </p> <p>而 <span class="filepath"> Server.cfg</span> 文件为所有 <span class="keyword"> 客户</span> 连接到Data Workbench服务器（默认为250e6字节）时，“最大采样大小”参数允许您进一步限制特定计算机的数据缓存大小。 当客户端安装在存储容量或计算能力有限的计算机上时，这非常有用。 </p> <p> <p>注意：此参数会限制客户端程序本地查询的本地数据采样大小。相比之下，<span class="filepath">cache.db</span> 文件包含客户端连接的每个配置文件的数据，还包含元素名称及其维度。运行本地查询时需要 <span class="filepath">cache.db</span> 文件中的这些元素名称和维度。因此，除减少数据集中的元素数量外，没有任何方法可限制其大小。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名称 </p> </td> 
   <td colname="col2">可选。<span class="keyword">客户端</span>用来标识<span class="keyword">服务器</span>的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Network Location（网络位置） </p> </td> 
   <td colname="col2"> <p>可选。该 <span class="keyword"> 客户端</span> 使用将Data Workbench服务器通用名称解析为IP地址。 可用的网络位置在服务器上的地址文件中进行定义。有关详细信息，请参阅《服务器产品安装和管理指南》<i></i>。 </p> <p>如果您没有指定网络位置，<span class="keyword">客户端</span>会使用默认的网络位置（“Insight”）解析通用名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port（端口） </p> </td> 
   <td colname="col2"> <p><span class="keyword">客户端</span>将请求发送到的端口。此端口号必须与Data Workbench服务器侦听请求的端口匹配。 通常使用 443 作为端口号进行安全连接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy Address（代理地址） </p> </td> 
   <td colname="col2"> <p>如果需要代理服务器才能连接到Data Workbench服务器计算机，则必须至少完成此参数和Proxy Port（代理端口）参数。 您可以选择性地完成 Proxy User Name（代理用户名）和 Proxy User Password（代理用户密码）参数。 </p> <p>该代理服务器的地址 <span class="keyword"> 客户</span> 必须用来访问Data Workbench服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy Password（代理密码） </p> </td> 
   <td colname="col2"> <p>可选。代理服务器的密码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy Port（代理端口） </p> </td> 
   <td colname="col2"> <p>代理服务器的端口。默认值为 8080。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy User Name（代理用户名） </p> </td> 
   <td colname="col2"> <p>可选。代理服务器的用户名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜索 </p> </td> 
   <td colname="col2"> <p>在 <span class="filepath">Insight.cfg</span>（或任何 <span class="filepath">.cfg</span> 文件）中，您可以按照键名称、键类型或值来进行搜索以快速查找条目，从而消除了以滚动方式在展开的大型文件中查找嵌套信息的需要。您可以查找到维度名称、服务器名称等。 </p> <p>在此字段中键入一个搜索短语以查找数据。根据是否匹配成功，字段的颜色将会发生相应变化。匹配项将会突出显示，而非匹配项将会变暗。如果不存在匹配项，则搜索字段的背景将会变为红色。当您按 Enter 时，配置树将展开每个存在匹配项的位置，并折叠不存在匹配项的位置。 </p> <p>您还可以在 <span class="wintitle">Search</span> 字段中使用正则表达式。例如，您可以使用 re: <span class="filepath">*zip.*</span> 搜索包含单词“zip”的任何项。 </p> <p>若要清除搜索，请按 <span class="uicontrol">Esc</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>服务器 </p> </td> 
   <td colname="col2"> <p>从<span class="keyword">客户端</span>到<span class="keyword">服务器</span>连接的矢量标题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Client Certificate（SSL 客户端证书） </p> </td> 
   <td colname="col2"> <p>可选参数，除非您拥有多个证书。包含此Data Workbench副本的数字证书的文件名。 这是您在“下载和安装数字证书”中下载的文件。 </p> <p>示例：<span class="filepath">Samantha Smith.pem</span> </p> <p>如果您将此参数保留为空，<span class="keyword">客户端</span>将使用提供的任何证书。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Server Common Name（SSL 服务器通用名称） </p> </td> 
   <td colname="col2"> <p>Data Workbench服务器的通用名称（在其数字证书上分配）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Toolbar Icons（工具栏图标） </p> </td> 
   <td colname="col2"> <p>如果设置为 False，则会关闭工作站用户界面中的图标，而在工具栏中显示文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use Address File（使用地址文件） </p> </td> 
   <td colname="col2"> <p>指定地址文件中的任何设置是否覆盖 Address（地址）参数设置。选项为 true 或 false。如果设置为 true，则地址文件（如果存在）中的设置将覆盖 Address（地址）参数设置。默认值为 true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use SSL（使用 SSL） </p> </td> 
   <td colname="col2">指定SSL是否用于Data Workbench服务器和 <span class="keyword"> 客户</span>. 选项为 true 或 false。默认值为 true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unhide All（全部取消隐藏） </p> </td> 
   <td colname="col2"> <p>可选。让您可以临时取消隐藏使用以下任一功能隐藏的所有量度、维度和过滤器： 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A"><span class="filepath">order.txt</span> 文件中的 [Exclusive]（[排除]）设置 </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306"><span class="filepath">order.txt</span> 文件中的 Hide（隐藏）选项 </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8"><span class="filepath">.metric</span>、<span class="filepath">.dim</span> 和 <span class="filepath">.filter</span> 文件中的 Show（显示）参数 </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC"><span class="filepath">Transformation.cfg</span> 文件中的 Hidden（隐藏）参数 </li> 
     </ul> </p> <p>有关这些方法的更多信息，请参阅 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> 隐藏菜单项</a>. </p> <p>选项为 true 或 false。默认值设置为 false。将此参数更改为 true 可以临时将隐藏的量度、维度和过滤器取消隐藏。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unlock（解锁） </p> </td> 
   <td colname="col2"> <p>可选。指定是否允许将锁定工作区解除锁定。选项为 true 和 false。True 表示允许您解除任何锁定工作区的锁定，而 false 则不允许。默认值为 false。有关锁定工作区的详细信息，请参阅 <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> 解锁工作区</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Update Software（更新软件） </p> </td> 
   <td colname="col2"> <p>可选。指定是否允许此操作 <span class="keyword"> the </span>客户端软件，由Data Workbench服务器更新。 选项为 true 或 false。默认值为 true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User Folder（用户文件夹） </p> </td> 
   <td colname="col2"> <p>可选。指定包含每个配置文件中任何工作区、量度、维度或配置文件本地副本的文件夹的名称和位置。默认设置为User\\，它指定Data Workbench安装目录中的User文件夹。 </p> <p>当两个用户共用同一台计算机时，更改此设置非常有用。为了适应两个用户，您可以指定一个让两位用户都具有访问权限的共享文件夹。 </p> </td> 
  </tr> 
 </tbody> 
</table>
