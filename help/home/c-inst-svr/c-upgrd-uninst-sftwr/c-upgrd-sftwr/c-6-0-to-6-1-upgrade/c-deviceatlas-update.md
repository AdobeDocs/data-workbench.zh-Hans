---
description: DeviceAtlas JSON 文件现在将与 DeviceAtlas.dll 和 DeviceAtlas64.dll 文件一起分配到 .bundle 文件（重命名的 .tar.gz）中。
title: DeviceAtlas 分配
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 94%

---

# DeviceAtlas 分配{#deviceatlas-distribution}

{{eol}}

DeviceAtlas JSON 文件现在将与 DeviceAtlas.dll 和 DeviceAtlas64.dll 文件一起分配到 .bundle 文件（重命名的 .tar.gz）中。

当管理员将 Insight Server 升级至版本 6.0 时，DeviceAtlas.bundle 文件将包含在“软件和文档”配置文件（softdocs 配置文件）的升级包中，该升级包位于：

[!DNL Server Packages > v6.00 > Server_6.00.zip]

将DeviceAtlas.bundle文件提取到 [!DNL Server\Lookups\DeviceAtlas].

DeviceAtlas.bundle 文件应被置于同步到 DPU 的目录中，与新 DeviceAtlasComponent 相对应的 DeviceAtlas.cfg 文件应被置于同步主服务器上的“Components for Processing Servers”目录中。当 DeviceAtlas.bundle 文件发生更改时，下一个 DeviceAtlas 查找调用将根据更新的 API 和/或 JSON 文件获得结果。

## 修改 Transformation.cfg 文件 {#section-394823348f5740028666e62e2bd42754}

DeviceAtlas 转换不再需要指定 JSON 文件的路径。Transformation.cfg 文件中定义的任何原有 DeviceAtlasTransformation 不应再包括指向混淆的 JSON 文件的 File（文件）参数。

此 Transformation.cfg 示例文件显示了应被删除以避免混淆的 File（文件）参数。（保留该参数不会造成损害，但是可能引发混淆，因为该参数将被忽略。）

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  
```

## 修改 DeviceAtlas.cfg 文件 {#section-10b43705a6c846fd9ec54ea6be249f88}

下面是 DeviceAtlas.cfg 文件中所需的 [!DNL component] 参数的示例。

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

从“配置文件同步”功能方面来看，该 DeviceAtlas.bundle 文件将被视作配置文件。此外，JSON 数据和 DLL 将用在“组件”级别，而不是单独的“转换”级别。

新的 DeviceAtlasComponent 会在启动时查找 .bundle 组合文件，将 JSON 文件反混淆到内存中，将文件提取到临时目录，并为运行的平台加载适当的 DLL。该组件还监控对捆绑文件的更改，并在发生更改后自动重新加载 DLL 和 .cfg 文件。

## 运行 DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

通过使用正确的配置，可以大大缩短转换所需的时间。可以将转换配置为仅针对每个会话的每个访客运行一次，以使 DeviceAtlas 加快该过程的速度。

**如果使用 Log Processing.cfg 进行部署**：

运行两次转换。

1. 只查找 [!DNL mobile id] 字段，然后
1. 创建条件以忽略 [!DNL mobile id] 然后查查其余的地方。

**如果使用 Transformation.cfg 进行部署**：

按照上面的日志处理中的步骤 1 进行部署，或者使用 cross-rows 以支持条件设置。

* Cross-Rows - 获取以前的会话键。然后，确定当前会话键是否与使用 cross-rows 找到的会话键不同。如果是这样，则仅为每个会话的一个记录运行 DeviceAtlas 转换。
