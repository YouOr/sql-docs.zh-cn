---
title: GetString 方法 (ADO) |Microsoft 文档
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
- Recordset20::raw_GetString
- Recordset20::GetString
helpviewer_keywords:
- GetString method [ADO]
ms.assetid: 92452940-b2a7-456e-94fc-3780c71da33c
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 824ad1a3223538e724e4430186dcf176e86617a2
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35278876"
---
# <a name="getstring-method-ado"></a>GetString 方法 (ADO)
返回[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)作为字符串。  
  
## <a name="syntax"></a>语法  
  
```  
  
Variant = recordset.GetString(StringFormat, NumRows, ColumnDelimiter, RowDelimiter, NullExpr)  
```  
  
## <a name="return-value"></a>返回值  
 返回**记录集**作为字符串值**Variant** (BSTR)。  
  
#### <a name="parameters"></a>Parameters  
 *StringFormat*  
 A [StringFormatEnum](../../../ado/reference/ado-api/stringformatenum.md)值，该值指定如何**记录集**应转换为字符串。 *RowDelimiter*， *ColumnDelimiter*，和*NullExpr*参数仅用于*StringFormat*的**adClipString**。  
  
 *NumRows*  
 可选。 要转换中的行数**记录集**。 如果*NumRows*未指定，或如果它大于中的行总数**记录集**，然后中的所有行**记录集**转换。  
  
 *columnDelimiter*  
 可选。 使用列，如果指定，否则 TAB 字符之间的分隔符。  
  
 *RowDelimiter*  
 可选。 使用行，如果指定，否则回车字符之间的分隔符。  
  
 *NullExpr*  
 可选。 如果指定，否则为空字符串来代替 null 值，用的表达式。  
  
## <a name="remarks"></a>Remarks  
 行数据，但没有架构数据将保存到字符串中。 因此，**记录集**无法使用此字符串重新打开。  
  
 此方法相当于 RDO **GetClipString**方法。  
  
## <a name="applies-to"></a>适用范围  
 [记录集对象 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>请参阅  
 [GetString 方法示例 (VB)](../../../ado/reference/ado-api/getstring-method-example-vb.md)
