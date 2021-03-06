---
title: DISCOVER_XML_METADATA 行集 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- DISCOVER_XML_METADATA
topic_type:
- apiref
helpviewer_keywords:
- DISCOVER_XML_METADATA rowset
ms.assetid: 0befd026-db1b-43ac-b0e6-734abb56a4b1
caps.latest.revision: 40
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 616e7c06087fff3d2c2e0388ba44a3e30b200e5f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37214007"
---
# <a name="discoverxmlmetadata-rowset"></a>DISCOVER_XML_METADATA 行集
  返回描述请求的对象的 XML 文档。 返回的行集始终包含一行和一列。  
  
 如果您调用[Discover](../../xmla/xml-elements-methods-discover.md)方法替换`DISCOVER_XML_METATDATA`中的枚举值[RequestType](../../xmla/xml-elements-properties/type-element-xmla.md)元素，`Discover`方法将返回`DISCOVER_XML_METATDATA`行集。  
  
## <a name="rowset-columns"></a>行集列  
 `DISCOVER_XML_METADATA` 行集包含以下列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|`METADATA`|`DBTYPE_WSTR`||描述限制所请求对象的 XML 文档。|  
  
 未对此架构行集进行排序。  
  
> [!IMPORTANT]  
>  不能使用 SELECT 命令语法查询 `DISCOVER_XML_METADATA` 行集。 但是，可以使用 <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A> 查询 `DISCOVER_XML_METADATA` 行集。  
  
## <a name="restriction-columns"></a>限制列  
 `DISCOVER_XML_METADATA`行集可以限制下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|`DatabaseID`|`DBTYPE_WSTR`|可选。|  
|`DimensionID`|`DBTYPE_WSTR`|可选。|  
|`CubeID`|`DBTYPE_WSTR`|可选。|  
|`MeasureGroupID`|`DBTYPE_WSTR`|可选。|  
|`PartitionID`|`DBTYPE_WSTR`|可选。|  
|`PerspectiveID`|`DBTYPE_WSTR`|可选。|  
|`DimensionPermissionID`|`DBTYPE_WSTR`|可选。|  
|`RoleID`|`DBTYPE_WSTR`|可选。|  
|`DatabasePermissionID`|`DBTYPE_WSTR`|可选。|  
|`MiningModelID`|`DBTYPE_WSTR`|可选。|  
|`MiningModelPermissionID`|`DBTYPE_WSTR`|可选。|  
|`DataSourceID`|`DBTYPE_WSTR`|可选。|  
|`MiningStructureID`|`DBTYPE_WSTR`|可选。|  
|`AggregationDesignID`|`DBTYPE_WSTR`|可选。|  
|`TraceID`|`DBTYPE_WSTR`|可选。|  
|`MiningStructurePermissionID`|`DBTYPE_WSTR`|可选。|  
|`CubePermissionID`|`DBTYPE_WSTR`|可选。|  
|`AssemblyID`|`DBTYPE_WSTR`|可选。|  
|`MdxScriptID`|`DBTYPE_WSTR`|可选。|  
|`DataSourceViewID`|`DBTYPE_WSTR`|可选。|  
|`DataSourcePermissionID`|`DBTYPE_WSTR`|可选。|  
|`ObjectExpansion`|`DBTYPE_WSTR`|可选。|  
  
 此限制， `ObjectExpansion`，可用于的每个主要对象[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]。 客户端通常使用限制来描述要为其返回 DLL 的 OLAP 对象，并使用 `ObjectExpansion` 限制来定义返回的 DLL 中扩展的程度。 下表指示是否允许枚举值[Alter 元素&#40;XMLA&#41; ](../../xmla/xml-elements-commands/alter-element-xmla.md)命令。  
  
|枚举值|Description|  
|-----------------------|-----------------|  
|`ReferenceOnly`|只返回对所请求对象及其所有递归后代主要对象请求的名称/ID/时间戳/状态。|  
|`ObjectProperties`|展开请求的对象，且不引用包含的对象（包括展开的次要所包含对象）。|  
|`ExpandObject`|与相同*ObjectProperties*，但也会返回名称、 ID 和所包含主要对象的时间戳。|  
|`ExpandFull`|以递归方式将请求的对象完全展开，直至每个所包含对象的最底层。|  
  
## <a name="see-also"></a>请参阅  
 [XML for Analysis 架构行集](xml-for-analysis-schema-rowsets.md)  
  
  
