---
title: 第 1 课：将表转换为层次结构 | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.suite: sql
ms.technology: table-view-index
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- SQL Server 2016
helpviewer_keywords:
- HierarchyID
ms.assetid: 5ee6f19a-6dd7-4730-a91c-bbed1bd77e0b
caps.latest.revision: 18
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: a38cbcec7f42ff99e0e7c56de16fc30a3187dded
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38042625"
---
# <a name="lesson-1-converting-a-table-to-a-hierarchical-structure"></a>第 1 课：将表转换为层次结构
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]
具有使用自联接表示层次结构关系的表的客户可以将本课程作为指南，将他们的表转换为层次结构。 相对而言，从这种表示形式迁移为使用 **hierarchyid**的表示形式较为容易。 迁移之后，用户将拥有一个精简且易于理解的层次结构表示形式，可以采用多种方式对其进行索引以进行有效查询。  
  
本课程将检查现有表、创建一个包含 **hierarchyid** 列的新表、使用源表中的数据填充此表，然后再演示三个索引策略。 本课程包含以下主题：  
  
-   [检查 Employee 表的当前结构](../../relational-databases/tables/lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
-   [使用现有层次结构数据填充表](../../relational-databases/tables/lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
-   [优化 NewOrg 表](../../relational-databases/tables/lesson-1-3-optimizing-the-neworg-table.md)  
  
-   [摘要：将表转换为层次结构](../../relational-databases/tables/lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
## <a name="prerequisites"></a>必备条件  
本课程需要使用 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 示例数据库。  
  
## <a name="next-task-in-lesson"></a>课程中的下一个任务  
[检查 Employee 表的当前结构](../../relational-databases/tables/lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
## <a name="next-lesson"></a>下一课  
[第 2 课：创建和管理层次结构表中的数据](../../relational-databases/tables/lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
  
  
  
