---
title: 创建连接字符串 |Microsoft 文档
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [ADO]
- connection strings [ADO]
ms.assetid: 14eae122-2d1e-40c8-b88e-b7cb8dfbc93b
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 106aacb0fbdda6e00d32b42a8bae49564ee1adbc
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35270556"
---
# <a name="creating-a-connection-string"></a>创建连接字符串
连接字符串包含的自变量/值对 （即，参数），用分号分隔的列表。 例如：  
  
```  
"arg1=val1; arg2=val2; ... argN=valN;"  
```  
  
 所有参数必须都经由 ADO 或指定的提供程序。  
  
 ADO 识别的连接字符串中的以下五个自变量。  
  
|参数|Description|  
|--------------|-----------------|  
|*提供程序*|指定要用于连接提供程序的名称。|  
|*文件名*|指定的提供程序特定文件 （例如，持久化的数据源对象） 包含预设的连接信息的名称。|  
|*URL*|连接字符串指定为标识某个资源，例如文件或目录的绝对 URL。|  
|*远程提供程序*|指定要在打开的客户端连接时使用的提供程序的名称。 （仅限在远程数据服务中。）|  
|*远程服务器*|指定要在打开的客户端连接时使用的服务器的路径名称。 （仅限在远程数据服务中。）|  
  
 其他自变量传递给提供程序中名为*提供程序*自变量，而不通过 ADO 任何处理。  
  
 中的 HelloData 应用程序[HelloData： 一个简单的 ADO 应用程序](../../../ado/guide/data/hellodata-a-simple-ado-application.md)使用以下连接字符串：  
  
```  
m_sConnStr = "Provider=SQLOLEDB;Data Source=MySqlServer;" & _  
             "Initial Catalog=Northwind;Integrated Security='SSPI';"  
```  
  
 在此连接字符串，ADO 仅识别`"Provider=SQLOLEDB"`参数，指定 Microsoft OLE DB Provider for SQL Server 作为 ADO 数据源。 参数/值对，rest `"Data Source=MySqlServer; Initial Catalog=Northwind;Integrated Security='SSPI';"`，传递逐字到此提供程序。 类型和有效性的此类参数是特定于提供程序的。 可以在连接字符串中传递的有效参数信息，请查阅单个提供程序的文档。  
  
 根据 OLE DB Provider for SQL Server 文档，可替换为"Server"*数据源*参数和"数据库"，以*初始目录*参数。 因此，以下连接字符串会生成与上面相同的结果：  
  
```  
m_sConnStr = "Provider=SQLOLEDB;Server=MySqlServer;" & _  
             "Database=Northwind;Integrated Security='SSPI';"  
```
