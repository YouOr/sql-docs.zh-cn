---
title: 将目标服务器登记到主服务器 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- enlisting target servers [SQL Server]
- SQL Server Agent jobs, target servers
- master servers [SQL Server], enlisting target servers
- SQL Server Agent jobs, master servers
- target servers [SQL Server], enlisting
ms.assetid: 7633adb5-d140-4e58-a8f2-5b4b50c2f95b
caps.latest.revision: 33
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 3005fedecb002b50c239f53f1726bb7b6c78e1bc
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37315177"
---
# <a name="enlist-a-target-server-to-a-master-server"></a>将目标服务器登记到主服务器
  本主题介绍了如何将目标服务器添加到多服务器管理配置中。 从主服务器运行此过程。 在 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 中通过使用 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]，或使用 SQL Server 管理对象 (SMO)。  
  
 有关用于 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent 服务的 Windows 帐户如何影响多服务器环境的信息，请参阅 [创建多服务器环境](create-a-multiserver-environment.md)。  
  
 默认情况下，将为主服务器和目标服务器之间的连接启用完全安全套接字层 (SSL) 加密和证书验证。 有关详细信息，请参阅 [在目标服务器上设置加密选项](set-encryption-options-on-target-servers.md)  
  
 **本主题内容**  
  
-   **若要登记目标服务器，请使用：**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
     [SMO](#PowerShellProcedure)  
  
##  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
  
#### <a name="to-enlist-a-target-server"></a>登记目标服务器  
  
1.  在对象资源管理器中，展开配置为主服务器的服务器。   
  
2.  右键单击“SQL Server 代理”，指向“多服务器管理”，然后单击“添加目标服务器”。  
  
3.  完成目标服务器向导，它将指导您完成该进程。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
  
#### <a name="to-enlist-a-target-server"></a>登记目标服务器  
  
1.  使用 `sp_msx_enlist` 存储过程。  有关详细信息，请参阅[sp_msx_enlist &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)  
  
##  <a name="PowerShellProcedure"></a> 使用 SQL Server 管理对象 (SMO)  
  
## <a name="see-also"></a>请参阅  
 [企业范围的自动化管理](automated-administration-across-an-enterprise.md)  
  
  
