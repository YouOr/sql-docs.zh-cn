---
title: 查看保存的跟踪 (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: sql-trace
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], viewing
- displaying traces
- viewing traces
ms.assetid: 3a95a816-aa89-4d5f-858c-968a9cb3ee87
caps.latest.revision: 22
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: e65a80b3ec4b344cbd20e249c7184bfc6926b07b
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38061685"
---
# <a name="view-a-saved-trace-transact-sql"></a>查看保存的跟踪 (Transact-SQL)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  本主题说明如何使用内置函数查看保存的跟踪。  
  
### <a name="to-view-a-specific-trace"></a>查看特定的跟踪  
  
1.  通过指定需要获得其信息的跟踪的 ID 来执行 **fn_trace_getinfo** 。 此函数将返回一个表，表中列出了跟踪、跟踪属性以及有关属性的信息。  
  
     请按以下方式调用此函数：  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(trace_id)  
    ```  
  
### <a name="to-view-all-existing-traces"></a>查看所有现有跟踪  
  
1.  通过指定 **或** 来执行 `0` fn_trace_getinfo `default`。 此函数将返回一个表，表中列出了所有跟踪、跟踪属性以及有关这些属性的信息。  
  
     请按以下方式调用此函数：  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(default)  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 若要运行内置函数 **fn_trace_getinfo**，用户需要具有以下权限：  
  
 对服务器具有 ALTER TRACE 权限。  
  
## <a name="see-also"></a>另请参阅  
 [sys.fn_trace_getinfo (Transact-SQL)](../../relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql.md)   
 [使用 SQL Server Profiler 查看和分析跟踪](../../tools/sql-server-profiler/view-and-analyze-traces-with-sql-server-profiler.md)  
  
  
