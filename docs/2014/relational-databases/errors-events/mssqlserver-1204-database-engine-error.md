---
title: MSSQLSERVER_1204 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 1204 (Database Engine error)
ms.assetid: de6ece78-79de-484d-9224-ca0f7645815f
caps.latest.revision: 18
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: dd7c0cd0f1488b8e81dce19898f9b694c511de10
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37409756"
---
# <a name="mssqlserver1204"></a>MSSQLSERVER_1204
    
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|1204|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|LK_OUTOF|  
|消息正文|SQL Server 数据库引擎的实例此时无法获得 LOCK 资源。 请在活动用户较少时重新运行该语句。 请询问数据库管理员，检查此实例的锁定和内存配置，或检查是否有长时间运行的事务。|  
  
## <a name="explanation"></a>解释  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 无法获得锁资源。 这可能是由以下任一原因导致的：  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 无法从操作系统分配更多的内存，因为其他进程正在使用它，或者因为服务器在配置了“最大服务器内存”选项的情况下运行。  
  
-   锁管理器使用的内存不会超过可供 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 使用的内存的 60%。  
  
## <a name="user-action"></a>用户操作  
 如果您怀疑 SQL Server 无法分配足够的内存，请尝试执行以下操作：  
  
-   如果除 SQL Server 外的应用程序正在占用资源，请尝试停止这些应用程序，或者考虑在单独的服务器上运行它们。 这样其他进程将释放并删除内存供 SQL Server 使用。  
  
-   如果已配置 max server memory，请增大其设置。  
  
 如果您怀疑锁管理器使用了最大可用内存，请识别持有最多锁的事务并终止它。 以下脚本将识别持有最多锁的事务：  
  
```  
SELECT request_session_id, COUNT (*) num_locks  
FROM sys.dm_tran_locks  
GROUP BY request_session_id   
ORDER BY count (*) DESC  
```  
  
 采用最大会话 id，并使用 KILL 命令终止它。  
  
  
