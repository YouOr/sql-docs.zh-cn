---
title: MSSQL_ENG014144 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014144 error
ms.assetid: fdc744d5-530e-48c4-9420-cca032fd482b
caps.latest.revision: 11
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 49be2d02192109607ace90021bfd8901817091ff
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37217037"
---
# <a name="mssqleng014144"></a>MSSQL_ENG014144
    
## <a name="message-details"></a>消息详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|14144|  
|事件源|MSSQLSERVER|  
|组件|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|符号名称||  
|消息正文|无法删除订阅服务器 '%s'。 在发布数据库 '%s' 中已有此服务器的订阅。|  
  
## <a name="explanation"></a>解释  
 配置为订阅服务器的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例在存在有为其配置的活动订阅时无法从订阅服务器的角色中删除。  
  
## <a name="user-action"></a>用户操作  
 在尝试更改 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的订阅服务器状态之前，删除所有相关联的订阅。  
  
1.  在发布服务器的发布数据库中执行 [sp_helpsubscription (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql)，以查找订阅。  
  
2.  在发布数据库中执行 [sp_dropsubscription (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql)，以删除订阅。  
  
## <a name="see-also"></a>请参阅  
 [错误和事件参考（复制）](errors-and-events-reference-replication.md)   
 [订阅发布](subscribe-to-publications.md)  
  
  
