---
title: 使用 ORDER BY 排序 (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms-visual-db
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- ORDER BY clause [Visual Database Tools]
ms.assetid: 459f5640-8058-4c24-97e7-7bbd6168bc39
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 98e5927c691cb1d9b4811cf308b139b205ed3058
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "37997649"
---
# <a name="sort-with-order-by-visual-database-tools"></a>使用 ORDER BY 排序 (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
可以使用 ORDER BY 子句按返回行中的一个或多个列对查询结果进行排序。 通过选择“条件详细信息”窗格中的选项可以定义 ORDER BY 子句。  
  
### <a name="to-sort-a-query-using-an-order-by-clause"></a>使用 ORDER BY 子句对查询进行排序  
  
1.  打开一个查询或创建一个新查询。  
  
2.  在[“条件”窗格](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md)中，单击与对查询结果进行排序所依据的列相对应的行的“排序类型”列。  
  
3.  从下拉列表中选择升序或降序。  
  
> [!NOTE]  
> 清除某列的“排序类型”项将从 ORDER BY 子句中删除该列。  
  
请注意，在“条件”窗格中操作时，查询的 UNION 子句将随之更改以反映最近执行的操作。  
  
> [!NOTE]  
> 按多列对结果进行排序时，可使用“排序顺序”列指定要搜索的各列的相对顺序。 有关详细信息，请参阅**如何对查询中的多个列进行排序**。  
  
## <a name="see-also"></a>另请参阅  
[对查询结果进行排序和分组 (Visual Database Tools)](../../ssms/visual-db-tools/sort-and-group-query-results-visual-database-tools.md)  
[汇总查询结果 (Visual Database Tools)](../../ssms/visual-db-tools/summarize-query-results-visual-database-tools.md)  
[设计查询和视图操作指南主题 (Visual Database Tools)](../../ssms/visual-db-tools/design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
