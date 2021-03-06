---
title: 数据类型元素 (ASSL) |Microsoft 文档
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 247d13565e82f2aac4175d262ecfd0f4c94e39b1
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "34037048"
---
# <a name="datatype-element-assl"></a>DataType 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  定义关联元素的数据类型。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<DataItem> <!-- or Measure -->  
   ...  
   <DataType>...</DataType>  
   ...  
</DataItem>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|说明|  
|--------------------|-----------------|  
|数据类型和长度|String（枚举）|  
|默认值|无|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[DataItem](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md)，[度量值](../../../analysis-services/scripting/objects/measure-element-assl.md)|  
|子元素|无|  
  
## <a name="remarks"></a>注释  
 值**DataType**中定义**System.Data.OleDb.OleDbType**枚举。 但是，仅在下表中的枚举值包括在中有效**DataType**元素。  
  
|“值”|Description|  
|-----------|-----------------|  
|*BigInt*|64 位有符号整数。 此数据类型映射到**Int64**中数据类型[!INCLUDE[msCoName](../../../includes/msconame-md.md)].NET Framework 和是 DBTYPE_I8 数据类型在 OLE DB。|  
|*bool*|一个布尔值。 此数据类型映射到**布尔**.NET Framework 和 OLE DB 中的 DBTYPE_BOOL 数据类型中的数据类型。|  
|*货币*|货币值，范围从-2<sup>63</sup> （或-922337203685，477.5808） 到 2<sup>63</sup>精确到货币单位的万分之一-1 （或 + 922337203685，477.5807）。 此数据类型映射到**十进制**.NET Framework 和 OLE DB 中的 DBTYPE_CY 数据类型中的数据类型。|  
|*日期*|双精度浮点数字的形式存储的日期数据。 整数部分是自 1899 年 12 月 30 日以来的天数，而小数部分是不足一天的部分。 此数据类型映射到**DateTime** .NET Framework 和 OLE DB 中的 DBTYPE_DATE 数据类型中的数据类型。|  
|*双精度*|双精度浮点数字范围是-1.79 e + 308 到 1.79 e + 308。 此数据类型映射到**Double** .NET Framework 和 OLE DB 中的 DBTYPE_R8 数据类型中的数据类型。|  
|*Integer*|32 位有符号整数。 此数据类型映射到**Int32** .NET Framework 和 OLE DB 中的 DBTYPE_I4 数据类型中的数据类型。|  
|*Single*|单精度浮点数字的-3.40 e 范围内 +38 通过 3.40 e +38。 此数据类型映射到**单个**.NET Framework 和 OLE DB 中的 DBTYPE_R4 数据类型中的数据类型。|  
|*SmallInt*|16 位有符号整数。 此数据类型映射到**Int16** .NET Framework 和 OLE DB 中的 DBTYPE_I2 数据类型中的数据类型。|  
|*TinyInt*|一个 8 位有符号整数。 此数据类型映射到**SByte** .NET Framework 和 OLE DB 中的 DBTYPE_I1 数据类型中的数据类型。|  
|*UnsignedBigInt*|一个 64 位无符号整数。 此数据类型映射到**UInt64** .NET Framework 和 OLE DB 中的 DBTYPE_UI8 数据类型中的数据类型。|  
|*unsignedInt*|32 位无符号整数。 此数据类型映射到**UInt32** .NET Framework 和 OLE DB 中的 DBTYPE_UI4 数据类型中的数据类型。|  
|*UnsignedSmallInt*|16 位无符号整数。 此数据类型映射到**UInt16** .NET Framework 和 OLE DB 中的 DBTYPE_UI2 数据类型中的数据类型。|  
|*WChar*|Unicode 字符的以 Null 值结束的流。 此数据类型映射到**字符串**.NET Framework 和 OLE DB 中的 DBTYPE_WSTR 数据类型中的数据类型。|  
|*继承*|数据类型**DataItem**中包含[源](../../../analysis-services/scripting/properties/source-element-measure-assl.md)元素**度量值**元素。<br /><br /> 注意： 仅适用于**度量值**元素。|  
  
## <a name="see-also"></a>另请参阅  
 [属性 & #40;ASSL & #41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
