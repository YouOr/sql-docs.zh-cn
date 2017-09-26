---
title: "创建会话作用域的计算成员 (MDX) |Microsoft 文档"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CREATE MEMBER statement
- session-scoped calculated members [MDX]
ms.assetid: 2875ed89-2c26-4645-8ed9-8848479d110f
caps.latest.revision: 30
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5da8ae05dc547de946228bb371df0b98a724ce41
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="mdx-calculated-members---session-scoped-calculated-members"></a>MDX 计算成员的会话作用域的计算成员
  若要创建在整个多维表达式 (MDX) 会话中都可用的计算成员，请使用 [CREATE MEMBER](../../../mdx/mdx-data-definition-create-member.md) 语句。 直到 MDX 会话关闭才会删除使用 CREATE MEMBER 语句创建的计算成员。  
  
 如本主题中所介绍，CREATE MEMBER 语句的语法很直观且易于使用。  
  
> [!NOTE]  
>  有关计算成员的详细信息，请参阅[在 MDX 中生成计算成员 (MDX)](../../../analysis-services/multidimensional-models/mdx/mdx-calculated-members-building-calculated-members.md)。  
  
## <a name="create-member-syntax"></a>CREATE MEMBER 语法  
 使用下列语法将 CREATE MEMBER 语句添加到 MDX 语句中：  
  
```  
CREATE [SESSION] MEMBER [<cube-name>.]<fully-qualified-member-name> AS <expression> [,<property-definition-list>]  
<cube name> ::= CURRENTCUBE | <Cube Name>  
<property-definition-list> ::= <property-definition>  
  | <property-definition>, <property-definition-list>  
<property-definition> ::= <property-identifier> = <property-value>  
<property-identifier> ::= VISIBLE | SOLVEORDER | SOLVE_ORDER | FORMAT_STRING | NON_EMPTY_BEHAVIOR <ole db member properties>  
```  
  
 在 CREATE MEMBER 语句的语法中， `fully-qualified-member-name` 值是计算成员的完全限定名。 完全限定名包含计算成员关联的维度或级别。 计算表达式值后， `expression` 值将返回计算成员的值。  
  
## <a name="create-member-example"></a>CREATE MEMBER 示例  
 下面的示例使用 CREATE MEMBER 语句创建 `LastFourStores` 计算成员。 此计算成员返回最后四家商店售出的部件总和，并且在多维数据集的整个会话中都可用。  
  
```  
Create Session Member [Store].[Measures].LastFourStores as   
sum(([Stores].[ByLocation].Lag(3) :  
[Stores].[ByLocation].NextMember), [Measures].[Units Sold])  
```  
  
## <a name="see-also"></a>另请参阅  
 [创建查询作用域的计算成员 (MDX)](../../../analysis-services/multidimensional-models/mdx/mdx-calculated-members-query-scoped-calculated-members.md)  
  
  