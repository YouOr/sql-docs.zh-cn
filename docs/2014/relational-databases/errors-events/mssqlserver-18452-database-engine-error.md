---
title: MSSQLSERVER_18452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
- 18452 (Database Engine error)
ms.assetid: 21da332c-e81d-4dee-a9d2-95598911b3be
caps.latest.revision: 9
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 217f46ea6fcd8a2697335d9811902aabfad3b296
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37410566"
---
# <a name="mssqlserver18452"></a>MSSQLSERVER_18452
    
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|18452|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称|LOGON_INVALID_CONNECT|  
|消息正文|用户 "%.*ls" 登录失败。 该登录名为 SQL Server 登录名，不能与 Windows 身份验证一起使用。%.\*ls|  
  
## <a name="explanation"></a>解释  
 用户尝试使用无法验证的凭据登录。 可能的原因包括：  
  
-   此登录可能为 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录，但服务器仅接受 Windows 身份验证。  
  
-   您尝试使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 身份验证连接，但 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 上不存在所用登录名。  
  
-   登录可能使用 Windows 身份验证，但登录名是无法识别的 Windows 主体。 无法识别的 Windows 主体表示 Windows 无法验证此登录名。 这可能是由于此 Windows 登录名来自不可信的域。  
  
 类似问题可能导致出现更一般性的错误 18456。  
  
## <a name="user-action"></a>用户操作  
 如果您尝试使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 身份验证进行连接，请验证是否将 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 配置为使用混合身份验证模式。  
  
 如果使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 身份验证连接，请验证此 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录名是否存在。  
  
 如果尝试使用 Windows 身份验证进行连接，请验证您是否正确地登录到相应的域。  
  
  
