---
title: 没有名称的列 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns without
ms.assetid: 440de44e-3a56-4531-b4e4-1533ca933cac
caps.latest.revision: 10
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 723ee2f2c9d9da6665c6a9a4b530e3deb247ff2d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37292157"
---
# <a name="columns-without-a-name"></a>没有名称的列
  任何没有名称的列都将成为内联列。 例如，未指定列别名的计算列或嵌套标量查询将生成没有名称的列。 如果该列属于`xml`类型，该数据类型实例的内容插入。 否则，列内容将作为文本节点插入。  
  
```  
SELECT 2+2  
FOR XML PATH  
```  
  
 生成此 XML。 默认情况下，针对行集中的每一行，生成的 XML 中将生成一个相应的 <`row`> 元素。 这与 RAW 模式相同。  
  
 `<row>4</row>`  
  
 以下查询将返回一个包含三列的行集。 第三列没有名称，且包含 XML 数据。 PATH 模式将插入一个 xml 类型的实例。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ;  
GO  
```  
  
 下面是部分结果：  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location ...LocationID="10" ...></MI:Location>`  
  
 `<MI:Location ...LocationID="20" ...></MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a>请参阅  
 [将 PATH 模式与 FOR XML 一起使用](use-path-mode-with-for-xml.md)  
  
  
