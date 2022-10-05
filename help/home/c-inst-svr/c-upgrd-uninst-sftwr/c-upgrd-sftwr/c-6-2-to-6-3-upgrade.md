---
description: 升级Data Workbench6.3的服务器组件。
title: 从DWB服务器升级6.2到6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
exl-id: 5106d9a3-179a-49f1-915a-c03b36ed5257
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 56%

---

# DWB 服务器升级：从 6.2 到 6.3{#dwb-server-upgrade-to}

{{eol}}

升级Data Workbench6.3的服务器组件。

**升级服务器**

如果您的自定义用户档案优先于 [!DNL Base] 包中，则需要更新这些自定义文件：

* **更新Meta.cfg文件** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]为文件系统单元（FSU服务器）设置更新的密码加密，并为名称值对转换添加条目以利用 [查询字符串分组](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. 打开 FSU 中的 [!DNL meta.cfg] 文件。
   1. 更改的数据类型 **[!UICONTROL Proxy Password]** 从&quot; [!DNL string"] &quot; [!DNL EncryptedString]“ *工作站配置* 中。

      ```
        Proxy User Name = string:
        Proxy Password = EncryptedString:   (
        from Proxy Password = String)
        Use Address File = bool: true
      ```

   1. 为启用新的名称值对转换而添加新条目：*BuildNameValuePair* 和 *ExtractNameValuePairs*。

      打开工作区，右键单击&#x200B;**管理员** > **配置文件管理器**。

      在&#x200B;**上下文**&#x200B;的下方，单击&#x200B;**基本**&#x200B;列中的 **meta.cfg** 文件，然后单击&#x200B;**制作本地副本**。在“用户”表格列中，选择&#x200B;**打开** > **在工作站中**。

      ![](assets/meta_cfg.png)

      * 在新窗口中，单击&#x200B;**元数据**，然后添加可接受的子模板。

         ![](assets/meta_cfg_child.png)

      * 打开&#x200B;**转换**，并添加新模板。

         ![](assets/meta_cfg_template.png)

* **为实现快速合并的改进而进行更新**。为下列配置文件添加参数或更改值，以便在转换过程中利用 Data Workbench 中的速度改进。

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:
          URI = string: /SourceListServer/
          Listing Interval = int: 10 (
      <new>)
      ```

   * **Disk Files.cfg** (在 [!DNL E:\Server\Components] 和 [!DNL E:\Server\Components for Processing Servers])

      ```
      Disk Cache Size (MB) = double: 1024
      <(from double: 256)>
      Disk Cache Read Limit (MB) = double: 768
      <(new)>
      ```

   * **Log Processing Mode.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

      ```
      <(changed)
      Batch Bytes = int: 268435456
      Cloud Bytes = int: 268435456
      Real Time FIFO Bytes = int: 268435456
      ```

      ```
      (
      <new>)
      Cache Bytes = int: 32000000
      Fast Input Decision Ratio = double: 200
      Fast Input FIFO Bytes = int: 268435456
      FIFO Hash Mask = int: 16383
      Fast Merge Buffer Bytes = int: 536870912
      Slow Merge Buffer Bytes = int: 268435456
      Fast Merge Fan In = int: 64
      Key Cache Size Logarithm = int: 21
      Max Seeks = int: 512
      Output Old Buffer Bytes = int: 536870912
      Overflow FIFO Bytes = int: 67108864
      Paused = bool: false
      ```
   >[!NOTE]
   >
   >若要利用快速合并改进，请确保您的每个 DPU 至少有 8 GB 的 RAM。

* **具有 DWB 集成更新的 Adobe Target**。新的导出文件， [!DNL ExportIntegration.exe]，替换现有 [!DNL TnTSend.exe] 文件(`E:\Server\Scripts\TnTSend.exe`)。 这个新导出的文件同时支持 [Adobe Target](https://www.adobe.com/marketing/target.html) 与最新主营销配置文件 (MMP) 和 [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html) 的集成和协同。

   您将需要为 Adobe Target 导出更新以下命令。

   `Command = string: TnTSend.exe`

   更改为

   ```
   <filepath>
   Command = string: ExportIntegration.exe
   </filepath>
   ```

   >[!NOTE]
   >
   >这将仅影响在版本6.3之前创建的导出。

   您还可以尝试下列操作以使用旧的导出过程：

   * 在工作站中创建新的 Test&amp;Target 导出。
   * 修改旧的Test &amp; Target导出，该导出位于 [!DNL Server/Profiles/`<your profile>`/导出。]

* **更新 Adobe SC 配置文件。** 对 [!DNL Exclude Hit.cfg] 文件要求在关联的 [!DNL Decoding Instructions.cfg] 文件。

   >[!NOTE]
   >
   >如果您的AdobeSC配置文件包含自定义 [!DNL Decoding Instructions.cfg] 文件，您将需要 [!DNL DelimitedDecoder] 参数添加到自定义文件。

   ```
   0 = DelimitedDecoder:
      Delimiter = string: \t
      Fields = vector: x items
      …
         5 = string:
   Changed to:
   
   5 = string: x-hit_source
   ```

   通过添加 [!DNL DelimitedDecoder] 字段，您可以利用功能更新，并避免可能由这些更新导致的日志处理问题。
