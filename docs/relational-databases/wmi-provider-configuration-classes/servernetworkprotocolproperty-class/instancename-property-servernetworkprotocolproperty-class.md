---
title: InstanceName 属性 （ServerNetworkProtocolProperty 类） |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: wmi
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- InstanceName Property (ServerNetworkProtocolProperty Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- InstanceName property
ms.assetid: b3f24bf0-6b02-496b-b08e-327f7b320bc5
caps.latest.revision: 31
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 7c85fb9bc5957b8a4b02b09a925e2324436a41e2
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "33008674"
---
# <a name="instancename-property-servernetworkprotocolproperty-class"></a>InstanceName 属性（ServerNetworkProtocolProperty 类）
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  获取安装了服务器网络协议的 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
object.InstanceName [= value]  
```  
  
## <a name="parts"></a>组成部分  
 *对象*  
 一个表示 [实例上的网络协议属性的](../../../relational-databases/wmi-provider-configuration-classes/servernetworkprotocolproperty-class/servernetworkprotocolproperty-class.md) ServerNetworkProtocolProperty 类 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]对象。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 一个指定对其安装服务器网络协议的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 实例的名称的字符串值。  
  
## <a name="remarks"></a>注释  
  
## <a name="see-also"></a>另请参阅  
 [配置服务器网络协议和网络库](http://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  
