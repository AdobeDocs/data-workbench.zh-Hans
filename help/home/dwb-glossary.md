---
description: Data Workbench 术语表
title: Data Workbench 术语表
uuid: 1000c43d-383c-442d-bd09-de4f286ded31
exl-id: 29d6560a-0394-4031-8152-20f7ea0de00b
source-git-commit: e355e8df64f7d6f0c3900ba51b55b6cf509f0751
workflow-type: tm+mt
source-wordcount: '4201'
ht-degree: 60%

---

# Data Workbench 术语表{#data-workbench-glossary}

{{eol}}

**警报**:在Data Workbench中，当量度在指定时间范围内达到定义的阈值时自动触发的消息或报表。 例如，您可以创建一个警报，以便在 24 小时内的页面查看次数超过或低于指定数量时发出电子邮件。

**分析师**:执行分析、定义报表或以其他方式使用Data Workbench的个人。

**架构师**:确定如何捕获、处理和组织数据以进行分析和报告的个人。 此人员通常具备丰富的专业知识，可熟练配置 Adobe® Platform 以供分析师使用。

**条形图**:一种图表形式，它使用各种大小的矩形条来显示两个或多个项目之间的比较。

**基准**:作为基准点的测量或标准，其他测量或判断可依据此基准点。 在 Data Workbench 中，基准描绘了与选定内容（选定的子集）关联的值和未做出选择时显示的值之间的比较。

**基数**:集中的元素数。 Adobe 数据维度中的元素数量称为维度的基数。

**检查点**:为备份或恢复目的写入Adobe数据集副本的时间。 此术语还指在检查点操作期间写入的数据集。

**卡方检验**:用于确定偶然发生与预期事件或结果的观察偏差的概率的统计测试。 在 Data Workbench 中，卡方检验越接近 100%，纯偶然发生偏差的可能性越小。

**点击流**:非正式术语，指用户在浏览网站时请求的页面序列。 点击流信息可帮助网站所有者了解访客如何使用他们的网站，以及他们最常请求访问哪些页面。网站所有者可捕获其网站内的访客点击流，但无法捕获其网站外的点击流（除了使用第三方 Cookie 或页面标记的情况以外），因为这些请求都是由外部 Web 服务器记录的。

**颜色图例**:Data Workbench中的图例，用于显示所选量度的颜色渐变。 颜色图例允许按各种量度对可视化进行颜色编码。通过对可视化进行颜色编码，可以更轻松地发现异常、例外情况和趋势。

**颜色渐变**:在颜色图例中，用于表示量度可能值范围的颜色范围。 将颜色图例应用于可视化后，将会根据由颜色渐变表示的值对可视化中的图形元素（例如，条形图中的条形）进行颜色编码。

**公共键**:两个表格数据集中的行之间形成关系的通用变量。 例如，产品 ID 可充当库存管理系统中查询字符串变量表格和产品数据表格之间的公共键。

**置信度区间**:具有包含速率或趋势的指定概率的值范围。 80% (p-value = .20)、95% (p-value = .05) 和 99% (p-value = .01) 置信度区间是最常用的区间。（来源：`https://www.nci.nih.gov/statistics/glossary`）

**置信水平**:调查结果中的采样错误在指定范围内的可能性，通常以标准错误表示（例如，1个标准错误等于68%的可能性，2个标准错误等于95.4%的可能性）。 （来源：`https://www.magazine.org/research/3410.cfm`）

**转化图**:在Data Workbench中，一种可视化类型，其中根据“转化”量度的值在x轴上绘制元素。

**转化率**:在Data Workbench中，发生值事件的会话的百分比。 转化率的计算方法为：将发生值事件的会话数量除以会话总数量。

**关联**:两个随机变量之间线性关系强度的数值测量。 通常一起向上或向下移动的变量呈正关联，而总是向反方向移动的变量呈负关联。另请参阅“关联系数”。

**关联系数**:表示两个随机变量之间线性关系强度的数值。 另请参阅“关联”。

**可计数维度**:一个维度，其中维度包含的元素数可以离散计数。 可计数维度可以含有以下类型的子维度：可计数、数值、简单、多对多和非正规。

**CrossRows 转换**:在Data Workbench Server中，一种数据转换，用于将访客的多个事件记录（在不同时间生成）中的数据纳入计算中。

**交叉表**:在Data Workbench中，一种表格可视化，可显示与两个维度的交集关联的量度。

