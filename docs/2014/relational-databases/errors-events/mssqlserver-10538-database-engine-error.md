---
title: MSSQLSERVER_10538 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 10538 (Database Engine error)
ms.assetid: 284d19b4-4979-4cbe-a9be-ac1104433c69
caps.latest.revision: 9
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 68ad165f0cc3282505d882537f791d253e811ad1
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37417506"
---
# <a name="mssqlserver10538"></a>MSSQLSERVER_10538
    
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|10538|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|PG_INVALID_PLANGUIDE_HANDLE|  
|消息正文|因为指定的计划指南 ID 为 NULL 或无效，或者您对该计划指南引用的对象没有所需权限，所以找不到该计划指南。 请确保计划指南 ID 有效，当前会话设置为正确的数据库上下文，并且你对计划指南所引用的对象具有 ALTER DATABASE 权限或 ALTER 权限。|  
  
## <a name="explanation"></a>解释  
 指定的计划指南 ID 为 NULL 或无效，或者您对该计划指南引用的对象没有所需权限。  
  
## <a name="user-action"></a>用户操作  
 请确保计划指南 ID 有效，当前会话设置为正确的数据库上下文，并且你对计划指南所引用的对象具有 ALTER DATABASE 权限或 ALTER 权限。  
  
## <a name="see-also"></a>请参阅  
 [sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)   
 [计划指南](../performance/plan-guides.md)   
 [sp_create_plan_guide_from_handle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
