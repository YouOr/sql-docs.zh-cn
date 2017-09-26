---
title: MSSQLSERVER_17194 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- "17194"
helpviewer_keywords:
- 17194 (Database Engine error)
ms.assetid: 0d03eb20-28a7-4ceb-8903-7f9420a620f7
caps.latest.revision: 11
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: f33e6e16d4f62e7b39afe3b5cd9b57ce13d15a1a
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="mssqlserver17194"></a>MSSQLSERVER_17194
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|SQL Server|  
|事件 ID|17194|  
|事件源|MSSQLSERVER|  
|组件|SQLEngine|  
|符号名称||  
|消息正文|服务器无法加载登录所需的 SSL 提供程序库；连接已关闭。 可以用 SSL 对登录序列或所有通信进行加密，具体取决于管理员配置服务器的方式。 有关错误消息：0xXXXX. [客户端: 11.11.11.11] 的详细信息，请参见联机丛书|  
  
## <a name="explanation"></a>解释  
此错误指示客户端已关闭连接。 因为连接超时时间已到，所以有可能发生此错误。 该错误消息将显示操作系统返回的值，说明错误的根本问题。  
  
## <a name="user-action"></a>用户操作  
如果错误消息中的错误代码为 0x2746（十进制值 10054），则说明客户端重置了连接,通常是因为连接超时。 若要纠正此错误，请延长客户端或调用程序连接超时时间。  
  
若要为其他错误消息值确定可能的解决方案，请使用操作系统命令 **net helpmsg**，并指定错误代码的十进制值。  
  
有关如何连接到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的详细信息，请参阅[服务器网络配置](~/database-engine/configure-windows/server-network-configuration.md)和[客户端网络配置](~/database-engine/configure-windows/client-network-configuration.md)。  
  
## <a name="internal-only"></a>仅内部  
