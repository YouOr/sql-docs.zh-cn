---
title: SMO 对象模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], object model
- SQL Server Management Objects, object model
ms.assetid: bd6e59b6-ca46-42c0-adb2-c9d64cf6e00b
caps.latest.revision: 29
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: e31e4efa6ee0655d50567a7da73e85cc811c6692
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37175864"
---
# <a name="smo-object-model"></a>SMO 对象模型
  SMO 对象模型由对象的层次结构构成。 <xref:Microsoft.SqlServer.Management.Smo.Server> 对象是顶层对象，所有实例类对象都位于 <xref:Microsoft.SqlServer.Management.Smo.Server> 对象之下。  
  
 <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> 类是具有单独的对象层次结构的顶级类。 <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>对象表示[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]服务和网络设置可通过 WMI 提供程序。  
  
 除了 <xref:Microsoft.SqlServer.Management.Smo.Server> 和 <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> 对象外，存在若干表示任务或操作的实用工具类，例如 <xref:Microsoft.SqlServer.Management.Smo.Transfer>、<xref:Microsoft.SqlServer.Management.Smo.Backup> 或 <xref:Microsoft.SqlServer.Management.Smo.Restore>。  
  
 SMO 对象模型由若干命名空间构成。 有关详细信息，请参阅 [SMO 命名空间](smo-object-model-namespaces.md)。  
  
## <a name="see-also"></a>请参阅  
 [SMO 对象模型关系图](smo-object-model-diagram.md)   
 [SMO 命名空间](smo-object-model-namespaces.md)   
 [用于配置管理的 WMI 提供程序的概念](../wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
