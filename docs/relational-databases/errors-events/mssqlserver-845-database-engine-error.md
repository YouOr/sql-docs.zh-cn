---
title: MSSQLSERVER_845 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 845 (Database Engine error)
ms.assetid: 8fff6ad4-234c-44be-b123-e25d5e1cd63e
caps.latest.revision: 17
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 1e277843fe036bde992e90ed3de4b780553a4e1e
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
ms.locfileid: "34324770"
---
# <a name="mssqlserver845"></a>MSSQLSERVER_845
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|845|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|BUFLATCH_TIMEOUT|  
|消息正文|等待用于页 %S_PGID，数据库 ID %d 的缓冲区闩锁类型 %d 时发生超时。|  
  
## <a name="explanation"></a>解释  
进程正在等待获取闩锁，但该进程一直等到超过时间限制也未能获取一个闩锁。 其他任务阻塞系统进程时，通常会导致完成 I/O 操作的时间过长，这时则可能发生此错误。 在一些实例中，此错误可能是硬件故障引起的。  
  
## <a name="user-action"></a>用户操作  
执行下列任务可能可以防止此错误：  
  
-   减少工作负荷。  
  
-   检查错误日志或事件日志中是否存在相关联的 I/O 故障。 I/O 故障通常是由磁盘故障引起的。  
  
-   检查错误日志中是否存在非生成任务和其他严重错误。  
  
-   如果频繁出现诸如断定之类的错误，请解决这些问题。  
  
如果错误仍存在，请与 Microsoft 客户服务与支持部门联系。  
  
