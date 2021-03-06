---
title: 最大记录属性 (ADO) |Microsoft 文档
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
- Recordset15::MaxRecords
helpviewer_keywords:
- MaxRecords property [ADO]
ms.assetid: 20c76571-8c9a-482c-a99e-726ab1d93f8b
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b83fad35d6bc237e932dad9ed40ab2ae6f4ea279
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35279236"
---
# <a name="maxrecords-property-ado"></a>最大记录属性 (ADO)
指示要返回到的记录的最大[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)从查询。  
  
## <a name="settings-and-return-values"></a>设置和返回值  
 设置或返回**长**值，表示要返回的记录的最大数目。 默认值为零 (**0**)，这意味着没有限制。  
  
## <a name="remarks"></a>Remarks  
 使用**MaxRecords**属性可限制的提供程序从数据源返回的记录数。 此属性的默认设置为零，这意味着该提供程序返回所有请求的记录。  
  
 **MaxRecords**属性为读/写时**记录集**打开时为已关闭，只读的。  
  
## <a name="applies-to"></a>适用范围  
 [记录集对象 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>请参阅  
 [最大记录的属性示例 (VB)](../../../ado/reference/ado-api/maxrecords-property-example-vb.md)   
 [MaxRecords 属性示例 (VC++)](../../../ado/reference/ado-api/maxrecords-property-example-vc.md)   
