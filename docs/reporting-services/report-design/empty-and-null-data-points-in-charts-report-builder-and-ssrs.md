---
title: "空和 Null 图 （报表生成器和 SSRS） 中的数据点 |Microsoft 文档"
ms.custom: 
ms.date: 05/30/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: faddd29d-4cc1-4c2c-8e29-d3d9918fe22a
caps.latest.revision: 10
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: cce213fa628dfed0d57304de308377520f60c3d0
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---

# <a name="empty-and-null-data-points-in-charts-report-builder-and-ssrs"></a>图表中的空和 Null 数据点（报表生成器和 SSRS）

  如果在 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 分页报表的图表中显示具有空值或 Null 值的字段，则图表外观可能与预期不符。 图表处理空值的方式会根据指定图表类型而改变：  
  
-   如果图表类型是线性图表类型（条形图、柱形图、散点图、折线图、面积图和范围图），则空值将在该图表中显示为空格或“空白”。 若要指示空点，则必须添加空点占位符。 有关详细信息，请参阅[添加空点添加到图表 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/add-empty-points-to-a-chart-report-builder-and-ssrs.md).  
  
-   如果图表类型是连续线性图表类型（面积图、条形图、柱形图、折线图和散点图），则空数据点将添加到该图表中以维护序列的连续性。  
  
-   如果图表类型是非线性图表类型（极坐标图、饼图、圆环图、漏斗图或棱锥图），则空值将不显示在该图表中。  
  
-   在形状图表类型中，会省略 Null 值。  
  
 具有空数据点的图表的示例可用于示例报表。 有关下载此示例报表和其他内容的详细信息，请参阅 [报表生成器和报表设计器示例报表](http://go.microsoft.com/fwlink/?LinkId=198283)。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="removing-empty-or-null-values"></a>删除空值或 Null 值  
 若要避免重要数据变得模糊，请考虑从数据集中删除空值。 若要筛选 Null 值，可以在查询中使用 NOT IS NULL 子句。 或者，也可以添加指定仅显示非 0 值的筛选表达式。 有关详细信息，请参阅[添加数据集筛选器、数据区域筛选器和组筛选器（报表生成器和 SSRS）](../../reporting-services/report-design/add-dataset-filters-data-region-filters-and-group-filters.md)。  
  
## <a name="fields-with-no-values-in-a-chart"></a>在图表中不含值的字段  
 如果在返回的结果集中某个字段不包含任何值，则图表会显示一个没有任何数据点的空图表，但是序列名称（通常是字段名称）会添加为图例项。  
  
 此行为不同于当报表已参数化并且所选值返回空结果集时，返回的数据集可能包含 0 行数据的情况。 如果数据集查询返回 0 行数据，在运行时系统会显示一条消息，指示没有可显示的数据。 你可以通过修改的报表中的 NoDataMessage 标题自定义此消息**属性**窗格。 有关详细信息，请参阅[报表的嵌入数据集和共享数据集（报表生成器和 SSRS）](../../reporting-services/report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)。  

## <a name="next-steps"></a>后续步骤

[图表](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)   
[设置图表格式](../../reporting-services/report-design/formatting-a-chart-report-builder-and-ssrs.md)   
[向报表添加图表](../../reporting-services/report-design/add-a-chart-to-a-report-report-builder-and-ssrs.md)   
[图表故障排除](../../reporting-services/report-design/troubleshoot-charts-report-builder-and-ssrs.md)  

更多问题？ [尝试的 Reporting Services 论坛](http://go.microsoft.com/fwlink/?LinkId=620231)