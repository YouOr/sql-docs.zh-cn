---
title: DISCOVER_CONNECTIONS 行集 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- DISCOVER_CONNECTIONS rowset
ms.assetid: e4703970-c31d-448c-ab68-503303c91aa4
caps.latest.revision: 16
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 02c834a399f2dc6056831f2d4f84b65deb5ba503
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37194297"
---
# <a name="discoverconnections-rowset"></a>DISCOVER_CONNECTIONS 行集
  提供服务器上当前打开的连接的资源使用情况和活动信息。  
  
 **适用于：** 表格模型和多维模型  
  
## <a name="rowset-columns"></a>行集列  
 `DISCOVER_CONNECTIONS`行集包含以下列。  
  
|列名|类型指示符|限制|Description|  
|-----------------|--------------------|------------------|-----------------|  
|`CONNECTION_ID`|`DBTYPE_I4`|是|标识连接的唯一编号。|  
|`CONNECTION_USER_NAME`|`DBTYPE_WSTR`|是|连接的用户名。|  
|`CONNECTION_IMPERSONATED_USER_NAME`|`DBTYPE_WSTR`|是|保留供将来使用。 Analysis Services 始终为 CONNECTION_IMPERSONATED_USER_NAME 的值返回 NULL。|  
|`CONNECTION_HOST_NAME`|`DBTYPE_WSTR`|是|启动连接的计算机名称。|  
|`CONNECTION_HOST_APPLICATION`|`DBTYPE_WSTR`||启动连接的应用程序名称。|  
|`CONNECTION_START_TIME`|`DBTYPE_DBTIMESTAMP`||启动连接时的服务器 UTC 日期和时间。|  
|`CONNECTION_ELAPSED_TIME_MS`|`DBTYPE_I8`|是|自连接开始起经过的时间（毫秒）。|  
|`CONNECTION_LAST_COMMAND_START_TIME`|`DBTYPE_DBTIMESTAMP`||服务器 UTC 日期和最后一个命令时启动其执行时间。|  
|`CONNECTION_LAST_COMMAND_END_TIME`|`DBTYPE_DBTIMESTAMP`||上次命令执行结束时的服务器 UTC 日期和时间。|  
|`CONNECTION_LAST_COMMAND_ELAPSED_TIME_MS`|`DBTYPE_I8`|是|自上次命令执行结束后经过的时间（毫秒）。|  
|`CONNECTION_IDLE_TIME_MS`|`DBTYPE_I8`|是|自连接开始后的空闲时间（毫秒）。|  
|`CONNECTION_BYTES_SENT`|`DBTYPE_I8`||自连接开始后该连接发送的累计字节数。|  
|`CONNECTION_DATA_BYTES_SENT`|`DBTYPE_I8`||自连接开始后该连接发送的累计数据字节数。<br /><br /> 数据在连接中以压缩方式传送；此值表示解压缩后的发送数据。|  
|`CONNECTION_BYTES_RECEIVED`|`DBTYPE_I8`||自连接开始后该连接收到的累计字节数。|  
|`CONNECTION_DATA_BYTES_RECEIVED`|`DBTYPE_I8`||自连接开始后该连接收到的累计数据字节数。<br /><br /> 数据在连接中以压缩方式传送；此值表示解压缩后的接收数据。|  
  
 未对此架构行集进行排序。  
  
## <a name="using-adomdnet-to-return-the-rowset"></a>使用 ADOMD.NET 返回行集  
 在使用 ADOMD.NET 和架构行集检索元数据时，可以使用 GUID 或字符串在 GetSchemaDataSet 方法中引用架构行集对象。 有关详细信息，请参阅 [Working with Schema Rowsets in ADOMD.NET](../../../relational-databases/native-client-ole-db-rowsets/rowsets.md)。  
  
 下表提供了用于标识此行集的 GUID 和字符串值。  
  
|参数|ReplTest1|  
|--------------|-----------|  
|GUID|a07ccd25-8148-11d0-87bb-00c04fc33942|  
|ADOMDNAME|连接|  
  
## <a name="see-also"></a>请参阅  
 [XML for Analysis 架构行集](xml-for-analysis-schema-rowsets.md)  
  
  
