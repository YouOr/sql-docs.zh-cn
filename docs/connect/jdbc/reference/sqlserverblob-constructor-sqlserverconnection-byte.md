---
title: SQLServerBlob 构造函数 (SQLServerConnection, byte) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerConnection, byte[].SQLServerBlob
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 9fe573e3-30db-4828-abab-e9346493e931
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 6d93e5bee03976c5ae9c55247f98ba180e237a4e
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38064410"
---
# <a name="sqlserverblob-constructor-sqlserverconnection-byte"></a>SQLServerBlob 构造函数 (SQLServerConnection, byte)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  在给定 [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) 对象和字节数组时，初始化 [SQLServerBlob](../../../connect/jdbc/reference/sqlserverblob-class.md) 类的新实例。  
  
> [!NOTE]  
>  JDBC 驱动程序 2.0 版已不推荐使用此方法， 而是使用 [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) 类的 [createBlob](../../../connect/jdbc/reference/createblob-method-sqlserverconnection.md) 方法。  
  
## <a name="syntax"></a>语法  
  
```  
  
public SQLServerBlob(SQLServerConnection connection,  
                     byte[] data)  
```  
  
#### <a name="parameters"></a>Parameters  
 连接  
  
 SQLServerConnection 对象。  
  
 data  
  
 一个字节数组。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerBlob 构造函数](../../../connect/jdbc/reference/sqlserverblob-constructors.md)   
 [SQLServerBlob 成员](../../../connect/jdbc/reference/sqlserverblob-members.md)   
 [SQLServerBlob 类](../../../connect/jdbc/reference/sqlserverblob-class.md)  
  
  
