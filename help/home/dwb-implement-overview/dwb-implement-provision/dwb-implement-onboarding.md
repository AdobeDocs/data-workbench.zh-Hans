---
description: 按照以下步骤启动Adobe Data Workbench(DWB)的入门过程，它是Adobe Analytics Premium(AAP)的一个组件。
title: DWB Managed Services的基本入门说明
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# DWB Managed Services的基本入门说明{#basic-onboarding-instructions-for-dwb-managed-services}

按照以下步骤启动Adobe Data Workbench(DWB)的入门过程，它是Adobe Analytics Premium(AAP)的一个组件。

这些入门说明适用于使用Adobe托管服务（无需咨询服务）实施单一报表包的Data Workbench的客户。 如果您是实施DWB的新AAP客户，Adobe入门培训团队将是您的初始联系人。 如果从Adobe Analytics标准版或从DWB的早期版本升级，Adobe客户成功经理将为您提供协助。

## 入门信息：我们需要您提供什么 {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe将联系您：

* 识别DWB的主用户，以在网络目录上为该用户生成证书。 主要用户还将充当与Adobe客户关怀部门进行互动的指点人员。
* 确定要加载到DWB的报表包。

然后，Adobe数字营销团队将利用您的信息创建DWB的配置文件、设置帐户和传送配置文件。

**Adobe入门任务**

* Adobe客户关怀团队创建DWB授权帐户。 Adobe客户关怀部门为主用户生成DWB证书。
* Adobe客户关怀部门将主用户定义为“受支持用户”，即为受支持呼叫和问题解决确定的人。
* Adobe客户关怀部门将软件包加载到DWB许可证和软件门户（SoftDocs/软件和文档配置文件），以下载到您的组织。
* Adobe TechOps团队为DWB准备生产和开发环境及其配置文件（按合同）。
* Adobe TechOps团队配置数据馈送和配置文件管理脚本。
* Adobe TechOps团队创建DWB配置文件(Insight.cfg)并将其发送到Adobe入门培训团队，该团队负责与您的组织关联的入门培训任务。

自定义数据馈送并生成凭据、证书和配置文件配置后，Adobe客户关怀团队将发送您的配置文件和凭据，以采取下一步行动。

## 访问自定义安装文件 {#section-26962bf57fef435dbd1c5486d4b6f688}

您将从Adobe客户关怀部门收到这些安装文件，以便在您的客户端计算机上安装DWB工作站。

* 您的自定义DWB配置文件(Insight.cfg)

   客户端计算机上的此配置文件将包括与受管DWB服务器的连接。

* 用于授权许可门户的登录凭据，用于下载DWB设置向导和必需的证书（.pem文件）以及主用户的名称。

**下载其他安装文件**

1. 浏览到：license.visualsciences.com下载许可证证书和DWB设置向导可执行文件。
1. 输入您的组织（帐户名）、主要用户的名称和您从Adobe客户关怀部门收到的密码，然后单击登录。

   >[!NOTE]
   >
   >此时，您的浏览器可能会提示您提供数字证书。 如果确实如此，请单击“取消”关闭对话框。

1. 在“下载”部分找到为Adobe Data Workbench(`<PrimaryUser>`.pem)实例颁发的证书并下载。
1. 在“下载”部分找到“标准客户端安装程序”，下载DWB设置向导(InsightSetup-x.xx.exe文件)。
1. 从Adobe客户服务中心接收并下载文件后，运行DWB设置向导，将工作站软件安装到您的客户端计算机。

>[!NOTE]
DWB设置向导将引导您完成DWB客户端工作站的安装，并帮助找到要放入所需文件夹中的Insight.cfg和 `<PrimaryUser>`.pem文件。 Insight.cfg文件驻留在已安装的客户端工作站中的Insight.exe文件中。 该 `<PrimaryUser>`.pem文件位于Certificates文件夹中，并带有trust_ca_cert.pem文件。 DWB必须提供所有证书和配置文件才能正常工作。

有关其他信息，请参阅 [DWB设置向导](https://docs.adobe.com/content/help/en/data-workbench/using/install/workstation-setup/install-setup.html)。

## 连接到DWB服务器 {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

您的受控服务器在Adobe客户关怀部门向您发送的Insight.cfg文件中标识，并驻留在您的客户端工作站上。 Adobe TechOps将设置您的服务器，Adobe客户关怀部门将在将这些托管服务器和配置文件的引用添加到Insight.cfg文件中，然后再将其发送给您。 （将完成DWB设置向导文档步骤12中的配置与服务器的连接。）

>[!NOTE]
在DWB客户端工作站上的工作站配置工作区中，您将能够看到连接的服务器和配置文件。

**Adobe Managed Services**

· Adobe技术运营部门管理包括网络、数据中心、服务器和存储在内的基础架构。 对于需要TechOps操作的警报，基础架构监控和对警报的响应是全天候的。 对于其他警报，TechOps将通知Adobe客户关怀团队与您协调。

· Adobe TechOps将为托管服务器执行维护和固件更新。 对于导致停机的维护，您至少提前两周收到客户关怀部门的维护窗口通知。 Adobe TechOps将尽快满足即时需求。 通知将取决于紧急程度，并在计划确定后予以解决。

· Adobe TechOps会设置一个计划任务以自动管理数据。 分析源数据将移入DWB，以便从每晚21:00报告包时间开始进行处理和转换。

· Adobe TechOps将在必要时处理其他Adobe Managed Services，包括数据备份、FTP帐户、数据归档和数据传输。

· Adobe TechOps将配置主生产群集以包含三个月的滚动数据，以便每月重置和重新处理。 对代码（地理位置、DeviceAtlas、标准分类）的更新也将作为重新处理任务的一部分进行。 默认情况下，该任务在每个月的第一个星期五运行。 如有必要，客户关怀团队可以修改计划。

有关其他信息，请与 [Adobe客户关怀联系](https://helpx.adobe.com/support/programs/enterprise-support-terms.html)。
