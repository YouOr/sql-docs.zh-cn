---
title: getColumnDisplaySize 方法 (SQLServerResultSetMetaData) |Microsoft 文档
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
- SQLServerResultSetMetaData.getColumnDisplaySize
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 21c25443-bd2b-4b60-9798-4efe2c158952
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 97d5899370329d49d6ed289e8742ebcab6d402d8
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32832162"
---
# <a name="getcolumndisplaysize-method-sqlserverresultsetmetadata"></a>getColumnDisplaySize 方法 (SQLServerResultSetMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  返回普通的最大宽度，以字符为单位，指定的列。  
  
## <a name="syntax"></a>语法  
  
```  
  
public int getColumnDisplaySize(int column)  
```  
  
#### <a name="parameters"></a>Parameters  
 *column*  
  
 指示列索引的 int。  
  
## <a name="return-value"></a>返回值  
 **Int** ，该值指示最大宽度。 如果宽度未知，则返回 0。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.ResultSetMetaData 接口中的 getColumnDisplaySize 方法指定此 getColumnDisplaySize 方法。  
  
 [!INCLUDE[msCoName](../../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] JDBC Driver 3.0 COLUMN_SIZE 列中具有的行为更改。 请参阅[SQLServerDatabaseMetaData.getColumns](../../../connect/jdbc/reference/getcolumns-method-sqlserverdatabasemetadata.md)有关详细信息。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerResultSetMetaData 成员](../../../connect/jdbc/reference/sqlserverresultsetmetadata-members.md)   
 [SQLServerResultSetMetaData 类](../../../connect/jdbc/reference/sqlserverresultsetmetadata-class.md)  
  
  
