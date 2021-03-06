---
title: 查看信息并与发布 （复制监视器） 相关联的代理执行任务 |Microsoft Docs
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
- agents [SQL Server replication], viewing information
- viewing replication agent information
- agents [SQL Server replication], tasks in Replication Monitor
ms.assetid: 2a420da2-66f4-4650-9bdd-1992221ed3fd
caps.latest.revision: 38
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f385a167fe56db1c9db2a2238b22de66daa3ab6a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37280993"
---
# <a name="view-information-and-perform-tasks-for-the-agents-associated-with-a-publication-replication-monitor"></a>查看与发布相关的代理的信息并执行此代理的任务（复制监视器）
  复制监视器提供了 **“代理”** 选项卡，其中包含与所选发布关联的代理的相关信息。 分发代理和合并代理均与订阅相关联；有关详细信息，请参阅[查看与订阅关联的代理的信息和执行其任务（复制监视器）](view-information-and-perform-tasks-for-subscription-agents.md)。  
  
 此选项卡显示有关下列代理的信息：  
  
-   快照代理，用于所有发布。  
  
-   日志读取器代理，用于所有事务发布。  
  
-   队列读取器代理，用于为排队更新订阅启用的事务发布。  
  
 若要查看有关此选项卡上的选项的详细信息，请在菜单栏上单击 **“帮助”** 。 有关启动复制监视器的信息，请参阅[启动复制监视器](start-the-replication-monitor.md)。  
  
### <a name="to-view-information-and-perform-tasks-for-the-agents-associated-with-a-publication"></a>查看与发布相关的代理的信息并执行此代理的任务  
  
1.  在左窗格中展开发布服务器组，再展开其中的一个发布服务器，然后单击其中的一个发布。  
  
2.  单击 **“代理”** 选项卡来查看有关代理的信息。 您还可以通过此选项卡访问更详细的信息并执行任务：  
  
    -   若要查看有关代理的详细信息（如信息性消息以及任何错误消息），请右键单击代理，然后单击 **“查看详细信息”**。  
  
    -   若要查看有关运行代理的作业的详细信息（如计划、作业步骤详细信息等等），请右键单击代理，然后单击 **“属性”**。  
  
    -   若要管理代理的配置文件，请右键单击代理，然后单击 **“代理配置文件”**。 有关详细信息，请参阅[处理复制代理配置文件](../agents/replication-agent-profiles.md)。  
  
    -   若要启动未运行的代理，请右键单击代理，然后单击 **“启动代理”**。  
  
    -   若要停止运行中的代理，请右键单击代理，然后单击 **“停止代理”**。  
  
## <a name="see-also"></a>请参阅  
 [在复制监视器中设置阈值和警告](set-thresholds-and-warnings-in-replication-monitor.md)   
 [查看发布的信息和执行其任务（复制监视器）](view-information-and-perform-tasks-for-a-publication-replication-monitor.md)   
 [复制代理管理](../agents/replication-agent-administration.md)   
 [监视复制](../monitoring-replication.md)  
  
  
