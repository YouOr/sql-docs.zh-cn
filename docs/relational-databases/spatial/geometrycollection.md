---
title: GeometryCollection | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: spatial
ms.reviewer: ''
ms.suite: sql
ms.technology:
- dbe-spatial
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- GeomCollection geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 4445c0d9-a66b-4d7c-88e4-a66fa6f7d9fd
caps.latest.revision: 17
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: b456a13f03c547c15258f002fb78df9c9759511e
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "39552007"
---
# <a name="geometrycollection"></a>GeometryCollection
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  **GeometryCollection** 是零个或更多个 **geometry** 或 **geography** 实例的集合。 **GeometryCollection** 可以为空。  
  
## <a name="geometrycollection-instances"></a>GeometryCollection 实例  
  
### <a name="accepted-instances"></a>已接受的实例  
 要接受某个 **GeometryCollection** 实例，该实例必须为空的 **GeometryCollection** 实例或组成 **GeometryCollection** 实例的所有实例必须为接受的实例。 下面的示例显示接受的实例。  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
 下面的示例引发一个 `System.FormatException` ，因为 **GeometryCollection** 实例中的 **LinesString** 实例不是接受的实例。  
  
```  
DECLARE @g geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1), POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
### <a name="valid-instances"></a>有效实例  
 当组成 **GeometryCollection** 实例的所有实例均有效时， **GeometryCollection** 实例有效。 以下示例显示三个有效的 **GeometryCollection** 实例和一个无效的实例。  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g4 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, 1 -5, -5 5, -5 -1, -1 -1)))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 `@g4` 无效，因为 **GeometryCollection** 实例中的 **Polygon** 实例无效。  
  
 有关接受的和有效的实例的详细信息，请参阅 [Point](../../relational-databases/spatial/point.md)、 [MultiPoint](../../relational-databases/spatial/multipoint.md)、 [LineString](../../relational-databases/spatial/linestring.md)、 [MultiLineString](../../relational-databases/spatial/multilinestring.md)、 [Polygon](../../relational-databases/spatial/polygon.md)和 [MultiPolygon](../../relational-databases/spatial/multipolygon.md)。  
  
## <a name="examples"></a>示例  
 下面的示例实例化一个包含 `geometry``GeometryCollection` 实例和 `Point` 实例的 `Polygon` ，它具有 Z 值，且 SRID 为 1。  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomCollFromText('GEOMETRYCOLLECTION(POINT(3 3 1), POLYGON((0 0 2, 1 10 3, 1 0 4, 0 0 2)))', 1);  
```  
  
## <a name="see-also"></a>另请参阅  
 [空间数据 (SQL Server)](../../relational-databases/spatial/spatial-data-sql-server.md)  
  
  
