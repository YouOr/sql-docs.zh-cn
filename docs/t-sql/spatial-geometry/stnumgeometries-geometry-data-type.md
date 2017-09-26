---
title: "STNumGeometries (geometry 数据类型) |Microsoft 文档"
ms.custom: 
ms.date: 08/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STNumGeometries (geometry Data Type)
- STNumGeometries_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STNumGeometries (geometry Data Type)
ms.assetid: 9402b03d-3039-42ca-ac59-f96b7f1a48de
caps.latest.revision: 22
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: c8ca87eeff2f807b55754d9d9adf19ebf03a4fd8
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="stnumgeometries-geometry-data-type"></a>STNumGeometries（geometry 数据类型）
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

返回构成的几何图形数目**几何图形**实例。
  
## <a name="syntax"></a>语法  
  
```  
  
.STNumGeometries ( )  
```  
  
## <a name="return-types"></a>返回类型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]返回类型： **int**  
  
 CLR 返回类型： **SqlInt32**  
  
## <a name="remarks"></a>注释  
 如果此方法返回 1**几何图形**实例不是**MultiPoint**， **MultiLineString**， **MultiPolygon**，或**GeometryCollection**实例和 0 如果**几何图形**实例为空。  
  
> [!NOTE]  
>  如果**GeometryCollection**有嵌套的空元素，`STNumGeometries()`不会返回 0。 尽管中的元素**GeometryCollection**实例为空，该实例本身不是一个空集。  
  
  