**多维数据集**:一种多维数据结构或一组数据单元，按数据的维度排列。 例如，电子表格体现了一个以行和列排列数据的二维阵列。在电子表格中，每一行或列都是一个维度。一个三维阵列可显示为一个立方体，其中每个维度均构成立方体的一个面，包括与该面平行的任何切面。更高维的阵列不含实际的隐喻，但是用户可按照他们对企业的设想使用这些阵列来组织数据。也称为超立方体、多维阵列或多维数据库。

**功能板**:创建用于查看而非交互的工作区。 功能板通过显示适用于特定管理者或运营者（负责监督一个或多个业务目标）的关键绩效指标，提供“大致”状态。另请参阅“工作区”。

**数据挖掘**:将数学过程集合无指导或交互式地应用于历史业务数据，以努力以关联和其他统计关系的形式找到洞察。

**数据子集**:一项功能，允许用户轻松选择数据集的子集，以用于在线或离线分析。 （数据子集是数据集中基于过滤器的一部分。）

**数据仓库**:一个数据库，用于支持组织中的决策。 Data Warehouse 通常包含大量面向主题的时变性和非易失性数据，这些数据的构建方式便于进行快速联机查询和管理式归纳。

**数据处理单元**:一种Data Workbench Server类型，用于处理、存储和提供来自Adobe数据集的数据。 DPU 可以选择存储包含源数据（数据集由这些数据构建而成）的 VSL 日志文件，还可以从 Data Workbench 服务器的文件服务器单元 (FSU) 接收数据。DPU 是一种 Data Workbench 服务器，通过它，Data Workbench 和 Report® 客户端可直接进行交互。

**数据集**:由Data Workbench Server加载和处理的数据。 数据集表示可出于分析、报告和警报目的而传输到 Data Workbench 或报表的数据。实际上，数据集存放在 temp.db 文件中。每个 Data Workbench 服务器计算机（或 Data Workbench 服务器聚类）均维护一个数据集。

**数据集数据**:在Data Workbench Server数据集中创建并存储的数据。 它包含准许在数据集中添加或创建的事件数据和集成数据。它还包含源于此类数据的任何信息，具体由定义该数据集的配置文件决定。通过使用相同或不同的配置文件重新处理事件和集成数据，可重新创建数据集数据。（配置文件是作为 Adobe 配置文件的一部分管理的系统文件。）

**数据集记录**:执行所有过滤和其他处理后，这些事件数据记录被允许进入Adobe数据集。 也称为已处理的日志条目。

**数据集架构**:Data Workbench中的一个可视化，用于显示支持当前选定配置文件的数据集架构。

**数据集存储空间**:在Adobe数据集中输入或创建的数据量（以字节为单位）。 此数据由 Data Workbench 服务器计算机上名为 Temp.db 的文件中的数据集存储。Temp.db 中的数据是瞬态的，可通过相应的配置文件重新处理源数据（例如事件数据和集成数据）来重新创建。

**解码器**:Data Workbench Server中的组件，可从各种源中读取事件数据，并生成用于生成数据集的数据。 解码器的输出可用作对 Data Workbench 服务器中任何“日志处理”功能的输入。解码器类型包括传感器解码器（从各种版本的传感器加载数据）、正则表达式解码器（从分隔的平面文件加载数据）和 ODBC 解码器（从 ODBC 数据源加载数据）。

**维度**:一组元素，在用户的感知中，所有元素都属于相似类型。 元素定义一组分组数据的类别。例如，元素“星期一”、“星期二”、“星期三”、“星期四”、“星期五”、“星期六”和“星期日”组成了“星期”维度。

**维度元素**:维度中的单个类别。 例如，“星期”维度包含单个元素“星期一”、“星期二”、“星期三”、“星期四”、“星期五”、“星期六”和“星期日”。

**维度图例**:在Data Workbench中，该图例列出了已在数据集中定义（或从中派生）的维度。 在可视化中做出选择后，维度图例会标识那些所含值与基准存在极大统计偏差的维度。

**从上向下钻取**:一种特定的分析技术，用户可以在从最汇总（上）到最详细（下）的数据级别之间导航。 例如，在查看北美地区的销售数据时，在区域维度中执行向下钻取操作可能会显示加拿大、美国和墨西哥。在加拿大中进一步向下钻取可能会显示多伦多、温哥华、蒙特利尔等。

**事件数据**:由传感器或其他方式（例如Web服务器日志文件）收集的数据，它构成对Data Workbench Server的主要输入。 每个事件数据记录均表示事件的交易记录或单个事件实例。

