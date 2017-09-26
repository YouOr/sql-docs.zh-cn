---
title: "连接到服务器 （SQL Server 事件探查器） 后自动启动跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automatic trace start
- traces [SQL Server], starting
- starting trace automatically
ms.assetid: d74b848d-e796-49af-a8c5-dd69230f3a78
caps.latest.revision: 21
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 4850c8ca65aecc5800d3fcf6940a12f79b270662
ms.contentlocale: zh-cn
ms.lasthandoff: 08/02/2017

---
# <a name="start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler"></a>连接到服务器后自动启动跟踪 (SQL Server Profiler)
  本主题介绍了如何在使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 连接到 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]实例后自动启动跟踪。  
  
### <a name="to-start-a-trace-automatically-after-connecting-to-a-server-with-sql-server-profiler"></a>在使用 SQL Server Profiler 连接到服务器后自动启动跟踪  
  
1.  在“工具”  菜单上，单击“选项” 。  
  
2.  选择 **“进行连接后立即启动跟踪”** 复选框。  
  
> [!NOTE]  
>  如果选择“建立连接后立即开始跟踪”，则不会显示“跟踪属性”对话框，而是开始跟踪。 若要编辑跟踪属性，必须先关闭此设置。  
  
## <a name="see-also"></a>另请参阅  
 [SQL Server 事件探查器](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  