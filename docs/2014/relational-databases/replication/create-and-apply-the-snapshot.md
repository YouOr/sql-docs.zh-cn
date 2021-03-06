---
title: 创建和应用快照 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- snapshots [SQL Server replication], applying
- snapshots [SQL Server replication], creating
ms.assetid: 631f48bf-50c9-4015-b9d8-8f1ad92d1ee2
caps.latest.revision: 37
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f8f3ee9c034bbb57e2d8b392f02a3021e6ee0eff
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37262343"
---
# <a name="create-and-apply-the-snapshot"></a>创建并应用快照
  快照由快照代理在创建发布后生成。 按以下方式生成：  
  
-   立即。 默认情况下，在新建发布向导中创建合并发布后会立即生成此发布的快照。  
  
-   在计划时间。 在新建发布向导的 **“快照代理”** 页面上指定计划时间，或者在使用存储过程或复制管理对象 (RMO) 时指定计划时间。  
  
-   手动。 从命令提示或 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]运行快照代理。 有关运行代理的详细信息，请参阅[复制代理可执行文件概念](concepts/replication-agent-executables-concepts.md)或[启动和停止复制代理 (SQL Server Management Studio)](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md)。  
  
 对于合并复制，每当运行快照代理时都会生成快照。 对于事务复制，是否生成快照取决于发布属性 **immediate_sync**的设置。 如果该属性设置为 TRUE（使用新建发布向导时的默认设置），则每当运行快照代理时都会生成快照，而且可以随时将其应用到订阅服务器。 如果该属性设置为 FALSE（使用 **sp_addpublication**时的默认设置），则仅当自上次快照代理运行以来添加了新订阅时，才会生成快照；订阅服务器必须等待快照代理完成，才能实现同步。  
  
 默认情况下，快照生成后，它们将保存在位于分发服务器上的默认快照文件夹中。 还可以将快照文件保存在可移动介质（例如可移动磁盘、CD-ROM）上，或者保存在默认快照文件夹以外的位置。 另外，可以压缩文件，以便它们更容易存储和传输以及在订阅服务器上应用快照前后执行脚本。 有关这些选项的详细信息，请参阅 [Snapshot Options](snapshot-options.md)。  
  
 如果快照用于使用参数化筛选器的合并发布，则创建快照的过程包括两部分。 首先创建包含复制脚本和已发布对象的架构（但不包含数据）的架构快照。 然后，使用包括脚本、从架构快照复制的架构以及属于订阅分区的数据的快照初始化每个订阅。 有关详细信息，请参阅 [Snapshots for Merge Publications with Parameterized Filters](snapshots-for-merge-publications-with-parameterized-filters.md)。  
  
 在发布服务器上创建快照并将其存储在默认位置或其他快照位置后，可以将快照传输到订阅服务器并应用。 分发代理（用于快照复制或事务复制）或合并代理（用于合并复制）在初始同步期间将快照传输到订阅服务器上的订阅数据库中并将架构和数据文件应用到此数据库。 默认情况下，如果使用新建订阅向导，在创建订阅后会立即发生初始同步。 此行为由该向导的 **“初始化订阅”** 页面上的 **“初始化时间”** 选项控制。 当初始化订阅后生成快照时，除非订阅标记为重新初始化，否则快照不会应用到订阅服务器。 有关详细信息，请参阅 [重新初始化订阅](reinitialize-subscriptions.md)。  
  
 在分发代理或合并代理应用初始快照后，该代理将传播后续更新和其他数据修改。 在向订阅服务器分发并应用快照时，只有那些正在等待初始快照或新建快照的订阅服务器会受到影响。 该发布的其他订阅服务器（即那些已经收到对已发布数据的插入、更新、删除或其他修改内容的订阅服务器）不受影响。  
  
 若要创建并应用初始快照，请参阅 [Create and Apply the Initial Snapshot](create-and-apply-the-initial-snapshot.md)。  
  
 若要查看或修改默认快照文件夹位置，请参阅  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]：[指定默认快照位置 (SQL Server Management Studio)](specify-the-default-snapshot-location-sql-server-management-studio.md)  
  
-   复制编程和 RMO 编程： [Configure Publishing and Distribution](configure-publishing-and-distribution.md)  
  
## <a name="see-also"></a>请参阅  
 [使用快照初始化订阅](initialize-a-subscription-with-a-snapshot.md)   
 [保护快照文件夹](security/secure-the-snapshot-folder.md)   
 [sp_addpublication (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql)  
  
  
