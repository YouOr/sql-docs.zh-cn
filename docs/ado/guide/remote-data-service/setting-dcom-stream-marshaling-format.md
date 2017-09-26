---
title: "设置 DCOM 流封送处理格式 |Microsoft 文档"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dcom stream marshaling format in rds [ADO]
ms.assetid: 46664ac5-d6e6-4457-8bae-3a98300f2a41
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: abc77e2e56ec8251e158121ca8bb6083641d4cb3
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="setting-dcom-stream-marshaling-format"></a>设置 DCOM 流格式封送处理
使用组件从 RDS 1.5 或更早版本的客户端计算机不符合使用组件从 RDS 2.0 或更高版本的服务器。 用作基础协议使用 DCOM，RDS 2.0 或更高版本的支持时，更高效地传输[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)对象。 如果你的客户端运行组件从 RDS 1.5 或更早版本，则可以设置服务器以使用以前的 RDS 支持 （称为 RDS 1.0） 或更高版本的 RDS 支持 (称为 RDS 2.0 或更高版本)。 设置以下注册表项之一：  
  
> [!IMPORTANT]
>  从 Windows 8 和 Windows Server 2012 开始，不再在 Windows 操作系统中包含 RDS 服务器组件 (请参阅 Windows 8 和[Windows Server 2012 兼容性手册](https://www.microsoft.com/en-us/download/details.aspx?id=27416)有关详细信息)。 将 Windows 的未来版本中删除 RDS 客户端组件。 请避免在新的开发工作中使用该功能，并着手修改当前还在使用该功能的应用程序。 使用 RDS 的应用程序应迁移到[WCF 数据服务](http://go.microsoft.com/fwlink/?LinkId=199565)。  
  
```  
[HKEY_CLASSES_ROOT]  
\CLSID\[58ECEE30-E715-11CF-B0E3-00AA003F000F}\ADTGOptions]"MarshalFormat"="RDS10"  
```  
  
 - 或 -  
  
```  
[HKEY_CLASSES_ROOT]  
\CLSID\[58ECEE30-E715-11CF-B0E3-00AA003F000F}\ADTGOptions]"MarshalFormat"="RDS20"  
```


