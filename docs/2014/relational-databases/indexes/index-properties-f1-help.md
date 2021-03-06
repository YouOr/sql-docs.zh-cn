---
title: 索引属性 F1 帮助 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: table-view-index
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.storage.f1
- sql12.swb.indexproperties.columns.f1
- sql12.swb.indexproperties.partitions.f1
- sql12.swb.indexproperties.general.f1
- sql12.swb.indexproperties.filter.f1
- sql12.swb.indexproperties.options.f1
- sql12.swb.indexproperties.spatial.f1
ms.assetid: 45efd81a-3796-4b04-b0cc-f3deec94c733
caps.latest.revision: 37
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 240c72d9facde541e2eefa25fd8ba6d456cb7133
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37290943"
---
# <a name="index-properties-f1-help"></a>“索引属性”对话框的 F1 帮助
  本主题中的这部分引用了使用 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 对话框提供的各种索引属性。  
  
 **本主题内容：**  
  
 [索引属性常规页](#General)  
  
 [用于为索引选择列的对话框](#Columns)  
  
 [索引属性存储页](#Storage)  
  
 [索引属性空间页](#Spatial)  
  
 [索引属性筛选器页](#Filter)  
  
##  <a name="General"></a> 索引属性常规页  
 使用“常规”页可以查看或修改所选表或视图的索引属性。 每一页上的选项可基于所选索引的类型更改。  
  
 **表名**  
 显示创建索引的表或视图的名称。 此字段为只读。 若要选择不同的表，请关闭“索引属性”页，选择适当的表，然后再次打开“索引属性”页。  
  
 不能对索引视图指定空间索引。 仅可为具有主键的表定义空间索引。 表中主键列的最大数目为 15。 复合主键列的每行大小限制在最多 895 个字节。  
  
 **索引名称**  
 显示索引的名称。 对于现有索引，此字段是只读的。 在创建新的索引时，请键入索引的名称。  
  
 **索引类型**  
 指示索引的类型。 对于新索引，指示在打开该对话框时所选索引的类型。 索引可以是： **“聚集”**、 **“非聚集”**、 **“主 XML”**、 **“辅助 XML”**、 **“空间”** \ **“聚集列存储索引”** 或 **“非聚集列存储”**。  
  
 **注意** 每个表只允许创建一个聚集索引。 每个表只允许创建一个 xVelocity 内存优化的列存储索引。  
  
 **唯一**  
 选中此复选框可使该索引成为唯一索引。 不允许两行具有相同的索引值。 默认情况下，此复选框处于未选中状态。 如果两行具有相同的值，在修改现有索引时，索引创建将会失败。 对于允许 NULL 的列，唯一索引允许为 NULL 值。  
  
 如果在 **“索引类型”** 字段中选择 **“空间”** ，则 **“唯一”** 复选框呈灰色。  
  
 **索引键列**  
 向 **“索引键列”** 网格中添加所需的列。 如果添加多列，则必须以所需的顺序列出这些列。 索引中的列顺序对索引的性能具有很大影响。  
  
 单个组合索引不能超过 16 列。 如果超过 16 列，请参阅本文末尾的“包含列”。  
  
 只能对包含空间数据类型（ *空间列*）的单个列定义空间索引。  
  
 **名称**  
 显示组成索引键的列的名称。  
  
 **排序顺序**  
 指定所选索引列的排序方向， **“升序”** 或 **“降序”**。  
  
> [!NOTE]  
>  如果索引类型为 **“主 XML”** 或 **“空间”**，则表中将不显示此列。  
  
 **数据类型**  
 显示数据类型信息。  
  
> [!NOTE]  
>  如果表列为计算列，则 **“数据类型”** 显示“计算列”。  
  
 **大小**  
 显示存储列数据类型所需的最大字节数。 对于空间列或 XML 列，显示零 (0)。  
  
 **标识**  
 显示组成索引键的列是否为标识列。  
  
 **允许 Null**  
 显示组成索引键的列是否允许在表或视图列中存储 Null 值。  
  
 **“添加”**  
 向索引键添加列。 从单击“添加”时出现的“从 \<table name> 选择列”对话框中选择表列。 对于空间索引，在选择一列后，该按钮将呈灰色。  
  
 **删除**  
 从组成索引键的列中删除所选列。  
  
 **上移**  
 在索引键网格中向上移动所选列。  
  
 **下移**  
 在索引键网格中向下移动所选列。  
  
 **列存储列**  
 单击“添加”可为列存储索引选择列。 有关列存储索引的限制，请参阅 [CREATE COLUMNSTORE INDEX (Transact-SQL)](/sql/t-sql/statements/create-columnstore-index-transact-sql)。  
  
 **包含列**  
 在非聚集索引中包含非键列。 使用此选项，您可以将列作为非键列添加到非聚集索引的叶级别中，从而跳过当前对索引键总大小的索引限制以及对构成索引键的最大列数的索引限制。 有关详细信息，请参阅 [创建带有包含列的索引](create-indexes-with-included-columns.md)。  
  
##  <a name="Columns"></a> 用于为索引选择列的对话框  
 在创建或修改索引时，使用此页可以向 **“索引属性常规”** 页中添加列。  
  
 **复选框**  
 选中复选框可添加列。  
  
 **名称**  
 列的名称。  
  
 **数据类型**  
 列的数据类型。  
  
 **字节**  
 列的大小（字节）。  
  
 **标识**  
 对于标识列显示 **“是”** ；如果该列不是标识列，则显示 **“否”** 。  
  
 **允许 Null 值**  
 如果表定义允许该列包含空值，则显示 **“是”** 。 如果表定义不允许该列包含 Null 值，则显示 **“否”** 。  
  
##  <a name="Storage"></a> 存储页选项  
 使用此页可查看或修改所选索引的文件组或分区方案属性。 仅显示与索引类型相关的选项。  
  
 **文件组**  
 在指定的文件组中存储索引。 该列表仅显示标准 (row) 文件组。 默认情况下，将在该列表中选择相应数据库的 PRIMARY 文件组。 有关详细信息，请参阅 [Database Files and Filegroups](../databases/database-files-and-filegroups.md)。  
  
 **Filestream 文件组**  
 指定 FILESTREAM 数据的文件组。 该列表仅显示 FILESTREAM 文件组。 默认情况下，将在该列表中选择 PRIMARY FILESTREAM 文件组。 有关详细信息，请参阅 [FILESTREAM (SQL Server)](../blob/filestream-sql-server.md)。  
  
 **分区方案**  
 在分区方案中存储索引。 单击 **“分区方案”** 可启用下面的网格。 默认情况下，将在该列表中选择用于存储表数据的分区方案。 在列表中选择其他分区方案将更新该网格中的信息。 有关详细信息，请参阅 [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md)。  
  
 如果数据库中没有分区方案，则分区方案选项不可用。  
  
 **Filestream 分区方案**  
 指定 FILESTREAM 数据的分区方案。 分区方案必须与 **“分区方案”** 选项中指定的方案对称。  
  
 如果表未分区，则该字段为空白。  
  
 **分区方案参数**  
 显示构成分区方案的列的名称。  
  
 **表列**  
 选择要映射到分区方案的表或视图。  
  
 **列数据类型**  
 显示有关列的数据类型信息。  
  
> [!NOTE]  
>  如果表列是计算列，则 **“列数据类型”** 显示为“计算列”。  
  
 **允许在移动索引时在线处理 DML 语句**  
 在索引操作过程中，允许用户访问基础表或聚集索引数据以及任何相关联的非聚集索引。 有关详细信息，请参阅 [Perform Index Operations Online](perform-index-operations-online.md)。  
  
> [!NOTE]  
>  此选项对 XML 索引不可用，或者如果索引为禁用的聚集索引，此选项也不可用。  
  
 **设置最大并行度**  
 限制执行并行计划时所使用的处理器数。 默认值为 0，表示使用实际可用的 CPU 数。 若将此值设置为 1，则取消生成并行计划；若将此值设置为大于 1 的数，则会限制单个查询执行使用的最多处理器数。 该选项仅在此对话框处于 **“重新生成”** 或 **“重新创建”** 状态时才可用。 有关详细信息，请参阅 [设置最大并行度选项以获取最佳性能](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md)。  
  
> [!NOTE]  
>  如果指定的值比可用 CPU 数大，则将使用实际的可用 CPU 数。  
  
##  <a name="Spatial"></a> 空间页索引选项  
 使用 **“空间”** 页，可以查看或指定空间属性的值。 有关详细信息，请参阅[空间数据 (SQL Server)](../spatial/spatial-data-sql-server.md)。  
  
### <a name="bounding-box"></a>边界框  
 “边界框”  为几何平面的顶级网格的周界。 边界框参数仅存在于几何图形网格分割中。 如果 **“分割方案”** 为 **“地理网格”**，这些参数将不可用。  
  
 面板将显示 **(*`X-min`*，*`Y-min`*)** 并 **(*`X-max`*，*`Y-max`* )** 的边界框坐标。 没有任何默认坐标值。 因此，在对 `geometry` 类型列创建新的空间索引时，必须指定坐标值。  
  
 `X-min`  
 边界框左下角的 X 坐标。  
  
 `Y-min`  
 边界框左下角的 Y 坐标。  
  
 `X-max`  
 边界框右上角的 X 坐标。  
  
 `Y-max`  
 边界框右上角的 Y 坐标。  
  
### <a name="general"></a>常规  
 **“分割方案”**  
 指示索引的分割方案。 支持的分割方案如下所示。  
  
 **几何图形网格**  
 指定几何图形网格分割方案，并将应用到的列`geometry`数据类型。  
  
 **几何自动网格**  
 在数据库兼容级别设置为 110 或更高时，将为 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 启用此选项。  
  
 **“地理网格”**  
 指定“地理网格”分割方案，它适用于 **geography** 数据类型的列。  
  
 **地理自动网格**  
 在数据库兼容级别设置为 110 或更高时，将为 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 启用此选项。  
  
 有关 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 如何实现分割的信息，请参阅[空间数据 (SQL Server)](../spatial/spatial-data-sql-server.md)。  
  
 **每个对象的单元格数**  
 指示可用于索引中单个空间对象的每个对象的分割单元格数。 该数字可以是 1 和 8192 之间（含 1 和 8192）的任何整数。 当数据库兼容级别设置为 110 或更高时，默认值为 16，并且对于 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 的早期版本为 8。  
  
 在顶级，如果对象包含的单元格多于 *n*指定的单元格，则索引操作将根据需要使用尽可能多的单元格来提供完整的顶级分割。 在这种情况下，对象收到的单元格数可能会大于指定的单元格数。 这种情况下，最大数量即为顶级网格创建的单元格数，这取决于 **“级别 1”** 的密度。  
  
### <a name="grids"></a>网格  
 此面板显示分割方案的每个级别上网格的密度。 密度可指定为 **“低”**、 **“中”** 或 **“高”** 三个级别。 默认值为 **“中”**。 **“低”** 表示 4x4 网格（16 个单元格）、 **“中”** 表示 8x8 网格（64 个单元格）而 **“高”** 表示 16x16 网格（256 个单元格）。 在选择 **“几何自动网格”** 或 **“地理自动网格”** 分割选项时，这些选项将不可用。  
  
 **级别 1**  
 第一级（顶级）网格的密度。  
  
 **级别 2**  
 第二级网格的密度。  
  
 **级别 3**  
 第三级网格的密度。  
  
 **级别 4**  
 第四级网格的密度。  
  
##  <a name="Filter"></a> 筛选器页  
 使用此页可以输入用于筛选索引的筛选器谓词。 有关详细信息，请参阅 [Create Filtered Indexes](create-filtered-indexes.md)。  
  
 **筛选表达式**  
 定义要将哪些数据行包含在筛选索引中。 例如： `StartDate > '20000101' AND EndDate IS NOT NULL'.`  
  
## <a name="see-also"></a>请参阅  
 [设置索引选项](set-index-options.md)   
 [INDEXPROPERTY (Transact-SQL)](/sql/t-sql/functions/indexproperty-transact-sql)   
 [sys.indexes (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
