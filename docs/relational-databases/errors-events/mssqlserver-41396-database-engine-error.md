---
title: MSSQLSERVER_41396 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 41396 (Database Engine error)
ms.assetid: 4ff04042-8367-46f3-8a16-c94682d6eedb
caps.latest.revision: 8
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 27799ec8daa7964bd60220c02053b24eac4af0a7
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
ms.locfileid: "34319908"
---
# <a name="mssqlserver41396"></a>MSSQLSERVER_41396
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|事件 ID|41396|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|MAX_SORT_ROWS_EXCEEDED|  
|消息正文|该排序操作超出了缓冲区限制。 存储过程执行已中止。 有关详细信息，请查阅 SQL Server 联机丛书。|  
  
## <a name="explanation"></a>解释  
本机编译的存储过程在内存中执行排序操作。 对排序缓冲区的大小存在限制。 此错误意味着该排序缓冲区的大小超过了此限制。 排序操作和存储过程执行已中止。  
  
排序缓冲区中每一行或条目的大小由已排序的行数以及查询中联接的数目和聚合函数的数目和类型确定。 通过简化查询，可以减小每一行的大小，从而在排序缓冲区中容纳更多的行。 基表中行的大小不会影响排序缓冲区中每一行或条目的大小。  
  
## <a name="user-action"></a>用户操作  
选择更少的行，或者通过删除联接或聚合函数降低查询的复杂程度。  
  
## <a name="see-also"></a>另请参阅  
[内存中 OLTP（内存中优化）](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
