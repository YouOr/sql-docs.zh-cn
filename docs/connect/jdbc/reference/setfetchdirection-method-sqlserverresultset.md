---
title: setFetchDirection 方法 (SQLServerResultSet) |Microsoft 文档
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
- SQLServerResultSet.setFetchDirection
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 4ee82290-508d-4bff-a5c5-8a56338deef8
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c1f042804aa21ca91031c56d285bbfb9d0d8e1f0
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32843562"
---
# <a name="setfetchdirection-method-sqlserverresultset"></a>setFetchDirection 方法 (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  在其中提供有关方向提示中行[SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)将处理对象。  
  
> [!NOTE]  
>  此方法当前不支持通过[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]。 如果使用此方法，则 JDBC 驱动程序将记住该设置，但目前不进行处理。  
  
## <a name="syntax"></a>语法  
  
```  
  
public void setFetchDirection(int direction)  
```  
  
#### <a name="parameters"></a>Parameters  
 *方向*  
  
 **Int** ，该值指示建议的提取方向。 可以是以下值之一：  
  
 ResultSet.FETCH_FORWARD  
  
 ResultSet.FETCH_REVERSE  
  
 ResultSet.FETCH_UNKNOWN  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.ResultSet 接口中的 setFetchDirection 方法指定此 setFetchDirection 方法。  
  
 此方法的初始值由[SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)生成此 SQLServerResultSet 对象的对象。 可以随时更改提取方向。  
  
> [!NOTE]  
>  当游标类型为只进时，使用此方法将不起作用。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerResultSet 成员](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 类](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
