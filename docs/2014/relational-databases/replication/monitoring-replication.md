---
title: 监视（复制）| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], about monitoring replication
- transactional replication, monitoring
- monitoring [SQL Server replication]
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
- replication [SQL Server], monitoring
- administering replication, monitoring
ms.assetid: f182f43a-6af8-45bc-a708-08d5f7a6984a
caps.latest.revision: 38
author: craigg-msft
ms.author: craigg
manager: craigg
ms.openlocfilehash: c1276429c773656e04a3ce15f277d08c3b3e52f5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37162298"
---
# <a name="monitoring-replication"></a>监视（复制）
  监视复制拓扑是部署复制的一个重要方面。 因为复制活动是分布式的，所以跟踪复制过程中涉及的所有计算机的活动和状态非常有必要。 以下工具可用于监视复制：  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] Replication Monitor  
  
     复制监视器是监视复制最重要的工具，它可以显示以发布服务器为中心的所有复制活动视图。 有关详细信息，请参阅[监视复制](monitor/monitoring-replication-overview.md)。  
  
-   [!INCLUDE[msCoName](../../includes/msCoName-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssManStudioFull-md.md)]  
  
     [!INCLUDE[ssManStudio](../../includes/ssManStudio-md.md)] 提供对复制监视器的访问。 它还允许您查看当前状态以及下列代理所记录的最后一条消息，还允许您启动和停止每个代理：日志读取器代理、快照代理、合并代理和分发代理。 有关详细信息，请参阅 [Monitor Replication Agents](agents/replication-agents.md)。  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] 和复制管理对象 (RMO)  
  
     两个界面都可用于监视分发服务器上的所有复制类型。 合并复制还提供从发布服务器监视复制的功能。  
  
-   复制代理事件的警报  
  
     复制提供了许多复制代理事件的预定义警报，如果有必要，您还可以创建其他警报。 警报用于触发对某个事件的自动响应和/或用于通知管理员。 有关详细信息，请参阅[对复制代理事件使用警报](agents/use-alerts-for-replication-agent-events.md)。  
  
-   系统监视器  
  
     系统监视器对性能监视很有用，它可为复制提供多个计数器。 有关详细信息，请参阅 [Monitoring Replication with System Monitor](monitor/monitoring-replication-with-system-monitor.md)。  
  
## <a name="see-also"></a>请参阅  
 [管理（复制）](administration/administration-replication.md)   
 [Best Practices for Replication Administration](administration/best-practices-for-replication-administration.md)   
 [监视器复制](monitor/monitoring-replication-overview.md)  
  
  
