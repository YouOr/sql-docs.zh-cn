---
title: Analysis Services 中的数据类型 |Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 910be4f4-3010-41cd-9fdc-f0a79a0ce823
caps.latest.revision: 9
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 6554aec8cf2bac0d90276caaf9930f726f9cc3b1
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37326597"
---
# <a name="data-types-in-analysis-services"></a>Analysis Services 中的数据类型
  为所有<xref:Microsoft.AnalysisServices.DataItem>对象，[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]支持的以下子集`System.Data.OleDb.OleDbType`。 若要设置或读取的数据类型，请使用[DataItem 数据类型&#40;ASSL&#41;](../../scripting/data-type/dataitem-data-type-assl.md)。  
  
## <a name="supported-data-types"></a>支持的数据类型  
  
|||  
|-|-|  
|BigInt|64 位有符号整数。 *BigInt*值类型表示其值范围从负的 9223372036854775808 到正的 9,223,372,036,854,775,807 的整数。|  
|二进制|二进制数据的一串**字节**类型。 **字节**是值类型表示无符号的整数，其范围从 0 到 255 的值。|  
|Boolean|此类型的实例具有 `true` 或 `false` 值。|  
|货币|一个*货币*值范围从-922337203685，477.5808 到 + 922,337,203,685,477.5807 之间，精度为千分之十个货币单位 （四个小数位）。|  
|date|以双精度存储的日期和时间数据。 整数部分是自 1899 年 12 月 30 日以来的天数，而小数部分是不足一天的部分或一天中的某个时间。|  
|双精度|浮点数，范围在 -1.79769313486232E +308 到 1.79769313486232E +308 之间。 Double 值存储精度最高为 15 个小数位的数字信息。|  
|Integer|32 位有符号整数，表示其值范围在负的 2,147,483,648 到正的 2,147,483,647 之间的有符号整数。|  
|Single|浮点数，范围在 - 3.4028235E +38 到 3.4028235E +38 之间。 Single 值存储精度最高为 7 个小数位的数字信息。|  
|Smallint|16 位有符号整数。 *Smallint*值类型表示其值范围从负的 32768 到正的 32767 的有符号的整数。|  
|Tinyint|一个 8 位有符号整数。 Tinyint 值类型表示其值范围从负的 128 到正的 127 的整数。|  
|UnsignedBigInt|一个 64 位无符号整数。 *UnsignedBigInt*值类型表示其值介于 0 到 18446744073709551615 之间的无符号的整数。|  
|UnsignedInt|32 位无符号整数。 *UnsignedInt*值类型表示其值介于 0 到 4294967295 之间的无符号的整数。|  
|UnsignedSmallInt|16 位无符号整数。 *UnsignedSmallInt*值类型表示其值范围从 0 到 65535 的无符号的整数。|  
|UnsignedTinyInt|8 位无符号整数。 *UnsignedTinyInt*值类型表示无符号的整数，其范围从 0 到 255 的值|  
|WChar|Unicode 字符的以 Null 值结束的流。 一个*WChar*是用于表示文本的 Unicode 字符的有序集合。|  
  
## <a name="amo-validations-on-data-types"></a>针对数据类型的 AMO 验证  
 下表列出了分析管理对象 (AMO) 针对特定绑定执行的附加验证：  
  
|Object|Binding|允许的数据类型|  
|------------|-------------|------------------------|  
|DimensionAttribute|KeyColumns|所有（Binary 除外）|  
||NameColumn|仅 WChar|  
||SkippedLevelsColumn|仅 integer 类型：BigInt、Integer、SmallInt、TinyInt、UnsignedBigInt、UnsignedInt、UnsignedSmallInt、UnsignedTinyInt|  
||CustomRollupColumn|仅 WChar|  
||CustomRollupPropertiesColumn|仅 WChar|  
||UnaryOperatorColumn|仅 WChar|  
||ValueColumn|All|  
|AttributeTranslation|CaptionColumn|仅 WChar|  
|ScalarMiningStructureColumn|KeyColumns|所有（Binary 除外）|  
||NameColumn|仅 WChar|  
|TableMiningStructureColumn|ForeignKeyColumns|所有（Binary 除外）|  
|MeasureGroupAttribute|KeyColumns|所有（Binary 除外）|  
|非重复计数度量值|数据源|BigInt、Currency、Double、Integer、Single、SmallInt、TinyInt、UnsignedBigInt、UnsignedInt、UnsignedSmallInt、UnsignedTinyInt|  
  
  
