---
title: 常用筛选器（报表生成器和 SSRS）| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- multivalued parameters [Reporting Services]
- single-valued parameters [Reporting Services]
- parameters [Reporting Services], multivalued
- valid values [Reporting Services]
ms.assetid: cb70d0cd-707b-4de5-b39f-e4eb57d316aa
caps.latest.revision: 36
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: e0c10880dd8557ed7d1a0902b33397e37bd6483c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37185746"
---
# <a name="commonly-used-filters-report-builder-and-ssrs"></a>常用筛选器（报表生成器和 SSRS）
  若要创建筛选器，必须指定一个或多个筛选器公式。 筛选器公式包括表达式、数据类型、运算符和值。 本主题提供了常用筛选器的示例。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a>筛选器示例  
 下表显示使用不同数据类型和不同运算符的筛选器公式的示例。 比较的范围由将为其定义筛选器的报表项确定。 例如，对于为数据集定义的筛选器， **TOP % 10** 表示数据集中前 10% 的值；对于为组定义的筛选器， **TOP % 10** 表示组中前 10% 的值。  
  
|简单表达式|数据类型|运算符|ReplTest1|Description|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|包括大于 7 的数据值。|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|包括前 10 个数据值。|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|包括前 20% 的数据值。|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|包括大于 $100 的 System.Decimal（SQL“money”数据类型）类型的所有值。|  
|`[OrderDate]`|`DateTime`|`>`|`2088-01-01`|包括从 2008 年 1 月 1 日到当前日期的所有日期。|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|包括从 2008 年 1 月 1 日到 2008 年 2 月 1 日（含此日）的日期。|  
|`[Territory]`|`Text`|`LIKE`|`*east`|以“east”结尾的所有区域名称。|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|名称开头包括“North”和“South”的所有区域名称。|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|以字母 B、 C 或 T 开头的所有子类别值。|  
  
## <a name="examples-with-report-parameters"></a>报表参数的示例  
 下表提供包括单值或多值参数引用的筛选表达式的示例。  
  
|参数类型|（筛选）表达式|运算符|ReplTest1|数据类型|  
|--------------------|---------------------------|--------------|-----------|---------------|  
|单值|`[EmployeeID]`|=|`[@EmployeeID]`|Integer|  
|多值|`[EmployeeID]`|IN|`[@EmployeeID]`|Integer|  
  
## <a name="see-also"></a>请参阅  
 [报表参数（报表生成器和报表设计器）](report-parameters-report-builder-and-report-designer.md)   
 [添加数据集筛选器、数据区域筛选器和组筛选器（报表生成器和 SSRS）](add-dataset-filters-data-region-filters-and-group-filters.md)   
 [在报表中使用表达式&#40;报表生成器和 SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md)   
 [表达式示例（报表生成器和 SSRS）](expression-examples-report-builder-and-ssrs.md)   
 [表达式中的数据类型&#40;报表生成器和 SSRS&#41;](expressions-report-builder-and-ssrs.md)  
  
  
