---
title: 将数据库复制到其他服务器 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: databases
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- servers [SQL Server], copying databases between
- bulk exporting [SQL Server], between servers
- database copying [SQL Server]
- migrating databases [SQL Server]
- moving databases
- copying databases
- bulk importing [SQL Server], between servers
ms.assetid: 978406d6-a3c8-4902-b1f4-4ced75234be5
caps.latest.revision: 42
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 2e5cef0155dbba74d3b5217da6d41d5ee7ffe77c
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32923822"
---
# <a name="copy-databases-to-other-servers"></a>将数据库复制到其他服务器
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  有时候将数据库从一台计算机复制到另一台计算机会很有用，无论是用于测试、检查一致性、开发软件、运行报表、创建镜像数据库还是将数据库用于远程分支操作。  
  
 有几种复制数据库的方法：  
  
-   使用复制数据库向导  
  
     可以使用复制数据库向导在服务器之间复制或移动数据库，或者将 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 数据库升级到更高版本。 有关详细信息，请参阅 [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md)。  
  
-   还原数据库备份  
  
     若要复制整个数据库，可以使用 BACKUP 和 RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] 语句。 通常，还原数据库的完整备份用于因各种原因将数据库从一台计算机复制到其他计算机。 有关使用备份和还原复制数据库的信息，请参阅[通过备份和还原复制数据库](../../relational-databases/databases/copy-databases-with-backup-and-restore.md)。  
  
    > [!NOTE]  
    >  若要为进行数据库镜像设置镜像数据库，则必须使用 RESTORE DATABASE *<database_name>* WITH NORECOVERY 将数据库还原到镜像服务器。 有关详细信息，请参阅 [为镜像准备镜像数据库 (SQL Server)](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md)的各版本中均未提供见证服务器实例。  
  
-   使用生成脚本向导发布数据库  
  
     可以使用生成脚本向导将数据库从本地计算机传输到 Web 宿主提供程序。 有关详细信息，请参阅 [生成和发布脚本向导](../../relational-databases/scripting/generate-and-publish-scripts-wizard.md)。  
  
  