**扩展维度**:基于扩展数据的维度。 扩展数据是指构成有效事件数据记录的最低所需数据以外的任何数据。在捕获了原始事件时，可将扩展数据添加到事件数据记录中，或者，也可以从其他来源纳入扩展数据并将其作为集成数据添加到事件数据记录中。任何基于此额外数据的维度都被视为“扩展维度”。

**文件服务器单元 (FSU)**:一种Data Workbench Server类型，其功能仅用于从一个或多个传感器或中继服务器接收事件数据，并将数据提供给一个或多个Data Workbench Server数据处理单元(DPU)，以用于构建Adobe数据集。 FSU 可优化事件数据向 DPU 的传输，并且其速度远远快于普通文件服务器。使用 FSU，可以将日志文件存储在成本较低的存储硬件上来减少硬件成本，还可以将多个传感器指向一个 Data Workbench 服务器来降低管理复杂性。

**增量查询评估**:Data Workbench Server根据所有群体的预计随机样本为用户提供即时查询结果的专利流程。 利用该流程，服务器会逐步改善查询的准确度，因为它会考虑更多的数据，直到所有数据都被考虑在内并获得了确切计数为止。

**集成数据**:集成数据是来自公司数据库或查找文件的外部数据，您可以将这些数据与事件数据结合以创建数据集。 通常，您会使用集成数据来补充由传感器获取的事件数据。（从概念上讲，可以将使用集成数据视为用额外的信息列填充事件数据记录。）

**图例**:Data Workbench中的一个窗口，提供有关工作区中显示的可视化的说明性详细信息。 图例的类型包括颜色图例、维度图例和量度图例。与 Data Workbench 中的任何窗口一样，图例窗口也可通过报表生成和分发。

**折线图**:Data Workbench中的一种可视化类型，用于将指定维度的量度绘制为图表x轴上的连续点，然后将这些点与线条连接。 使用折线图，可以非常有效地对基于时间的维度可视化量度。

**日志条目条件**:一个条件，用于确定数据集中是否包含事件数据记录（日志条目）。 例如，日志条目条件可以指定只有与特定网站关联的事件数据记录才准许添加到数据集中。日志条目条件在 Data Workbench 服务器上的日志处理配置文件中指定。

**多对多Dimension**:在“Adobe平台”中，与父可计数维度具有多对多关系的维度。 多对多维度表示一组值，这些值对应其父维度的每个元素。例如，在网站中，“搜索短语”维度与其父维度，也就是“会话”维度具有多对多关系（即，一个会话可具有任意数量的搜索短语，而一个搜索短语也可具有任意数量的会话）。

**蒙版**:Data Workbench中的一项功能，允许分析人员临时隐藏他们不希望包含在分析中的元素。

**平均值**:一组数字的算术平均值。 数据的总和除以取样大小。

**中间值**:一个数字，用于将样本、群体或概率分布的最高半部分与最低半部分分开。 一半的人群将具有小于或等于中间值的值，而另一半的人群将具有大于或等于中间值的值。

**量度**:在Adobe中，一个命名的公式，用于描述如何从数据集中的数据计算定量值。 例如在网站中，“每个访客的会话数”量度表示用会话计数除以访客计数的公式。

**量度图例**:Data Workbench中的一个窗口，用于显示由活动配置文件定义的量度。 量度图例显示由数据集或当前选区计算而来的每个量度的值（如果选区在工作区中处于活动状态，则量度图例显示选定子集的值而不是整个数据集的值）。与 Data Workbench 中的任何窗口一样，量度图例也可通过报表生成和分发。

**量度工作表**:Data Workbench中的一个窗口，允许分析人员为数据集定义自己的量度。 量度工作表类似于一个电子表格。使用 Data Workbench 公式语法，分析师可以输入表达式来描述他们希望从数据集得出的数量值。例如，分析师可定义一个量度以显示从特定域查看某个页面的访客百分比。与常规量度一样，当某个选区在工作区中处于活动状态时，量度工作表中的公式将对选定子集进行运算。与 Data Workbench 中的任何窗口一样，量度工作表也可通过报表生成和分发。

**新访客条件**:此条件用于确定在向Data Workbench Server显示事件数据记录时是否创建了新的跟踪ID。

