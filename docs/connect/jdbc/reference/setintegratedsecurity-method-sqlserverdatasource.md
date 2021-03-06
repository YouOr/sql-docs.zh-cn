---
title: setIntegratedSecurity 方法 (SQLServerDataSource) |Microsoft 文档
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
- SQLServerDataSource.setIntegratedSecurity
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 4c968ee4-b041-424a-bf69-cc2c4a4f51c6
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e2dca7a3c3cb2f6ac80fd9901c05e03135a42dc4
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32842862"
---
# <a name="setintegratedsecurity-method-sqlserverdatasource"></a>setIntegratedSecurity 方法 (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  集**布尔**值，该值指示是否启用了 integratedSecurity 属性。  
  
## <a name="syntax"></a>语法  
  
```  
  
public void setIntegratedSecurity(boolean enable)  
```  
  
#### <a name="parameters"></a>Parameters  
 *enable*  
  
 **true**如果启用 integratedSecurity。 否则为 **false**。  
  
## <a name="remarks"></a>注释  
 设置为"**true**"以指示，将通过使用 Windows 凭据[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]的应用程序用户进行身份验证。 如果"**true**"，则[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]将搜索已提供在计算机或网络登录的凭据的本地计算机凭据缓存。 如果"**false**"，必须提供用户名和密码。  
  
> [!NOTE]  
>  在上才支持此属性[!INCLUDE[msCoName](../../../includes/msconame_md.md)]Windows 操作系统。  
  
 有关使用集成身份验证的详细信息，请参阅[生成连接 URL](../../../connect/jdbc/building-the-connection-url.md)。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerDataSource 成员](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 类](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
