---
title: 迷你图和数据条（报表生成器和 SSRS）| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.sparklines.f1
- "10544"
ms.assetid: b287436b-fa48-4970-a1a7-1dbcb86e7411
caps.latest.revision: 9
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: beeecbb80ff375bdb13f2a91bff84dbb34a9a4f5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37181626"
---
# <a name="sparklines-and-data-bars-report-builder-and-ssrs"></a>迷你图和数据条（报表生成器和 SSRS）
  迷你图和数据条是较小的简单图表，它们可以在很小的空间中传递很多信息，并且常常与文本并排。 迷你图和数据条通常用于表和矩阵中。 其影响来自于将它们一起进行查看并且能够快速对它们进行相互比较，而不是单独查看它们。 这样可以便于看到离群值，即不像其他项那样执行的行。 尽管较小，但每个迷你图通常表示一段时间中的多个数据点。 数据条可表示多个数据点，但通常只说明一个。 每个迷你图通常展示单个序列。 不能将迷你图添加到表的详细信息组中。 因为迷你图显示聚合数据，所以它们必须处于与某一组相关联的单元中。 迷你图和数据条具有相同的基本图表元素类别、序列和值，但没有图例、轴线、标签或刻度线。  
  
 ![rs_SparklineExample](../media/rs-sparklineexample.gif "rs_SparklineExample")  
  
 若要快速开始使用迷你图，请参阅[教程：向报表添加迷你图（报表生成器）](../tutorial-add-a-sparkline-to-your-report-report-builder.md)和视频[如何：在表中创建迷你图](http://go.microsoft.com/fwlink/?LinkId=197092)以及[报表生成器中的迷你图、条形图和指示器](http://technet.microsoft.com/bi/video/ff877165)。  
  
> [!NOTE]  
>  您可以将迷你图和数据条连同它们的父表、矩阵或列表作为报表部件与报表分开发布。 [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="KindsofSparklines"></a> 迷你图的类型  
 您几乎可以像常规图表一样创建任意类型的迷你图。 一般情况下，不能生成三维迷你图。 您可以生成以下完整图表的迷你图版本：  
  
-   [柱形图（报表生成器和 SSRS）](charts-report-builder-and-ssrs.md)：基本柱形图、堆叠柱形图和百分比堆叠柱形图。  
  
-   [折线图（报表生成器和 SSRS）](line-charts-report-builder-and-ssrs.md)：除三维折线图之外的所有图。  
  
-   [分区图（报表生成器和 SSRS）](area-charts-report-builder-and-ssrs.md)：除三维分区图之外的所有图  
  
-   [饼图（报表生成器和 SSRS）](pie-charts-report-builder-and-ssrs.md)：圆环图（平面和三维均可），但不包括漏斗图和棱锥图之类的其他形状。  
  
-   [范围图（报表生成器和 SSRS）](range-charts-report-builder-and-ssrs.md)：股价图、K 线图、误差线和盒须图。  
  
##  <a name="DataBars"></a> 数据条  
 数据条通常表示单个数据点，尽管它们也可以像常规条形图一样表示多个数据点。 它们通常包含无类别的若干序列，或者具有序列分组。  
  
 ![rs_DataBars](../media/rs-databars.gif "rs_DataBars")  
  
 在此示例中使用堆积数据条，每个数据条（尽管只有一个）说明多个数据点。 例如，数据条的三种不同颜色可以表示三个优先级的任务，并且数据条的长度表示分配给每个人的任务的总数。 如果您改为生成这些百分比堆积数据条，则每个条都将填充单元，并且不同颜色将表示对于每个优先级占整体的百分比。  
  
 您可以生成以下完整图表的数据条版本：  
  
-   [条形图（报表生成器和 SSRS）](bar-charts-report-builder-and-ssrs.md)：基本条形图、堆叠条形图和百分比堆叠条形图。  
  
-   [柱形图（报表生成器和 SSRS）](charts-report-builder-and-ssrs.md)：基本柱形图、堆叠柱形图和百分比堆叠柱形图。 柱形图可以是迷你图或数据条。  
  
 ![用于“返回页首”链接的箭头图标](../../2014-toc/media/uparrow16x16.gif "用于“返回页首”链接的箭头图标")[返回页首](#BackToTop)  
  
##  <a name="AlignDatainTableMatrix"></a> 在表或矩阵中对齐迷你图数据  
 在您将一个迷你图插入到表或矩阵中时，将每个迷你图中的数据点与该列中其他迷你图的数据点对齐通常十分重要。 否则，很难比较不同行中的数据。 例如，为您的公司中的不同销售人员按月比较销售数据时，您需要对齐月份。 如果某个员工在四月外出，则该员工在该月可能会没有销售数据。 您想要看到该月的差距，并且看到后续月份的数据与其他员工的数据对齐。 为此，您可以对齐水平轴。 有关详细信息，请参阅[总计、聚合和内置集合的表达式作用域（报表生成器和 SSRS）](expression-scope-for-totals-aggregates-and-built-in-collections.md)中关于迷你图的部分，另请参阅[在表或矩阵中的图表中对齐数据（报表生成器和 SSRS）](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)。  
  
 同样，为了可以跨多行进行比较，数据还必须垂直对齐，这意味着一个迷你图或数据条中条和线条的高度必须相对于所有其他迷你图或数据条中条和线条的高度。 否则，将不能彼此比较这些行。  
  
 ![rs_SparklineAlignData](../media/rs-sparklinealigndata.gif "rs_SparklineAlignData")  
  
 在此图像中，柱形图显示每个雇员每天的销售额。 请注意，对于雇员没有销售额数据的那些天，该图留空并对齐后面的天。 这是一个水平对齐的示例。 还要注意的是，对于某些员工，每个条都比较短，并且没有条达到单元的顶部。 这是一个垂直对齐的示例；如果没有垂直对齐，则在没有较高的条的行中，短条将扩展以便填充单元的高度。  
  
 ![用于“返回页首”链接的箭头图标](../../2014-toc/media/uparrow16x16.gif "用于“返回页首”链接的箭头图标")[返回页首](#BackToTop)  
  
##  <a name="UnderstandScope"></a> 理解提供给迷你图或数据条的数据  
  在您向表或矩阵添加迷你图或数据条时，这称作在一个数据区域内“嵌套”另一个数据区域。 嵌套意味着提供给迷你图或数据条的数据由表或矩阵所基于的数据集控制，或者由将其放置于表或矩阵中的位置控制。 有关详细信息，请参阅[嵌套数据区域（报表生成器和 SSRS）](nested-data-regions-report-builder-and-ssrs.md)。  
  
##  <a name="ConvertSparklinetoChart"></a> 将迷你图或数据条转换为完整图表  
 因为迷你图和数据条只是一种图表，所以，在你决定想要具备整个图表功能时，可以通过右键单击图表并单击“转换为整个图表”，将迷你图或数据条转换为整个图表。 执行此操作时，将自动添加轴线、标签、刻度线和图例。  
  
> [!NOTE]  
>  通过一次单击不能将整个图表转换为迷你图或数据栏。 但是，只需通过删除不在迷你图和数据条中的所有图表元素，即可从完整图表生成迷你图或数据条。  
  
 ![用于“返回页首”链接的箭头图标](../../2014-toc/media/uparrow16x16.gif "用于“返回页首”链接的箭头图标")[返回页首](#BackToTop)  
  
##  <a name="HowTo"></a> 操作指南主题  
 [添加迷你图和数据条&#40;报表生成器和 SSRS&#41;](sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
 [表或矩阵中的图表中对齐数据&#40;报表生成器和 SSRS&#41;](align-the-data-in-a-chart-in-a-table-or-matrix-report-builder-and-ssrs.md)  
  
### <a name="other-how-to-topics-for-charts"></a>针对图表的其他操作指南主题  
 因为迷你图和数据条为图表类型，所以，您可能还会发现以下针对图表的操作指南主题既对您很有帮助，又颇具针对性：  
  
 [向报表添加图表&#40;报表生成器和 SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md)  
  
 [向图表添加空点&#40;报表生成器和 SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
 [添加或删除边距在图表中&#40;报表生成器和 SSRS&#41;](add-or-remove-margins-from-a-chart-report-builder-and-ssrs.md)  
  
 [更改图表类型&#40;报表生成器和 SSRS&#41;](change-a-chart-type-report-builder-and-ssrs.md)  
  
 [在图表中使用调色板定义颜色&#40;报表生成器和 SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md)  
  
 [在序列上显示工具提示（报表生成器和 SSRS）](show-tooltips-on-a-series-report-builder-and-ssrs.md)  
  
 [指定对数刻度&#40;报表生成器和 SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md)  
  
 [指定轴间隔&#40;报表生成器和 SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
 [对多个形状图指定一致的颜色（报表生成器和 SSRS）](shape-charts-report-builder-and-ssrs.md)  
  
## <a name="see-also"></a>请参阅  
 [图表（报表生成器和 SSRS）](charts-report-builder-and-ssrs.md)   
 [教程： 向报表添加迷你图&#40;报表生成器&#41;](../tutorial-add-a-sparkline-to-your-report-report-builder.md)   
 [迷你图、 条形图和指示器在报表生成器 （视频）](http://technet.microsoft.com/bi/video/ff877165)   
 [如何： 为表 （视频） 中创建迷你图](http://go.microsoft.com/fwlink/?LinkId=197092)  
  
  
