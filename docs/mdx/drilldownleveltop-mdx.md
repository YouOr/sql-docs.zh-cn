---
title: DrilldownLevelTop (MDX) |Microsoft 文档
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 3564a1ac5ab899f4fb731381b74d9d39999845c9
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34739856"
---
# <a name="drilldownleveltop-mdx"></a>DrilldownLevelTop (MDX)


  将集中某一指定级别上最顶端的成员深化到下一个级别。  
  
## <a name="syntax"></a>语法  
  
```  
  
DrilldownLevelTop(<Set_Expression>, <Count> [,[<Level_Expression>] [,[<Numeric_Expression>][,INCLUDE_CALC_MEMBERS]]])  
  
```  
  
## <a name="arguments"></a>参数  
 *Set_Expression*  
 返回集的有效多维表达式 (MDX)。  
  
 *计数*  
 指定要返回的元组数的有效数值表达式。  
  
 *Level_Expression*  
 返回级别的有效多维表达式 (MDX)。  
  
 *Numeric_Expression*  
 返回数字的有效数值表达式，通常为单元坐标的多维表达式 (MDX)。  
  
 *Include_Calc_Members*  
 用于将计算成员添加到深化结果的关键字。  
  
## <a name="remarks"></a>Remarks  
 如果指定数值表达式，则**DrilldownLevelTop**函数以降序顺序，根据的数值表达式的值指定集中的每个成员的子级，如对子成员组成的集求值排序。 如果未指定数值表达式，则此函数根据由查询上下文确定的子成员集所表示的单元值，对指定集中每个成员的子成员按降序排序。  
  
 排序之后, **DrilldownLevelTop**函数返回一组包含父成员和中指定的子成员数*计数，* 使用最高值。  
  
 **DrilldownLevelTop**函数是类似于[DrilldownLevel](../mdx/drilldownlevel-mdx.md)函数，但而不是包含在指定的级别中，每个成员的所有子级**DrilldownLevelTop**函数返回的最顶层子成员数目。  
  
 查询的 XMLA 属性 MdpropMdxDrillFunctions，您可以验证服务器提供钻函数; 支持的级别请参阅[支持 XMLA 属性&#40;XMLA&#41; ](../analysis-services/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties.md)有关详细信息。  
  
## <a name="examples"></a>示例  
 下面的示例根据默认度量值返回产品类别级别的前三个子成员。 在 Adventure Works 示例多维数据集中，Accessories 的前三个子成员是Bike Racks、Bike Stands 和 Bottles and Cages。 在 Management Studio 的 MDX 查询窗口中，你可导航到“产品 | 产品类别 | 成员 | 所有产品 | 附件”查看完整的列表。 你可增加计数参数以返回更多成员。  
  
```  
SELECT DrilldownLevelTop   
   ([Product].[Product Categories].children,  
   3,  
   [Product].[Product Categories].[Category])  
   ON 0  
   FROM [Adventure Works]  
```  
  
 下一个示例演示如何使用**include_calc_members**标志，用于在向级别下钻取中包含计算的成员。 中包含度量值 [分销商订单计数] **DrilldownLevelTop**语句，以确保该按该度量值进行排序的返回值。  
  
```  
WITH MEMBER   
[Product].[Product Categories].[Category].&[3].[Premium Clothes] AS  
[Product].[Product Categories].[Subcategory].&[18] +  
[Product].[Product Categories].[Subcategory].&[21]  
SELECT [Measures].[Reseller Order Count] ON 0,  
DRILLDOWNLEVELTOP(  
  [Product].[Product Categories].children ,  
  2,  
  [Product].[Product Categories].[Category] ,  
  [Measures].[Reseller Order Count],  
  INCLUDE_CALC_MEMBERS ) ON 1  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>请参阅  
 [DrilldownLevel &#40;MDX&#41;](../mdx/drilldownlevel-mdx.md)   
 [MDX 函数引用&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
