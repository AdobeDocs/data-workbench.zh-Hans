---
description: 按照以下步骤开始AdobeData Workbench(DWB)(Adobe Analytics Premium(AAP)的一个组件)的载入流程。
title: DWB Managed Services 的基本入门说明
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
exl-id: 49fb6afe-b417-4554-9238-fd6381c00029
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# DWB Managed Services 的基本入门说明{#basic-onboarding-instructions-for-dwb-managed-services}

按照以下步骤开始AdobeData Workbench(DWB)(Adobe Analytics Premium(AAP)的一个组件)的载入流程。

这些入门说明适用于使用Adobe托管服务在单个报表包中实施Data Workbench的客户，而无需咨询服务。 如果您是实施DWB的新AAPAdobe，则客户入门团队将是您的初始联系人。 如果从Adobe Analytics标准或更早版本的DWB升级，Adobe客户成功经理将为您提供帮助。

## 入门信息：我们需要您的 {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe将联系您，以：

* 识别DWB的主用户，以在网络目录上专门为该用户生成证书。 主要用户还将充当与Adobe客户关怀团队进行交互的指点人员。
* 确定要加载到DWB中的报表包。

然后，Adobe数字营销团队将获取您的信息，以创建用户档案、设置帐户并交付DWB的配置文件。

**Adobe载入任务**

* Adobe客户关怀团队创建DWB授权帐户。 Adobe客户关怀团队为主用户生成DWB证书。
* Adobe客户关怀团队将主用户定义为“受支持用户”，即为受支持呼叫和问题解决而识别的人员。
* Adobe客户关怀团队将软件包加载到DWB许可证和软件门户（SoftDocs/软件和文档配置文件），然后将其下载到您的组织。
* Adobe技术运营团队为DWB准备生产和开发环境及其配置文件（按合同）。
* Adobe技术运营团队配置数据馈送和配置文件管理脚本。
* Adobe技术运营团队创建DWB配置文件(Insight.cfg)，并将其发送给负责与贵组织关联的入门任务的Adobe载入团队。

自定义数据馈送并生成凭据、证书和配置文件配置后，Adobe客户关怀团队将发送您的配置文件和凭据，以执行下一步。

## 访问自定义安装文件 {#section-26962bf57fef435dbd1c5486d4b6f688}

您将从Adobe客户关怀团队收到这些设置文件，以在客户端计算机上安装DWB工作站。

* 您的自定义DWB配置文件(Insight.cfg)

   客户端计算机上的此配置文件将包含与托管DWB服务器的连接。

* 许可门户的登录凭据，用于下载DWB设置向导和必需的证书（.pem文件），以及主用户的名称。

**下载其他设置文件**

1. 浏览到：license.visualsciences.com下载许可证证书和DWB安装向导可执行文件。
1. 输入您的组织（帐户名称）、主要用户的名称以及您从Adobe客户关怀部门收到的密码，然后单击登录。

   >[!NOTE]
   >
   >此时，您的浏览器可能会提示您提供数字证书。如果是这样，请单击“取消”关闭该对话框。

1. 在“下载”部分中找到为AdobeData Workbench实例(`<PrimaryUser>`.pem)颁发的证书并下载。
1. 在“下载”部分中找到标准客户端安装程序，以下载DWB安装向导(InsightSetup-x.xx.exe文件)。
1. 从Adobe客户关怀团队接收和下载文件后，运行DWB安装向导，将工作站软件安装到客户端计算机。

>[!NOTE]
DWB安装向导将指导您完成DWB客户端工作站的安装，并帮助您找到要放入所需文件夹中的Insight.cfg和`<PrimaryUser>`.pem文件。 Insight.cfg文件与Insight.exe文件一起驻留在已安装的客户端工作站中。 `<PrimaryUser>`.pem文件位于Certificates文件夹中，并带有trust_ca_cert.pem文件。 DWB必须存在所有证书和配置文件才能正常运行。

有关其他信息，请参阅[DWB设置向导](https://experienceleague.adobe.com/docs/data-workbench/using/install/workstation-setup/install-setup.html)。

## 与DWB服务器的连接 {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

您的托管服务器在您从Adobe客户关怀团队收到的Insight.cfg文件中进行标识，并位于您的客户端工作站上。 Adobe技术运营团队将设置您的服务器，Adobe客户关怀团队将在将这些托管服务器和配置文件的引用添加到Insight.cfg文件中之后，再将其发送给您。 （将完成DWB设置向导文档步骤12中的配置与服务器的连接。）

>[!NOTE]
在DWB客户端工作站的工作站配置工作区中，您将能够看到连接的服务器和配置文件。

**Adobe Managed Services**

·Adobe技术运营管理基础架构，包括网络、数据中心、服务器和存储。 对于需要TechOps操作的警报，基础架构监控和对警报的响应是全天候的。 对于其他警报，技术运营部门将通知Adobe客户关怀部门与您进行协调。

·AdobeTechOps将为您的托管服务器执行维护和固件更新。 对于导致停机的维护，您将至少提前两周收到客户关怀团队的维护时间通知。 AdobeTechOps将尽快满足即时需求。 通知将依紧急情况而定，并在计划知晓后得到解决。

·AdobeTechOps设置计划任务以自动管理数据。 从报表包时间的21:00开始，分析信息源数据会移至DWB中，以便每天晚上进行处理和转换。

·Adobe技术运营将在必要时处理其他Adobe托管服务，包括数据备份、FTP帐户、数据存档和数据传输。

·Adobe技术运营将配置主生产群集以包含三个月的滚动数据，以便每月重置和重新处理。 在重新处理任务中，还将对查找(Geography、DeviceAtlas、Standard Classifications)进行更新。 默认情况下，该任务在每月的第一个星期五运行。 如有必要，客户关怀团队可以修改计划。

有关其他信息，请联系[Adobe客户关怀](https://helpx.adobe.com/support/programs/enterprise-support-terms.html)。
