---
title: MSSQLSERVER_844 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 844 (Database Engine error)
ms.assetid: 2060c886-1226-4066-bc0c-de90a1cfb82b
caps.latest.revision: 18
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 7d9e2f0374fbbd3fbb9147cceeaef47edccfd769
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
ms.locfileid: "34325078"
---
# <a name="mssqlserver844"></a>MSSQLSERVER_844
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|844|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|BUFLATCH_TIMEOUT_CONTINUE|  
|消息正文|等待缓冲区闩锁时出现超时 - 类型 %d，bp %p，页 %d:%d，stat %#x，数据库 ID: %d，分配单元 ID: %I64d%ls，任务 0x%p : %d，等待时间 %d，标志 0x%I64x，所属任务 0x%p。  将继续等待。|  
  
## <a name="explanation"></a>解释  
进程正在等待获取闩锁。 此问题可能是由所用时间太长而无法完成的 I/O 操作导致的。 通常，此类型的错误是其他任务阻塞系统进程的结果。 在一些实例中，此错误可能是硬件故障引起的。  
  
## <a name="user-action"></a>用户操作  
尝试执行以下操作以防止出现此错误：  
  
-   减少工作负荷。  
  
-   在错误日志或事件日志中检查关联的 I/O 故障。 I/O 故障通常是指磁盘故障。  
  
-   检查错误日志以查找非生成任务和其他错误。  
  
-   如果频繁出现诸如断定之类的错误，请解决这些问题。  
  
如果错误仍存在，请与 Microsoft 客户服务与支持部门联系。  
  
