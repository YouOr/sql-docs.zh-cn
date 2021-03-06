---
title: 模式属性 (ADO) |Microsoft 文档
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
- Connection15::Mode
- _Stream::Mode
- _Record::Mode
helpviewer_keywords:
- Mode property [ADO]
ms.assetid: 808661eb-0d7c-4e6d-8e40-9dc3bef3d77a
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 5122d4587674e643090b4291fb3487322d9f71c0
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35279346"
---
# <a name="mode-property-ado"></a>模式属性 (ADO)
指示在中修改数据的可用权限[连接](../../../ado/reference/ado-api/connection-object-ado.md)，[记录](../../../ado/reference/ado-api/record-object-ado.md)，或[流](../../../ado/reference/ado-api/stream-object-ado.md)对象。  
  
## <a name="settings-and-return-values"></a>设置和返回值  
 设置或返回[ConnectModeEnum](../../../ado/reference/ado-api/connectmodeenum.md)值。 默认值为**连接**是**adModeUnknown**。 默认值为**记录**对象是**adModeRead**。 默认值为**流**与基础源关联 (使用 URL 作为源，或为默认打开**流**的**记录**) 是**adModeRead**。 默认值为**流**不与基础相关联 （在内存中实例化） 的源是**adModeUnknown**。  
  
## <a name="remarks"></a>Remarks  
 使用**模式**属性来设置或返回提供程序当前连接上使用的访问权限。 你可以设置**模式**属性仅当**连接**对象已关闭。  
  
 有关**流**对象，如果未指定访问模式，它从用来打开的源继承**流**对象。 例如，如果**流**从打开**记录**对象，默认情况下与相同的模式打开**记录**。  
  
 虽然该对象是已关闭，只读的该对象处于打开状态时，此属性是读/写。  
  
> [!NOTE]
>  **远程数据服务使用情况**时在客户端上使用**连接**对象，**模式**属性只能设置为**adModeUnknown**。  
  
## <a name="applies-to"></a>适用范围  
  
||||  
|-|-|-|  
|[连接对象 (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)|[记录对象 (ADO)](../../../ado/reference/ado-api/record-object-ado.md)|[流对象 (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)|  
  
## <a name="see-also"></a>请参阅  
 [IsolationLevel 和模式属性示例 (VB)](../../../ado/reference/ado-api/isolationlevel-and-mode-properties-example-vb.md)   
 [IsolationLevel 和模式属性示例 （VC + +）](../../../ado/reference/ado-api/isolationlevel-and-mode-properties-example-vc.md)   
