---
title: 用于配置管理使用 WQL 访问 WMI 提供程序 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
ms.assetid: 26499530-d93b-452b-bbe4-217ef1d11e68
caps.latest.revision: 16
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: f35c895597bf19a7cc4ad20614d2d2f29521504e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37313357"
---
# <a name="access-wmi-provider-for-configuration-management-using-wql"></a>使用 WQL 访问用于配置管理的 WMI 提供程序
  本节描述如何根据用于计算机管理的 WMI 提供程序执行 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Management Instrumentation 查询语言 (WQL) 语句。  
  
 该示例使用 WQL 编辑器 WBEMtest.exe 根据 WMI 提供程序运行 WQL 查询，以枚举 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 服务、网络协议和别名。  
  
### <a name="querying-services-using-wbemtest"></a>使用 WBEMtest 查询服务  
  
1.  从**启动**菜单上，单击**运行**，然后输入`WBEMtest`。  
  
2.  将出现 WBEMtest.exe 对话框。 单击 **“连接”**。  
  
3.  在第一个文本字段中，键入计算机管理命名空间的 WMI 提供程序：root\Microsoft\SqlServer\ComputerManagement11。 单击 **“连接”**。  
  
4.  单击**查询**。 键入用于返回在本地计算机上运行的当前服务的查询：**选择\*从 SqlService。** 单击 **“应用”**。  
  
5.  通过添加 `WHERE ServiceName = "MSSQLSERVER"`，进一步细化查询。  
  
  
