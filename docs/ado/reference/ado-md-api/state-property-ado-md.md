---
title: State 属性 (ADO MD) |Microsoft 文档
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
- State
- Cellset::State
helpviewer_keywords:
- State property [ADO MD]
ms.assetid: 06d480ca-9eb6-4570-a45d-a73539bddd32
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 975a9354734e0f6e5d0a2502b89b43c886be5fa3
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35284556"
---
# <a name="state-property-ado-md"></a>State 属性 (ADO MD)
指示单元集的当前状态。  
  
## <a name="return-values"></a>返回值  
 返回**长**整数，指示的当前状态[单元集](../../../ado/reference/ado-md-api/cellset-object-ado-md.md)对象，并是只读的。 以下为有效值： **adStateClosed** (0) 和**adStateOpen** (1)。  
  
## <a name="remarks"></a>Remarks  
 若要使用[ObjectStateEnum](../../../ado/reference/ado-api/objectstateenum.md)常量名，必须在你的项目中引用的 ADO 类型库。 请参阅[利用 ADO MD 使用 ADO](../../../ado/guide/multidimensional/using-ado-with-ado-md.md)有关详细信息。  
  
## <a name="applies-to"></a>适用范围  
 [单元集对象 (ADO MD)](../../../ado/reference/ado-md-api/cellset-object-ado-md.md)  
  
## <a name="see-also"></a>请参阅  
 [Close 方法 (ADO MD)](../../../ado/reference/ado-md-api/close-method-ado-md.md)   
 [Open 方法 (ADO MD)](../../../ado/reference/ado-md-api/open-method-ado-md.md)