**节点**:将一个或多个离散项目分组到单个逻辑实体中。 在配置文件 (.cfg) 中，节点是包含相关参数的项目。另请参阅“参数”和“矢量”。在 Data Workbench 中，流程图上的节点表示一个页面或一组定义的页面。

**数值维度**:在“Adobe平台”中，具有有序数值且与父可计数维度具有一对多关系的维度。 通常，数值维度表示父维度元素的数值属性。数值维度通常用于定义“总和”量度。

**一对多关系**:两个数据维度之间的关系，其中一个维度中的单个元素与另一个维度中的一个或多个元素相关（或可以与这两个维度中的单个元素相关）。

**序数**:表示或表示序列中的数值顺序。 （来源：`https://wordnet.princeton.edu/perl/webwn?s=ordinal`）如果维度在 Data Workbench 中按自然顺序排序，则维度的元素会以它们在内部呈现的顺序显示。

**离群值**:在一组数据中，一个值与分布中的其他值相去甚远，该值的存在不能归因于偶然原因的随机组合。

**页面叠加**:Data Workbench中的一种可视化类型，可根据指定的量度对网页图像上的链接进行颜色编码。 您可以使用页面叠加可视化快速识别页面中的哪些链接最能吸引访客的注意（并将他们带到网站上的其他页面），哪些链接没有吸引力。您还可以使用页面叠加了解页面上的各种链接为您的网站生成的“值”（由值事件测量）。

**页面查看条件**:Data Workbench Server转换中的一个选项，允许根据事件记录的内容类型或实际内容将其包含或排除为页面查看。 例如，您可以使用此选项排除与不成功的 HTTP 请求（例如，生成 404 状态代码的请求）或返回特定内容类型的请求（例如，图像请求）有关的事件记录。如果“页面查看条件”选项没有过滤出 HTTP 事件记录，则该事件记录将在数据集中表示一次页面查看。

**路径浏览器可视化**:Data Workbench中的一种可视化类型，使分析师能够以交互方式探索访客会话中或访客会话中的一系列事件（如页面查看次数）。

**主服务器**:在Data Workbench Server群集中，Data Workbench Server用于协调客户端（如Data Workbench和Report）与群集中其他服务器之间的通信。 主服务器还可充当聚类的管理焦点。使用 Data Workbench 服务器的配置文件同步功能，管理员对主服务器所做的更改可自动传播到聚类中的其他服务器。主服务器是一个 Data Workbench 服务器 DPU。

**流程图**:Data Workbench中的一种可视化类型，使分析师能够了解网站上页面或节点之间的流量流量。 流程图描绘了有关特定页面的信息（例如查看了页面的会话数量），还描述了页面或节点间的流量额。

**处理服务器**:在Data Workbench Server群集中，由主服务器上的配置信息控制的Data Workbench Server。 处理服务器将事件数据处理到一个数据集中并响应来自客户端（例如 Data Workbench 和报表）的查询。在响应查询时，处理服务器会将执行查询的责任分给（“分区”）聚类中的多个服务器。当其他服务器完成其负责的查询部分后，处理服务器将合并（“取消分区”）它们的结果并将合并后的结果返回给客户端。

**配置文件**:一组配置文件，其中包含用于为特定分析目的创建数据集的规则。 配置文件还定义各个项目，例如量度、派生维度、工作区、报表、可视化和图例，以允许分析师与数据集进行交互并从中获取信息。通常可为网站构建配置文件（例如为 www.mysite.com 构建的配置文件），或者为特定类型的用户量身定制配置文件（例如“营销”用户配置文件或“财务”用户配置文件）。

**配置文件管理器**:Data Workbench中的一种交互式管理工具，它允许管理员或其他用户管理与配置文件关联的配置文件。

**正则表达式**:根据特定语法规则描述或匹配一组字符串的公式。 正则表达式（通常简写为 regexp、regex 或 regxp）用于基于特定模式搜索和处理文本正文。正则表达式符号源自早期 Unix 编辑器并在其他 Unix 实用工具（例如 vi 和 Perl）中得到广泛应用。如今，正则表达式受到许多文本编辑器、脚本语言和其他文本处理工具的支持。Data Workbench 服务器包含一个正则表达式引擎。

**维系图**:Data Workbench中的一种可视化类型，可根据“保留”量度的值在x轴上绘制元素。

**散点图**:Data Workbench中的一种可视化类型，可将双变量数据表示为图表上的点。 对于以图表表示的每个元素，散点图都具有两条数据。例如，由 10 个页面组成的集合的转化率和访客数量度散点图会导致在图中产生 10 个单独的点。

