---
title: 修改跟踪模板 |Microsoft Docs
ms.custom: ''
ms.date: 07/12/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.suite: sql
ms.technology: profiler
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], SQL Server Profiler
- Profiler [SQL Server Profiler], templates
- trace templates [SQL Server]
- modifying trace templates
- SQL Server Profiler, templates
ms.assetid: 75b62a54-8d16-4599-bd2d-c42cfcc209f4
caps.latest.revision: 24
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 28455e8a0af59b60ffa51e41c01726baaa851987
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "37988159"
---
# <a name="modify-trace-templates"></a>修改跟踪模板
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  用户可以在运行 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] 的本地计算机上的文件中修改保存的模板。 也可以修改从那些文件派生的模板。 修改现有模板时，可以在 **“跟踪属性”** 对话框的 **“事件选择”** 选项卡上，以最初设置属性时相同的顺序编辑事件类和数据列等模板属性。 可以添加和删除事件类和数据列，也可以对筛选进行更改。 修改模板后，将创建用户特定的模板，并且将保持原始系统模板的完整性。 有关详细信息，请参阅 [保存跟踪和跟踪模板](../../tools/sql-server-profiler/save-traces-and-trace-templates.md)。  
  
 如果您无法想起（或者没有保存）创建跟踪时使用的原始模板，或希望以后运行同一跟踪，则可能需要从现有的跟踪文件派生一个模板。 在使用现有跟踪时，可以查看属性，但是不能修改属性。 若要修改属性，请停止或暂停跟踪。 有关详细信息，请参阅[从跟踪文件或跟踪表派生模板 (SQL Server Profiler)](../../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) 和[从正在运行的跟踪派生模板 (SQL Server Profiler)](../../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)。  
  
## <a name="to-modify-a-trace-template"></a>修改跟踪模板  
  
1.  在 **“文件”** 菜单上，指向 **“模板”**，然后单击 **“编辑模板”**。  
  
2.  在 **“跟踪模板属性”** 对话框的 **“常规”** 选项卡上，可以修改服务器类型和模板名称，或者选择将默认模板用于服务器类型。  
  
3.  在“事件选择”选项卡上，使用网格控件来添加或删除跟踪文件中的事件和数据列，如下所示。  
  
    -   若要添加事件，请在 **“事件”** 列中展开相应的事件类别，再选择事件名称。  
  
    -   添加事件时，默认情况下将包含所有相关数据列。 若要从跟踪中删除某个事件的数据列，请清除此事件的该数据列中的复选框。  
  
    -   若要添加筛选器，请单击数据列的名称，然后在 **“编辑筛选器”** 对话框中指定筛选条件。 也可以右键单击数据列名称，再单击“编辑列筛选器”，以启动“编辑筛选器”对话框。 单击 **“确定”** 以添加筛选器。  
  
4.  单击“保存”，或单击“另存为”将跟踪模板另存为其他名称。  
  
## <a name="next-steps"></a>后续步骤  
[启动跟踪](../../tools/sql-server-profiler/start-a-trace.md)  
[创建跟踪](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
[使用 Transact-SQL 修改现有跟踪](../../relational-databases/sql-trace/modify-an-existing-trace-transact-sql.md)  
[使用 SQL Server Profiler 指定跟踪的事件和数据列](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
[sp-跟踪-setevent-transact-sql](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)  
  
