---
title: setAsciiStream 方法 (SQLServerNClob) |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 617ece92-0fb1-4f95-b32d-29b5b56eb3fb
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 89906ee626bc16d1b3c5b1b4f83fa5b4c4b8f15d
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32841242"
---
# <a name="setasciistream-method-sqlservernclob"></a>setAsciiStream 方法 (SQLServerNClob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索流用于写入 ASCII 字符到**NCLOB**值**java.sql.NClob**对象所表示，从指定位置开始。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.io.OutputStream setAsciiStream(long pos)  
```  
  
#### <a name="parameters"></a>Parameters  
 *pos*  
  
 若要开始写入的位置**NCLOB**对象; 的第一个位置为 1。  
  
## <a name="return-value"></a>返回值  
 可以写入 OutputStream 对象表示向其 ASCII 编码字符的流。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.NClob 接口中的 setAsciiStream 方法指定此 setAsciiStream 方法。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerNClob 方法](../../../connect/jdbc/reference/sqlservernclob-methods.md)   
 [SQLServerNClob 成员](../../../connect/jdbc/reference/sqlservernclob-members.md)   
 [SQLServerNClob 类](../../../connect/jdbc/reference/sqlservernclob-class.md)  
  
  
