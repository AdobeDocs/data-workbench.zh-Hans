---
description: Data Workbench Geography支持所有地形图像层源的经纬度投影和通用横轴墨卡托(UTM)投影。
title: 指定地形图像的投影信息
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 65%

---

# 指定地形图像的投影信息{#specifying-projection-information-for-terrain-images}

Data Workbench Geography支持所有地形图像层源的经纬度投影和通用横轴墨卡托(UTM)投影。

原始的未投影位图和未投影的一般图像需要投影信息。您可以为包含嵌入投影信息的图像指定投影信息，尽管它通常并不需要此信息，因为投影的参数是由嵌入图像本身的大地数据自动确定的。以下部分提供了有关在 [!DNL Terrain Images.cfg] 文件中指定这些投影格式的详细信息。
