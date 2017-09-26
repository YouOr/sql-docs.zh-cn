---
title: "ToString (geography 数据类型) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ToString (geography Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- ToString method
ms.assetid: 045c12fa-8fc6-441a-9500-7021cb4ff13e
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 34e028dcd1a9fd141d0771e1b410d469d6dbd47c
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="tostring-geography-data-type"></a>ToString（geography 数据类型）
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  返回的开放地理空间联盟 (OGC) 熟知文本 (WKT) 表示形式**geography**扩充任何 Z （仰角） 和 M （度量） 值的实例执行的实例。  
  
 此 geography 数据类型方法支持**FullGlobe**实例或大于半球的空间实例。  
  
## <a name="syntax"></a>语法  
  
```  
  
.ToString ()  
```  
  
## <a name="return-types"></a>返回类型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]返回类型： **nvarchar (max)**  
  
 CLR 返回类型： **SqlString**  
  
## <a name="remarks"></a>注释  
 在针对 Null 实例调用时，此方法将返回字符串“Null”。 在[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]的服务器上的可能结果集已扩展到**FullGlobe**实例。 此方法将返回与 `AsTextZM()` 相同的值。  
  
 此方法不精确。  
  
## <a name="examples"></a>示例  
 下面的示例创建`LineString`实例并使用`ToString()`返回实例的文本说明。  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326);  
SELECT @g.ToString();  
```  
  
## <a name="see-also"></a>另请参阅  
 [地域实例的扩展的方法](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)   
 [AsTextZM（geography 数据类型）](../../t-sql/spatial-geography/astextzm-geography-data-type.md)  
  
  