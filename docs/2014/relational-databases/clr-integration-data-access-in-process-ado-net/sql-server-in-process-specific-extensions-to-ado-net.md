---
title: SQL Server 进程内特定扩展 ADO.NET |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- data access [CLR integration]
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], in-process extensions
- in-process data access providers [CLR integration]
- extensions [CLR integration]
ms.assetid: 781b812e-eb14-472a-85fa-aa4cdb929bee
caps.latest.revision: 32
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: bd625f2b09f70e7356c169248953786c70dd1ad9
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37354939"
---
# <a name="sql-server-in-process-specific-extensions-to-adonet"></a>SQL Server 进程内专用的 ADO.NET 扩展
  主要有四种专门在进程内使用的 ADO.NET 功能性扩展。 下列主题将详细地介绍这些扩展功能。  
  
## <a name="in-this-section"></a>本节内容  
 [SqlContext 对象](sqlcontext-object.md)  
 该类通过提取在进程内执行托管代码的 SQL Server 例程的调用方上下文来提供对其他扩展功能的访问。  
  
 [SqlPipe 对象](sqlpipe-object.md)  
 该类包含向客户端发送表格式结果和消息的例程。  
  
 [SqlTriggerContext 对象](sqltriggercontext-object.md)  
 该类提供触发器运行所在的上下文的信息。  
  
 [SqlDataRecord 对象](sqldatarecord-object.md)  
 SqlDataRecord 类表示一行数据及其相关元数据，并允许存储过程将自定义结果集返回到客户端。  
  
  
