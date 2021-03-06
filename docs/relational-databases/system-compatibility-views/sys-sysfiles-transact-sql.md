---
title: sys.sysfiles (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-compatibility-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sysfiles
- sys.sysfiles_TSQL
- sys.sysfiles
- sysfiles_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysfiles system table
- sys.sysfiles compatibility view
ms.assetid: 3b47f38d-1cff-404d-89d3-9342c451c802
caps.latest.revision: 40
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 74db81ffa2764f3243a80b504df84b9f6ffd6ec5
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33220848"
---
# <a name="syssysfiles-transact-sql"></a>sys.sysfiles (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  数据库中的每个文件对应一行。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**fileid**|**int**|每个数据库的唯一文件标识号。|  
|**groupid**|**int**|文件组标识号。|  
|size|**int**|文件大小（8 KB 页）。|  
|**最大大小**|**int**|最大文件大小（以 8 KB 为单位的页）。<br /><br /> 0 = 无增长。<br /><br /> -1 = 文件将一直增长到磁盘充满为止。<br /><br /> 268435456 = 日志文件将增长到最大大小 2 TB。<br /><br /> 注意： 无限制的日志文件大小与升级的数据库将报告为-1 的日志文件的最大大小。|  
|**增长**|**int**|数据库的增长大小。 可以是页面数，或是文件大小，具体取决于值的百分比**状态**。<br /><br /> 0 = 无增长。|  
|**status**|**int**|有关 bits 状态**增长**以兆字节 (MB) 或千字节 (KB) 的值。<br /><br /> 0x2 = 磁盘文件。<br /><br /> 0x40 = 日志文件。<br /><br /> 0x100000 = 增长。 该值是百分比，不是页数。|  
|**perf**|**int**|保留。|  
|**名称**|**sysname**|文件的逻辑名称。|  
|**filename**|nvarchar(260)|物理设备的名称。 这包括文件的完整路径。|  
  
## <a name="see-also"></a>另请参阅  
 [将系统表映射到系统视图&#40;Transact SQL&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [兼容性视图 (Transact SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
