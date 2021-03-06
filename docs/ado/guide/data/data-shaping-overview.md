---
title: 数据定形概述 |Microsoft 文档
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- data shaping [ADO], overview
ms.assetid: 4cb5fd29-4e56-46ac-ae48-a6771c321c0c
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 68044aa5ef5eb6364157aa3251b8cc39da73ac78
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35271536"
---
# <a name="data-shaping-overview"></a>数据调整概述
*数据成型*意味着构建在查询中的两个或多个逻辑实体之间的层次结构关系。 可以在父-子关系之间的一个记录中看到层次结构[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)，和一个或多个记录 （也称为章） 的另一个**记录集**。 在父-子关系中，父**记录集**包含子**记录集**。 此类层次结构关系的一个示例是客户和订单。 对于数据库中每个客户，可以有零个或多个订单。 层次结构关系可以是递归的这意味着，孙级记录可以嵌套子记录中。 原则上，可以为任何深度嵌套分层记录。 在实践中，ADO 限制为最多 512 个递归**记录集**s。  
  
 通常情况下，列有形状中**记录集**可以包含来自数据提供程序，如 Microsoft® SQL Server，对另一个引用数据**记录集**，从一单个行计算得出的值**记录集**，或在整个某一列，值派生自操作**记录集**。 虚构且为空，也可以新是某一列。  
  
 检索包含到另一个引用列的值时**记录集**，ADO 会自动将返回实际**记录集**表示引用。 对引用**记录集**是实际的参考子，调用的子集*章*。 单个父类可以引用多个子**记录集**。  
  
 ADO 数据调整的支持，可查询数据源并返回**记录集**顺序 （父） 记录表示的 （子）**记录集**。 在客户订单方案中，你可以使用调整才能检索客户的信息以及订单的单个查询中每个客户的数据。 所产生的**记录集**也称为调整**记录集**。  
  
 此外，数据在 ADO 定形允许你创建新**记录集**而无需使用基础数据源对象**新建**关键字来描述的字段的父和子**记录集**。 新**记录集**对象随后可使用数据填充并持久地存储。 开发人员还可以执行各种计算或聚合 (例如，**总和**， **AVG**，和**最大**) 子字段。 调整数据还可以创建父**记录集**从子级**记录集**通过对子组织单位中的记录进行分组并将一个行放在每个组的子级的父级。  
  
 常规 SQL 允许您检索数据使用**加入**语法，但这可能效率低下和庞大因为冗余的父数据在给定的父-子关系返回每个记录中重复。 数据成型可以使相关的父代中的单个父类记录**记录集**对子组织单位中的多个子记录**记录集**，避免的冗余**加入**。 大多数人查找父-子多个**记录集**编程模型更自然和更轻松地使用比单**记录集加入**模型。
