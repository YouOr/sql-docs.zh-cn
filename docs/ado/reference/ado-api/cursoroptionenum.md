---
title: CursorOptionEnum |Microsoft 文档
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CursorOptionEnum
helpviewer_keywords:
- CursorOptionEnum enumeration [ADO]
ms.assetid: 4e10cda7-ce81-4466-94c2-844d38191cf1
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: cf036719cdfc8c03f94c613fae9cc411c1d619b8
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35277326"
---
# <a name="cursoroptionenum"></a>CursorOptionEnum
指定哪些功能[支持](../../../ado/reference/ado-api/supports-method.md)方法应进行测试以。  
  
|常量|ReplTest1|Description|  
|--------------|-----------|-----------------|  
|**adAddNew**|0x1000400|支持[AddNew](../../../ado/reference/ado-api/addnew-method-ado.md)方法来添加新的记录。|  
|**adApproxPosition**|0x4000|支持[AbsolutePosition](../../../ado/reference/ado-api/absoluteposition-property-ado.md)和[AbsolutePage](../../../ado/reference/ado-api/absolutepage-property-ado.md)属性。|  
|**adBookmark**|0x2000|支持[书签](../../../ado/reference/ado-api/bookmark-property-ado.md)属性来访问特定的记录。|  
|**adDelete**|0x1000800|支持[删除](../../../ado/reference/ado-api/delete-method-ado-recordset.md)方法来删除记录。|  
|**adFind**|0x80000|支持[查找](../../../ado/reference/ado-api/find-method-ado.md)方法来查找中的行[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)。|  
|**adHoldRecords**|0x100|检索更多记录或提交所有挂起的更改的情况下修改的下一个位置。|  
|**adIndex**|0x100000|支持[索引](../../../ado/reference/ado-api/index-property.md)属性可以命名索引。|  
|**adMovePrevious**|0x200|支持[MoveFirst](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md)和[MovePrevious](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md)方法，和[移动](../../../ado/reference/ado-api/move-method-ado.md)或[GetRows](../../../ado/reference/ado-api/getrows-method-ado.md)向后位置将当前记录的方法而无需书签。|  
|**adNotify**|0x40000|该值指示基础数据提供程序支持通知 (用于确定是否**记录集**支持事件)。|  
|**adResync**|0x20000|支持[重新同步](../../../ado/reference/ado-api/resync-method.md)方法以将游标更新在基础数据库中可见的数据。|  
|**adSeek**|0x200000|支持[Seek](../../../ado/reference/ado-api/seek-method.md)方法来查找中的行**记录集**。|  
|**adUpdate**|0x1008000|支持[更新](../../../ado/reference/ado-api/update-method.md)方法来修改现有的数据。|  
|**adUpdateBatch**|0x10000|支持批处理更新 ([UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md)和[执行](../../../ado/reference/ado-api/cancelbatch-method-ado.md)方法) 来传输组更改为提供程序。|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 等效项  
 包： **com.ms.wfc.data**  
  
|常量|  
|--------------|  
|AdoEnums.CursorOption.ADDNEW|  
|AdoEnums.CursorOption.APPROXPOSITION|  
|AdoEnums.CursorOption.BOOKMARK|  
|AdoEnums.CursorOption.DELETE|  
|AdoEnums.CursorOption.FIND|  
|AdoEnums.CursorOption.HOLDRECORDS|  
|AdoEnums.CursorOption.INDEX|  
|AdoEnums.CursorOption.MOVEPREVIOUS|  
|AdoEnums.CursorOption.NOTIFY|  
|AdoEnums.CursorOption.RESYNC|  
|AdoEnums.CursorOption.SEEK|  
|AdoEnums.CursorOption.UPDATE|  
|AdoEnums.CursorOption.UPDATEBATCH|  
  
## <a name="applies-to"></a>适用范围  
 [Supports 方法](../../../ado/reference/ado-api/supports-method.md)
