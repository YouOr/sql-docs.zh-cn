---
title: 'Ibcpsession:: Bcpcolumns (OLE DB) |Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- IBCPSession::BCPColumns (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPColumns method
ms.assetid: c338abe8-9e30-4853-a7c6-b1a6c00095e1
caps.latest.revision: 23
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a1fc6c8da0e46ac40bf6ddd2fbd821cdd6986dc8
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37426336"
---
# <a name="ibcpsessionbcpcolumns-ole-db"></a>IBCPSession::BCPColumns (OLE DB)
  设置绑定到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 表中列的字段数。  
  
## <a name="syntax"></a>语法  
  
```  
  
HRESULT BCPColumns(   
DBCOUNTITEMnColumns);  
```  
  
## <a name="remarks"></a>Remarks  
 在内部调用[ibcpsession:: Bcpcolfmt](ibcpsession-bcpcolfmt-ole-db.md)设置字段数据的默认值。 从访问接口内部检索时通过指定表名的 SQL Server 列信息获取这些默认值[ibcpsession:: Bcpinit](ibcpsession-bcpinit-ole-db.md)。  
  
> [!NOTE]  
>  可以调用此方法后，才**BCPInit**已调用具有有效的文件名称。  
  
 只有在您要使用不同于默认设置的用户文件格式时，才应调用此方法。 有关默认用户文件格式的说明的详细信息，请参阅**BCPInit**方法。  
  
 在调用**BCPColumns**方法时，必须调用**BCPColFmt**完整地定义自定义文件格式的用户文件中的每列的方法。  
  
## <a name="arguments"></a>参数  
 *nColumns*[in]  
 用户文件中字段的总数。 即使你准备从用户文件的大容量复制数据到 SQL Server 表并不打算将所有字段都复制用户文件中，仍必须设置*nColumns*参数对用户文件字段的总数。 然后可以通过指定跳过的字段**BCPColFmt**。  
  
## <a name="return-code-values"></a>返回代码值  
 S_OK  
 方法成功。  
  
 E_FAIL  
 特定于访问接口时出错;详细信息，请使用[ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md)接口。  
  
 E_UNEXPECTED  
 意外调用了该方法。 例如， **BCPInit**调用此方法之前，未调用方法。 在为某一大容量复制操作多次调用此方法时，也会发生这一意外调用。  
  
 E_OUTOFMEMORY  
 内存不足错误。  
  
## <a name="see-also"></a>请参阅  
 [IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md)   
 [执行大容量复制操作](../native-client/features/performing-bulk-copy-operations.md)  
  
  
