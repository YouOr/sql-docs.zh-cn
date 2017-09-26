---
title: "sqlsrv_configure |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- sqlsrv_configure
apitype: NA
helpviewer_keywords:
- sqlsrv_configure
- API Reference, sqlsrv_configure
ms.assetid: 9393f975-a4ef-4c50-b4dd-14892fc55cc9
caps.latest.revision: 20
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ee3da7943b4bba95335de991e38d45b6261f96e3
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="sqlsrvconfigure"></a>sqlsrv_configure
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

更改错误处理和日志记录选项的设置。  
  
## <a name="syntax"></a>语法  
  
```  
  
sqlsrv_configure( string $setting, mixed $value )  
```  
  
#### <a name="parameters"></a>Parameters  
*$setting*：要配置的设置的名称。 有关设置列表，请参阅下表。  
  
*$value*：要应用于在 *$setting* 参数中指定的设置的值。 此参数的可能值取决于指定的设置。 下表列出了可能的组合：  
  
|设置|$Value 参数的可能值（括号中为等效整数）|默认值|  
|-----------|------------------------------------------------------------------------------|-----------------|  
|ClientBufferMaxKBSize<sup>1</sup>|达到 PHP 内存限制的非负数。<br /><br />零 (0) 表示对缓冲区大小没有任何限制。|10240|  
|LogSeverity<sup>2</sup>|SQLSRV_LOG_SEVERITY_ALL (-1)<br /><br />SQLSRV_LOG_SEVERITY_ERROR (1)<br /><br />SQLSRV_LOG_SEVERITY_NOTICE (4)<br /><br />SQLSRV_LOG_SEVERITY_WARNING (2)|SQLSRV_LOG_SEVERITY_ERROR (1)|  
|LogSubsystems<sup>2</sup>|SQLSRV_LOG_SYSTEM_ALL (-1)<br /><br />SQLSRV_LOG_SYSTEM_CONN (2)<br /><br />SQLSRV_LOG_SYSTEM_INIT (1)<br /><br />SQLSRV_LOG_SYSTEM_OFF (0)<br /><br />SQLSRV_LOG_SYSTEM_STMT (4)<br /><br />SQLSRV_LOG_SYSTEM_UTIL (8)|SQLSRV_LOG_SYSTEM_OFF (0)|  
|WarningsReturnAsErrors<sup>3</sup>|**true** (1) 或**false** (0)|**true** (1)|  
  
## <a name="return-value"></a>返回值  
如果使用不受支持的设置或值调用 **sqlsrv_configure** ，该函数将返回 **false**。 否则，该函数返回 **true**。  
  
## <a name="remarks"></a>注释  
（1） 有关客户端查询的详细信息，请参阅[游标类型 &#40;SQLSRV 驱动程序 &#41;](../../connect/php/cursor-types-sqlsrv-driver.md).  
  
（2） 有关日志记录活动的详细信息，请参阅[日志记录活动](../../connect/php/logging-activity.md)。  
  
（3） 有关配置错误和警告处理的详细信息，请参阅[如何： 配置错误和警告处理使用 SQLSRV 驱动程序](../../connect/php/how-to-configure-error-and-warning-handling-using-the-sqlsrv-driver.md)。  
  
## <a name="see-also"></a>另请参阅  
[SQLSRV 驱动程序 API 参考](../../connect/php/sqlsrv-driver-api-reference.md)  
[PHP SQL 驱动程序编程指南](../../connect/php/programming-guide-for-php-sql-driver.md) 
  
