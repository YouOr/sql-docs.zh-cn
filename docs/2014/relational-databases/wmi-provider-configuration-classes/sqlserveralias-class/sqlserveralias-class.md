---
title: SqlServerAlias 类 |Microsoft Docs
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
api_name:
- SqlServerAlias Class
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServerAlias class
ms.assetid: 475662b9-6985-45bf-b1e9-b0f26ef50443
caps.latest.revision: 33
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 68976bc9c8683554ac58a0744196ecfa5bc7e689
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37274273"
---
# <a name="sqlserveralias-class"></a>SqlServerAlias 类
  [SqlServerAlias 类](sqlserveralias-class.md)类表示服务器连接别名。  
  
 出现以下两种情况时需要服务器连接别名：  
  
-   客户端连接到的实例[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]在不是默认网络传输的网络传输。  
  
-   客户端连接到的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例侦听备用命名管道。  
  
 **注意：** [SqlServerAlias 类](sqlserveralias-class.md)继承`Put`从提供程序类的方法。 但是，与 `Provider::Put` 方法不同，它不会返回任何结果。 有关详细信息，请参阅 WMI 文档。  
  
## <a name="see-also"></a>请参阅  
 [配置客户端协议](http://technet.microsoft.com/library/ms181035.aspx)  
  
  
