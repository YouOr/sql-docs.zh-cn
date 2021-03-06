---
title: SqlXmlAdapter 对象 （SQLXML 托管类） |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- void Update(DataSet ds) method
- SqlXmlAdapter object
- void Fill(DataSet ds) method
- SQLXML Managed Classes, SqlXmlAdapter object
- Managed Classes [SQLXML], SqlXmlAdapter object
ms.assetid: 0a16eddf-fc26-4d92-82d4-359b5fb905d5
caps.latest.revision: 22
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 192f356052289725043ae2b3dc748931aedb11fd
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37331407"
---
# <a name="sqlxmladapter-object-sqlxml-managed-classes"></a>SqlXmlAdapter 对象（SQLXML 托管类）
  此对象提供用于促进与 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework 中的数据集进行交互的方法。 有关工作示例，请参阅[在.NET 环境中访问 SQLXML 功能](accessing-sqlxml-functionality-in-the-net-environment.md)。  
  
 SqlXmlAdapter 对象支持以下方法：  
  
 void Fill (DataSet ds)  
 用从 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 检索的 XML 数据填充 .NET Framework 中的数据集。  
  
 void Update (DataSet ds)  
 用数据集中的数据更新 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 中的记录。  
  
 SqlXmlAdapter 对象支持以下构造函数：  
  
```  
public SqlXmlAdapter(SqlXmlCommand  cmd)   
  
public SqlXmlAdapter(  
                     string commandText,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                      )   
  
public SqlXmlAdapter(  
                     Stream commandStream,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                     )   
```  
  
## <a name="see-also"></a>请参阅  
 [SqlXmlCommand 对象&#40;SQLXML 托管类&#41;](sqlxml-4-0-net-framework-support-managed-classes.md)   
 [SqlXmlParameter 对象&#40;SQLXML 托管类&#41;](sqlxml-managed-classes-sqlxmlparameter-object.md)  
  
  
