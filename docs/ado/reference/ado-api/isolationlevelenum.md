---
title: IsolationLevelEnum |Microsoft 文档
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
- IsolationLevelEnum
helpviewer_keywords:
- IsolationLevelEnum enumeration [ADO]
ms.assetid: 8e17a7bc-b8a3-4ae2-b6c9-ce088ad31fdf
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8fbf9db6b578bc886862069ddc31bc07f18d673b
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35279156"
---
# <a name="isolationlevelenum"></a>IsolationLevelEnum
指定的事务的隔离级别[连接](../../../ado/reference/ado-api/connection-object-ado.md)对象。  
  
|常量|ReplTest1|Description|  
|--------------|-----------|-----------------|  
|**adXactUnspecified**|-1|指示提供程序正在使用不同的隔离级别，与指定，但无法确定级别。|  
|**adXactChaos**|16|指示，挂起的更改程度更高的隔离级别事务中不能被覆盖。|  
|**adXactBrowse**|256|指示从一个事务你可以查看未提交的更改在其他事务中。|  
|**adXactReadUncommitted**|256|与相同**adXactBrowse**。|  
|**adXactCursorStability**|4096|指示从一个事务你可以查看更改在其他事务中仅后将其提交。|  
|**adXactReadCommitted**|4096|与相同**adXactCursorStability**。|  
|**adXactRepeatableRead**|65536|指示从一个事务无法查看其他事务中所做的更改，但该再次查询可以检索新**记录集**对象。|  
|**adXactIsolated**|1048576|指示事务的进行中的其他事务的隔离。|  
|**adXactSerializable**|1048576|与相同**adXactIsolated**。|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 等效项  
 包： **com.ms.wfc.data**  
  
|常量|  
|--------------|  
|AdoEnums.IsolationLevel.UNSPECIFIED|  
|AdoEnums.IsolationLevel.CHAOS|  
|AdoEnums.IsolationLevel.BROWSE|  
|AdoEnums.IsolationLevel.READUNCOMMITTED|  
|AdoEnums.IsolationLevel.CURSORSTABILITY|  
|AdoEnums.IsolationLevel.READCOMMITTED|  
|AdoEnums.IsolationLevel.REPEATABLEREAD|  
|AdoEnums.IsolationLevel.ISOLATED|  
|AdoEnums.IsolationLevel.SERIALIZABLE|  
  
## <a name="applies-to"></a>适用范围  
 [IsolationLevel 属性](../../../ado/reference/ado-api/isolationlevel-property.md)
