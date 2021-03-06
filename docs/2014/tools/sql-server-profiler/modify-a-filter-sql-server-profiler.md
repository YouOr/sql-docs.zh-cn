---
title: 修改筛选器 (SQL Server Profiler) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], modifying
- modifying filters, modifying
- filters [SQL Server], traces
ms.assetid: 8b317813-4918-4485-b930-77b1951aa00c
caps.latest.revision: 14
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ef43f5f4c479866b945b284ce95370b06d1dcc1f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37264123"
---
# <a name="modify-a-filter-sql-server-profiler"></a>修改筛选器 (SQL Server Profiler)
  可以通过将筛选器添加到包含跟踪定义的跟踪模板，来限制跟踪所收集的事件数。 限制收集的事件数能够减少跟踪对性能的影响。 如果已设置了跟踪模板的筛选器，并发现该跟踪没有收集所需类型的信息，则可以对该筛选器进行编辑。  
  
### <a name="to-modify-a-filter"></a>修改筛选器  
  
1.  在 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]中，打开要修改的跟踪筛选器的模板。 在 **“文件”** 菜单上，单击 **“模板”**，然后选择 **“编辑模板”**。  
  
2.  在 **“跟踪模板属性”** 对话框的 **“常规”** 选项卡中，选择 **“选择模板名称”** 列表中的一个模板。  
  
3.  单击 **“事件选择”** 选项卡。  
  
     **“事件选择”** 选项卡包含一个网格控件。 网格控件是包含所有可跟踪事件类的表。 每个事件类在表中占一行。 事件类可能略有不同，这取决于所连接服务器的类型和版本。 事件类由网格的“事件” **“事件”** 列进行标识，并按事件类别进行分组。 其余列则列出每个事件类可以返回的数据列。  
  
4.  单击 **“列筛选器”**。  
  
5.  在 **“编辑筛选器”** 对话框中，单击要编辑的比较运算符旁边的值，然后键入新值或删除一个值。 此外，还可以添加其他筛选器。  
  
6.  单击 **“确定”** 保存模板。  
  
## <a name="see-also"></a>请参阅  
 [SQL Server 事件探查器](sql-server-profiler.md)  
  
  