**选区**:Data Workbench中的一项功能，允许分析人员限制检索和显示的数据集，以便进行报告或分析。 通过单击一个或多个维度中显示的元素，能够以交互方式在 Data Workbench 内进行选择（左键单击可选择元素，右键单击可取消选择元素）。通过定义在指定维度内选择某些元素的过滤器，也可进行选择。

**简单维度**:在Adobe平台中，与父可计数维度具有一对多关系的维度。 例如，“访客反向链接”是一种简单维度，其父维度是可计数维度“访客”。一个访客只有一个访客反向链接。但是，一个访客反向链接可以有多个访客（即，一个访客反向链接可以与多个访客关联）。

**平滑**:线形图中跨多个点的曲线的数学推断，用于说明相对稀疏的数据点上更有意义的趋势线。

**来源**:在Data Workbench Server上，包含可用于创建数据集的事件数据的资源。 Adobe 解码器可查找事件数据的来源以进行解码，从而供 Data Workbench 服务器使用。

**源数据**:在Data Workbench Server上，作为其解码器之一的输入的数据。 源数据可以输入到以下解码器：传感器解码器（从各种版本的传感器加载源数据）、正则表达式解码器（从分隔的平面文件加载源数据）和 ODBC 解码器（从 ODBC 数据源加载源数据）。

**表格图**:Data Workbench中的一种可视化类型，可以以表格格式显示数据。 表格图中的量度值能够以数值方式或条形格式表示。

**时间系列**:一个图表，显示给定属性或值随时间的变化情况。

**跟踪ID**:唯一区分Adobe数据集中正在分析的主要实体的标识符。 跟踪 ID 可以从各种来源构建，包括来自 Web 客户端 Cookie 的唯一 ID、IP 号码和用户代理哈希，或 x.509 名称。尽管这些是跟踪 ID 的一些常见来源，但您也可以使用任意值，只要该值能够唯一标识填充数据集内访客维度的实体即可。

**转换**:使用一些数学运算来更改变量值的方法。 例如，在 Data Workbench 服务器中，分析师可以使用拆分转换将查询字符串中的名称-值对划分到单个变量中。

**二维条形图**:Data Workbench中的一种可视化类型，可在三维图形视图中同时显示两个维度和最多两个量度。

**值图例**:Data Workbench中的一个窗口，允许分析人员将货币值与选定事件关联，并在数据集中选定事件的所有实例都汇总该货币值时查看结果。

**访客**:数据集中用于标识生成事件的实体的维度。 访客维度的每个成员均由一个唯一跟踪 ID 来标识。例如，在网站中，跟踪 ID 通常来源于客户端 Cookie 内的唯一 ID。在电话中，跟踪 ID 可能是来电者的电话号码。

**访客反向链接**:访客在Adobe数据集的时间范围内的第一个HTTP反向链接。

**访客拆分**:Data Workbench Server中的一项功能，允许具有大量事件数据的访客在两个跟踪ID之间进行拆分。 当访客超过配置的每访客最大事件数量（设置的一个参数，用于确保正确的系统性能）时，可以使用访客拆分来防止从数据集中过滤事件数据。尽管访客拆分会人为增加数据集中的访客数量，但它并不会夸大事件记录的总数，从而确保可计数事件（例如页面查看次数、预订次数）的总数保持准确。

**VSL**: 日志文件. 一种文件类型，Data Workbench 服务器可在其中存储它们从传感器接收的事件数据。VSL 文件是经过压缩的，但可使用数据传输功能以未压缩的形式输出。VSL 是日志文件的文件扩展名。

**假设分析**:一种分析类型，用于通过观察对数据模型中其他数据所做的更改对数据模型中的其他数据产生的影响，来了解更改数据模型中某些变量的后果。

**工作区**:在Data Workbench中，工作区是用于特定分析和可视化任务的容器。 工作区可以包含多个可视化，所有可视化都针对一组通用的数据执行操作（即，工作区中的所有可视化都呈现相同的查询结果集）。当分析师在一个可视化中执行子设置或过滤操作时，会在整个工作区中反映所选的子集。

**工作台**:Data Workbench用户界面中的“主页”区域，用于组织和访问您的所有工作区和报表。 它还允许您创建新的工作区和报表，并将新建和更新后的工作区和报表保存到 Data Workbench 服务器，以便使用相同配置文件的其他人员也能访问这些工作区和报表。