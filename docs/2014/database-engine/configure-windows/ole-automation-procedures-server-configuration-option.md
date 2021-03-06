---
title: Ole Automation Procedures 服务器配置选项 | Microsoft Docs
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
- Ole Automation Procedures option
ms.assetid: e8982e05-4984-4406-9760-285e8c028ddf
caps.latest.revision: 20
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: a1f1feb6278c36f09c978f5f8f1ae6dbf9f64e60
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37205757"
---
# <a name="ole-automation-procedures-server-configuration-option"></a>Ole Automation Procedures 服务器配置选项
  使用 `Ole Automation Procedures` 选项可指定是否可以在 [!INCLUDE[tsql](../../includes/tsql-md.md)] 批处理中实例化 OLE Automation 对象。 还可以使用基于策略的管理或者 **sp_configure** 存储过程来配置这一选项。 有关详细信息，请参阅 [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md)。  
  
 `Ole Automation Procedures`选项可以设置为以下值。  
  
 0  
 禁用 OLE Automation Procedures。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]新实例的默认值。  
  
 @shouldalert  
 启用 OLE Automation Procedures。  
  
 当启用 OLE Automation Procedures 时，对 **sp_OACreate** 的调用将会启动 OLE 共享执行环境。  
  
 当前值`Ole Automation Procedures`选项可以查看和更改通过使用**sp_configure**系统存储过程。  
  
## <a name="examples"></a>示例  
 以下示例显示了如何查看 OLE Automation Procedures 的当前设置。  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 以下示例显示了如何启用 OLE Automation Procedures。  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>请参阅  
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)   
 [RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql)   
 [外围应用配置器](../../relational-databases/security/surface-area-configuration.md)   
 [服务器配置选项 (SQL Server)](server-configuration-options-sql-server.md)  
  
  
