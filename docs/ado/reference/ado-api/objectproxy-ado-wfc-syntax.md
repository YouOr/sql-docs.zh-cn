---
title: ObjectProxy (ADO-WFC 语法) |Microsoft 文档
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
helpviewer_keywords:
- ObjectProxy collection [ADO]
ms.assetid: f68f58bc-ad28-46cc-9fb3-099e1a678397
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0ce52d661b5fffe6f0263baa81808dc7d1e9fd3b
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35279656"
---
# <a name="objectproxy-ado---wfc-syntax"></a>ObjectProxy (ADO-WFC 语法)
**ObjectProxy**对象表示的服务器，并且由返回**createObject**方法[DataSpace](../../../ado/reference/rds-api/dataspace-object-rds.md)对象。 ObjectProxy 类具有一个方法，**调用**，其可以调用服务器上的方法并返回从该调用而产生的对象。  
  
 **包 com.ms.wfc.data**  
  
## <a name="methods"></a>方法  
  
### <a name="call-method-adowfc-syntax"></a>调用方法 （ADO/WFC 语法）  
 调用由 ObjectProxy 所表示的服务器上的方法。 （可选） 可以作为对象的数组传递方法自变量。  
  
#### <a name="syntax"></a>语法  
  
```  
public Object ObjectProxy.( String method )  
public Object ObjectProxy.( String method, Object[] args)  
```  
  
#### <a name="returns"></a>返回  
 Object  
 从调用的方法而产生的对象。  
  
#### <a name="parameters"></a>Parameters  
 *ObjectProxy*  
 **ObjectProxy**表示服务器的对象。  
  
 *方法*  
 一个字符串，包含要在服务器上调用的方法的名称。  
  
 *参数*  
 可选。 在服务器上的方法参数的对象的数组。 Java 数据类型自动转换为适用于服务器上使用的数据类型。
