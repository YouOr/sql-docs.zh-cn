---
title: MSSQLSERVER_17130 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 17130 (Database Engine error)
ms.assetid: 7ce6afca-221d-402f-89df-da7e74a339a8
caps.latest.revision: 17
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: a12e82794f17df089a6b426a5795b91424093349
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
ms.locfileid: "34321758"
---
# <a name="mssqlserver17130"></a>MSSQLSERVER_17130
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|17130|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|INIT_NOLOCKSPACE|  
|消息正文|没有足够的内存分配给所配置的锁数。 正尝试以较小的锁哈希表启动，但这可能会影响性能。 请与数据库管理员联系，为数据库引擎的这一实例配置更多内存。|  
  
## <a name="explanation"></a>解释  
没有足够的内存来分配所需大小的锁管理器哈希表。  将尝试分配一个较小的哈希表。  
  
## <a name="user-action"></a>用户操作  
检查服务器内存配置参数（最小/最大服务器内存），然后检查内存不足情况。 为 SQL Server 提供更多的内存。  
  
