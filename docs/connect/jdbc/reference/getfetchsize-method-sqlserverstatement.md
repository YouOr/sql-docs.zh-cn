---
title: getFetchSize 方法 (SQLServerStatement) |Microsoft 文档
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
- SQLServerStatement.getFetchSize
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 8115ca58-8ae9-46ce-8515-7905d7bb25fe
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f27175ff8b83e6c60fbf7f92b7dcf8d37d3658c0
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32834362"
---
# <a name="getfetchsize-method-sqlserverstatement"></a>getFetchSize 方法 (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索的结果数设置为结果集生成从该对象是默认提取大小的行数[SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
public final int getFetchSize()  
```  
  
## <a name="return-value"></a>返回值  
 **Int** ，该值指示由指定的提取大小[setFetchSize](../../../connect/jdbc/reference/setfetchsize-method-sqlserverstatement.md)方法。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.Statement 接口中的 getFetchSize 方法指定此 getFetchSize 方法。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerStatement 成员](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 类](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
