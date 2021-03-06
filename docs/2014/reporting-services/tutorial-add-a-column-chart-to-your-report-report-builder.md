---
title: 教程：向报表添加柱形图（报表生成器）| Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 63480059-b7b9-44b5-9d7f-91780db708b6
caps.latest.revision: 10
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: cc295fcd58d3e7609989f35a382e780614e9d7a3
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37161898"
---
# <a name="tutorial-add-a-column-chart-to-your-report-report-builder"></a>教程：向报表添加柱形图（报表生成器）
  柱形图将序列显示为一组按类别分组的垂直图条。 柱形图可能在以下方面十分有用：  
  
-   显示一段时间内数据的更改。  
  
-   比较多个序列的相对值。  
  
-   显示移动平均线，以显示趋势。  
  
 下图显示了将创建的带有移动平均线的柱形图。  
  
 ![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")  
  
##  <a name="BackToTop"></a> 您将学习  
 在本教程中，您将学习如何执行下列操作：  
  
1.  [使用图表向导创建图表](#Chart)  
  
2.  [选择图表类型](#ChartType)  
  
3.  [格式和标签的水平轴](#Horizontal)  
  
4.  [移动图例](#Legend)  
  
5.  [设置图表的标题](#ChartTitle)  
  
6.  [格式和标签的垂直轴](#Vertical)  
  
7.  [添加移动平均线](#Average)  
  
8.  [添加报表标题](#Title)  
  
9. [保存报表](#Save)  
  
> [!NOTE]  
>  在本教程中，将向导的多个步骤合并为一个过程。 有关如何浏览到报表服务器、选择数据源和创建数据集的分步说明，请参阅本系列中的第一个教程：[教程：创建基本表报表（报表生成器）](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md)。  
  
 本教程的预计学时：15 分钟。  
  
## <a name="requirements"></a>要求  
 有关要求的信息，请参阅[教程先决条件（报表生成器）](../reporting-services/report-builder-tutorials.md)。  
  
##  <a name="Chart"></a> 1.使用图表向导创建图表报表  
 从**Getting Started**对话框，请使用图表向导创建嵌入数据集，选择共享的数据源，并创建柱形图。  
  
> [!NOTE]  
>  在本教程中，由于查询包含了数据值，因此它不需要外部数据源。 这样，查询就会非常长。 在业务环境中，查询不会包含数据。 本教程中的查询仅供学习使用。  
  
#### <a name="to-create-a-new-chart-report"></a>创建新的图表报表  
  
1.  单击 **“开始”**，依次指向 **“程序”**、 **Microsoft SQL Server 2012 Report Builder**，再单击 **“报表生成器”**。  
  
     此时将显示 **“入门”** 对话框。  
  
    > [!NOTE]  
    >  如果**Getting Started**对话框不会出现，从**报表生成器**按钮，再单击**新建**。  
  
2.  在左窗格中，确认已选中 **“新建报表”** 。  
  
3.  在右窗格中，单击“图表向导”。  
  
4.  在“选择数据集”页上，单击“创建数据集”，然后单击“下一步”。  
  
5.  在“选择数据源的连接”页中，选择现有数据源或浏览到报表服务器并选择一个数据源，然后单击“下一步”。 您可能需要输入用户名和密码。  
  
    > [!NOTE]  
    >  只要您具有足够的权限，则选择哪一个数据源并不重要。 您将不会从数据源中获取数据。 有关详细信息，请参阅[获取数据连接的备选方式（报表生成器）](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md)。  
  
6.  在“设计查询”页上，单击“编辑为文本”。  
  
7.  将以下查询粘贴到查询窗格中：  
  
    ```  
    SELECT CAST('2009-01-01' AS date) AS SalesDate, CAST(54995.21 AS money) AS Sales  
    UNION SELECT CAST('2009-01-05' AS date) AS SalesDate, CAST(64499.04 AS money) AS Sales  
    UNION SELECT CAST('2009-02-11' AS date) AS SalesDate, CAST(37821.79 AS money) AS Sales  
    UNION SELECT CAST('2009-03-18' AS date) AS SalesDate, CAST(53633.08 AS money) AS Sales  
    UNION SELECT CAST('2009-04-23' AS date) AS SalesDate, CAST(24019.3 AS money) AS Sales  
    UNION SELECT CAST('2009-05-01' AS date) AS SalesDate, CAST(93245.5 AS money) AS Sales  
    UNION SELECT CAST('2009-06-06' AS date) AS SalesDate, CAST(55288.0 AS money) AS Sales  
    UNION SELECT CAST('2009-06-16' AS date) AS SalesDate, CAST(68733.5 AS money) AS Sales  
    UNION SELECT CAST('2009-07-16' AS date) AS SalesDate, CAST(24750.85 AS money) AS Sales  
    UNION SELECT CAST('2009-08-23' AS date) AS SalesDate, CAST(43452.3 AS money) AS Sales  
    UNION SELECT CAST('2009-09-24' AS date) AS SalesDate, CAST(58656. AS money) AS Sales  
    UNION SELECT CAST('2009-10-15' AS date) AS SalesDate, CAST(44583. AS money) AS Sales  
    UNION SELECT CAST('2009-11-21' AS date) AS SalesDate, CAST(81568. AS money) AS Sales  
    UNION SELECT CAST('2009-12-15' AS date) AS SalesDate, CAST(45973. AS money) AS Sales  
    UNION SELECT CAST('2009-12-26' AS date) AS SalesDate, CAST(96357. AS money) AS Sales  
    UNION SELECT CAST('2009-12-31' AS date) AS SalesDate, CAST(81946. AS money) AS Sales  
    ```  
  
8.  （可选）单击“运行”按钮 (**!**)，查看要用于图表的数据。  
  
9. 单击“下一步” 。  
  
##  <a name="ChartType"></a> 2.选择图表类型  
 可以从各种预定义的图表类型中进行选择。  
  
#### <a name="to-add-a-column-chart"></a>添加柱形图  
  
1.  在“选择图表类型”页上，柱形图为默认图表类型。 单击“下一步” 。  
  
2.  在“排列图表字段”页上，将 SalesDate 字段拖到“类别”中。 “类别”显示在水平轴上。  
  
3.  将 Sales 字段拖到“值”中。 “值”框显示 Sum(Sales)，因为销售总计值之和是对每个日期的合计。 “值”显示在垂直轴上。  
  
4.  单击“下一步” 。  
  
5.  上**选择一种样式**页上，在样式中，选择一种样式。  
  
     样式指定字形、颜色集和边框样式。 选择样式时，“预览”窗格将显示具有该样式的图表的示例。  
  
6.  单击 **“完成”**。  
  
     图表将添加到设计图面中。  
  
7.  单击图表以显示图表控点。 拖动该图表的右下角以扩大该图表。 请注意，报表设计图面的大小将增大以容纳图表。  
  
8.  单击 **“运行”** 以预览报表。  
  
##  <a name="Horizontal"></a> 3.设置水平轴的格式和标签  
 默认情况下，水平轴采用常用格式显示值，将自动调整为适合图表的大小。  
  
#### <a name="to-format-a-date-on-the-horizontal-axis"></a>设置水平轴上的日期格式  
  
1.  切换到报表设计视图。  
  
2.  右键单击水平轴，然后依次**水平轴属性**。  
  
3.  单击**数**。  
  
4.  在中**类别**，选择**日期**。  
  
5.  在“类型”框中，选择“2000 年 1 月 31 日”。  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  在“主文件夹”选项卡上，单击“运行”以预览报表。  
  
 日期会以您选择的日期格式显示。 请注意，图表不会在水平轴上显示每个类别的标签。 默认情况下，仅包括适合放在轴旁边的标签。  
  
 通过旋转标签和指定间隔，可以自定义标签显示方式。  
  
#### <a name="to-rotate-the-axis-labels-and-change-the-display-interval-along-the-horizontal-axis"></a>沿着水平轴旋转轴标签并更改显示间隔  
  
1.  切换到报表设计视图。  
  
2.  右键单击水平轴标题，然后单击**显示轴标题**以删除标题。 因为水平轴显示日期，所以不需要标题。  
  
3.  右键单击水平轴，然后单击**水平轴属性**。  
  
4.  在中**轴选项**页**轴范围和间隔**，类型**3**有关**间隔**。 图表将每隔三个日期显示一次标签。  
  
5.  单击**标签**。  
  
6.  在中**更改轴标签自动调整选项**，选择**禁用自动调整**。  
  
7.  在“标签旋转角度”中，选择 -90。  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     水平轴的示例文本将旋转 90 度。  
  
9. 单击 **“运行”** 以预览报表。  
  
 在图表上，标签将旋转并每隔三个日期显示一次标签。  
  
##  <a name="Legend"></a> 4.移动图例  
 系统会根据类别和序列数据自动创建图例。  
  
#### <a name="to-move-the-legend-below-the-chart-area-of-a-column-chart"></a>在柱形图的图表区域的下方移动图例  
  
1.  切换到报表设计视图。  
  
2.  右键单击图表上的图例，然后单击**图例属性**。  
  
3.  有关**布局和位置**，选择其他位置。 例如，将图例位置设置为底部中间。  
  
     如果将图例置于图表的顶部或底部，则图例的布局将会从垂直改为水平。 可以从“布局”下拉列表中选择不同的布局。  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  （可选）因为本教程中只有一个类别，所以不需要图例。 若要删除图例，请右键单击图例，然后单击**删除图例**。  
  
6.  单击 **“运行”** 以预览报表。  
  
##  <a name="ChartTitle"></a> 5.设置图表的标题  
  
#### <a name="to-change-the-chart-title-above-the-chart-area"></a>更改图表区上方的图表标题  
  
1.  切换到报表设计视图。  
  
2.  选择词语**图表标题**顶部的图表，然后键入以下文本： **Store Sales Order Totals**。  
  
3.  单击 **“运行”** 以预览报表。  
  
##  <a name="Vertical"></a> 6.设置垂直轴的格式和标签  
 默认情况下，垂直轴采用常用格式显示值，将自动调整为适合图表的大小。  
  
#### <a name="to-format-as-currency-the-numbers-on-the-vertical-axis"></a>将货币格式设置为垂直轴上的数字  
  
1.  切换到报表设计视图。  
  
2.  在图表的一侧双击垂直轴上的标签以选择它们。  
  
3.  在功能区中，在**主页**选项卡上，在**数量**组中，单击**货币**按钮。 轴标签将更改以显示货币格式。  
  
4.  在功能区中，在**主页**选项卡上，在**数量**组中，单击**减少小数位数**按钮两次，以显示舍入为最接近的美元金额。  
  
5.  右键单击垂直轴，然后单击**垂直轴属性**。  
  
6.  单击**数**。 请注意，**货币**已在中选择**类别**框中，并且**小数位数**已经**0** （零）。  
  
7.  在中**中显示值**框中，单击**数千个**。  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. 右键单击垂直轴标题沿图表的一侧，然后单击**轴标题属性**。  
  
10. 替换中的文本**标题文本**字段的以下文本： **Sales Total (in Thousands)**。 还可以指定与如何设置标题格式相关的多种选项。  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. 单击 **“运行”** 以预览报表。  
  
##  <a name="Average"></a> 7.添加移动平均线  
  
#### <a name="to-add-a-moving-average"></a>添加移动平均线  
  
1.  切换到报表设计视图。  
  
2.  双击图表以显示“图表数据”窗格。  
  
3.  右键单击 **[sum （sales)]** 字段中**值**区域中，并单击**添加计算序列**。  
  
4.  在“公式”中，验证是否已选中“移动平均线”。  
  
5.  在“设置公式参数”中，针对“期间”，选择“4”。  
  
6.  单击**边框**。  
  
7.  在中**线条宽度**，选择**3pt**。  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. 单击 **“运行”** 以预览报表。  
  
 图表将显示一条线条，它按日期显示销售总计的移动平均线，每隔四天计算一次平均值。  
  
##  <a name="Title"></a> 8。添加报表标题  
  
#### <a name="to-add-a-report-title"></a>添加报表标题  
  
1.  切换到报表设计视图。  
  
2.  在设计图面上，单击“单击以添加标题”。  
  
3.  类型**Sales Chart**，再按 ENTER，，然后键入**January to December 2009**，使其如下所示：  
  
     **Sales Chart**  
  
     **1 月至 2009 年 12 月**  
  
4.  选择**Sales Chart**，然后单击**加粗**按钮**字体**部分上**主页**功能区选项卡。  
  
5.  选择**January to December 2009**，然后在**字体**部分**主页**选项卡上，将字号设置为**10**。  
  
6.  （可选）可能需要进行**标题**文本框高度以容纳两行文本，通过拉下双头箭头，单击底部边缘的中部时。  
  
     此标题将显示在报表的顶部。 未定义页标头时，报表体顶部的项就等同于报表标头。  
  
7.  单击 **“运行”** 以预览报表。  
  
##  <a name="Save"></a> 9。保存报表  
  
#### <a name="to-save-the-report"></a>保存报表  
  
1.  切换到报表设计视图。  
  
2.  从“报表生成器”按钮，单击 **“另存为”**。  
  
3.  在“名称”中，键入 Sales Order Column Chart。  
  
4.  单击 **“保存”**。  
  
## <a name="next-steps"></a>后续步骤  
 您已成功完成“向报表添加柱形图”教程。 若要了解有关图表的详细信息，请参阅[图表（报表生成器和 SSRS）](report-design/charts-report-builder-and-ssrs.md)和[迷你图和数据条（报表生成器和 SSRS）](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程&#40;报表生成器&#41;](report-builder-tutorials.md)   
 [SQL Server 2014 中的报表生成器](report-builder/report-builder-in-sql-server-2016.md)  
  
  
