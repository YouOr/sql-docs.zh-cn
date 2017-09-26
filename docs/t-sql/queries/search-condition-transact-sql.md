---
title: "搜索条件 (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 08/09/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- search
- Search Condition
- condition
dev_langs:
- TSQL
helpviewer_keywords:
- OR operator [Transact-SQL]
- CONTAINS predicate (Transact-SQL)
- ESCAPE keyword
- operators [Transact-SQL], search condition
- search conditions [SQL Server]
- WHERE clause, search conditions
- ALL keyword
- FREETEXT predicate (Transact-SQL)
- EXISTS keyword
- search conditions [SQL Server], about search conditions
- NOT operator [Transact-SQL]
- BETWEEN operator
- SOME | ANY keyword
- predicates [full-text search]
- AND, about search conditions
- logical operators [SQL Server], about search conditions
- precedence [SQL Server], logical operators
- logical operators [SQL Server], precedence
- LIKE comparisons
ms.assetid: 09974469-c5d2-4be8-bc5a-78e404660b2c
caps.latest.revision: 43
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: fa99ed46f0d5248f2cb0552a62ec1547d5b4f296
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="search-condition-transact-sql"></a>搜索条件 (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  使用逻辑运算符 AND、OR 和 NOT 的一个或多个谓词的组合。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
<search_condition> ::=   
    { [ NOT ] <predicate> | ( <search_condition> ) }   
    [ { AND | OR } [ NOT ] { <predicate> | ( <search_condition> ) } ]   
[ ,...n ]   
  
<predicate> ::=   
    { expression { = | < > | ! = | > | > = | ! > | < | < = | ! < } expression   
    | string_expression [ NOT ] LIKE string_expression   
  [ ESCAPE 'escape_character' ]   
    | expression [ NOT ] BETWEEN expression AND expression   
    | expression IS [ NOT ] NULL   
    | CONTAINS   
  ( { column | * } , '<contains_search_condition>' )   
    | FREETEXT ( { column | * } , 'freetext_string' )   
    | expression [ NOT ] IN ( subquery | expression [ ,...n ] )   
    | expression { = | < > | ! = | > | > = | ! > | < | < = | ! < }   
  { ALL | SOME | ANY} ( subquery )   
    | EXISTS ( subquery )     }   
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
< search_condition > ::=   
    { [ NOT ] <predicate> | ( <search_condition> ) }   
    [ { AND | OR } [ NOT ] { <predicate> | ( <search_condition> ) } ]   
[ ,...n ]   
  
<predicate> ::=   
    { expression { = | < > | ! = | > | > = | < | < = } expression   
    | string_expression [ NOT ] LIKE string_expression   
    | expression [ NOT ] BETWEEN expression AND expression   
    | expression IS [ NOT ] NULL   
    | expression [ NOT ] IN (subquery | expression [ ,...n ] )   
    | expression [ NOT ] EXISTS (subquery)     }   
```  
  
## <a name="arguments"></a>参数  
 \<search_condition >  
 指定要在 SELECT 语句、查询表达式或子查询的结果集中返回的行的条件。 对于 UPDATE 语句，指定要更新的行。 对于 DELETE 语句，指定要删除的行。 [!INCLUDE[tsql](../../includes/tsql-md.md)] 语句搜索条件中可以包含任意多个谓词。  
  
 NOT  
 对谓词指定的布尔表达式求反。 有关详细信息，请参阅[不 &#40;Transact SQL &#41;](../../t-sql/language-elements/not-transact-sql.md).  
  
 和  
 组合两个条件，并在两个条件都为 TRUE 时取值为 TRUE。 有关详细信息，请参阅[AND &#40;Transact SQL &#41;](../../t-sql/language-elements/and-transact-sql.md).  
  
 或  
 组合两个条件，并在任何一个条件为 TRUE 时取值为 TRUE。 有关详细信息，请参阅[或者 &#40;Transact SQL &#41;](../../t-sql/language-elements/or-transact-sql.md).  
  
 \<谓词 >  
 返回 TRUE、FALSE 或 UNKNOWN 的表达式。  
  
 *expression*  
 列名、常量、函数、变量、标量子查询，或者是通过运算符或子查询连接的列名、常量和函数的任意组合。 表达式还可以包含 CASE 表达式。  
  
> [!NOTE]  
>  引用的 Unicode 字符数据类型时**nchar**， **nvarchar**，和**ntext**，expression 应前缀为大写字母 ' N '。 如果未指定“N”，则 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 会将字符串转换为与数据库或列的默认排序规则相对应的代码页。 此代码页中没有的字符都将丢失。  
  
 =  
 用于测试两个表达式是否相等的运算符。  
  
 <>  
 用于测试两个表达式是否彼此不相等的运算符。  
  
 !=  
 用于测试两个表达式是否彼此不相等的运算符。  
  
 \>  
 用于测试一个表达式是否大于另一个表达式的运算符。  
  
 \>=  
 用于测试一个表达式是否大于或等于另一个表达式的运算符。  
  
 !>  
 用于测试一个表达式是否不大于另一个表达式的运算符。  
  
 <  
 用于测试一个表达式是否小于另一个表达式的运算符。  
  
 <=  
 用于测试一个表达式是否小于或等于另一个表达式的运算符。  
  
 !<  
 用于测试一个表达式是否不小于另一个表达式的运算符。  
  
 *string_expression*  
 字符串和通配符。  
  
 [ NOT ] LIKE  
 指示后续字符串使用时要进行模式匹配。 有关详细信息，请参阅[如 &#40;Transact SQL &#41;](../../t-sql/language-elements/like-transact-sql.md).  
  
 转义*escape_ 字符*  
 允许在字符串中搜索通配符，而不是将其作为通配符使用。 *escape_character*是放置要指明此特殊用途的通配符字符的前面的字符。  
  
 [ NOT ] BETWEEN  
 指定值的包含范围。 使用 AND 分隔开始值和结束值。 有关详细信息，请参阅[BETWEEN &#40;Transact SQL &#41;](../../t-sql/language-elements/between-transact-sql.md).  
  
 IS [NOT] NULL  
 根据使用的关键字，指定是否搜索空值或非空值。 如果有任何一个操作数为 NULL，则包含位运算符或算术运算符的表达式的计算结果为 NULL。  
  
 CONTAINS  
 搜索包含基于字符的精确或不太精确的数据列 (*模糊*) 到单个词和短语，另一个，和加权匹配项的一定范围之内的词的邻近匹配。 此选项只能与 SELECT 语句一起使用。 有关详细信息，请参阅[CONTAINS &#40;Transact SQL &#41;](../../t-sql/queries/contains-transact-sql.md).  
  
 FREETEXT  
 在包含基于字符的数据的列中，搜索与谓词中的词的含义相符而非精确匹配的值，从而提供一种形式简单的自然语言查询。 此选项只能与 SELECT 语句一起使用。 有关详细信息，请参阅[FREETEXT &#40;Transact SQL &#41;](../../t-sql/queries/freetext-transact-sql.md).  
  
 [ NOT ] IN  
 根据是在列表中包含还是排除某表达式，指定对该表达式的搜索。 搜索表达式可以是常量或列名，而列表可以是一组常量，更常用的是子查询。 将一组值用圆括号括起来。 有关详细信息，请参阅[IN &#40;Transact SQL &#41;](../../t-sql/language-elements/in-transact-sql.md).  
  
 *子查询*  
 就被认为是受限制的 SELECT 语句，它类似于\<query_expresssion > SELECT 语句中。 不允许使用 ORDER BY 子句和 INTO 关键字。 有关详细信息，请参阅[选择 &#40;Transact SQL &#41;](../../t-sql/queries/select-transact-sql.md).  
  
 ALL  
 与比较运算符和子查询一起使用。 返回时为 TRUE，\<谓词 > 当子查询检索到的所有值都满足的比较操作，或 FALSE 时并不是所有的值都满足比较或当子查询在外部语句中返回了任何行。 有关详细信息，请参阅[所有 &#40;Transact SQL &#41;](../../t-sql/language-elements/all-transact-sql.md).  
  
 { SOME | ANY }  
 与比较运算符和子查询一起使用。 返回时为 TRUE，\<谓词 > 任何中检索值时为子查询满足的比较操作，或 FALSE 时，子查询中的任何值满足比较或当子查询在外部语句中返回了任何行。 其他情况下，表达式为 UNKNOWN。 有关详细信息，请参阅[一些 &#124;任何 &#40;Transact SQL &#41;](../../t-sql/language-elements/some-any-transact-sql.md).  
  
 EXISTS  
 与子查询一起使用，用于测试是否存在子查询返回的行。 有关详细信息，请参阅[EXISTS &#40;Transact SQL &#41;](../../t-sql/language-elements/exists-transact-sql.md).  
  
## <a name="remarks"></a>注释  
 逻辑运算符的优先顺序是 NOT（最高），然后是 AND，最后是 OR。 不过，可以在搜索条件内使用括号来表示优于此优先顺序的运算符。 根据查询优化器所做的选择，逻辑运算符的求值顺序可能有所不同。 有关逻辑运算符中如何工作的逻辑值的详细信息，请参阅[AND &#40;Transact SQL &#41;](../../t-sql/language-elements/and-transact-sql.md)，[或者 &#40;Transact SQL &#41;](../../t-sql/language-elements/or-transact-sql.md)，和[不 &#40;Transact SQL &#41;](../../t-sql/language-elements/not-transact-sql.md).  
  
## <a name="examples"></a>示例  
  
### <a name="a-using-where-with-like-and-escape-syntax"></a>A. 在 WHERE 中使用 LIKE 和 ESCAPE 语法  
 下面的示例将搜索以下行，其中的 `LargePhotoFileName` 列包含字符 `green_`；由于 `ESCAPE` 是通配符，因此使用了 `_` 选项。 如果不指定 `ESCAPE` 选项，则查询搜索到的任何说明值中将包含后跟一个非 `green` 字符的 `_` 一词。  
  
```  
USE AdventureWorks2012 ;  
GO  
SELECT *   
FROM Production.ProductPhoto  
WHERE LargePhotoFileName LIKE '%greena_%' ESCAPE 'a' ;  
```  
  
### <a name="b-using-where-and-like-syntax-with-unicode-data"></a>B. 对 Unicode 数据使用 WHERE 和 LIKE 语法  
 下面的示例将使用 `WHERE` 子句检索美国 (`US`) 以外且所在城市的名称以 `Pa` 开头的所有公司的邮件地址。  
  
```  
USE AdventureWorks2012 ;  
GO  
SELECT AddressLine1, AddressLine2, City, PostalCode, CountryRegionCode    
FROM Person.Address AS a  
JOIN Person.StateProvince AS s ON a.StateProvinceID = s.StateProvinceID  
WHERE CountryRegionCode NOT IN ('US')  
AND City LIKE N'Pa%' ;  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="c-using-where-with-like"></a>C. 与 LIKE 一起使用的位置  
 下面的示例搜索中行`LastName`列包含字符`and`。  
  
```  
-- Uses AdventureWorks  
  
SELECT EmployeeKey, LastName  
FROM DimEmployee  
WHERE LastName LIKE '%and%';  
```  
  
### <a name="d-using-where-and-like-syntax-with-unicode-data"></a>D. 对 Unicode 数据使用 WHERE 和 LIKE 语法  
 下面的示例使用`WHERE`子句，以执行 Unicode 搜索`LastName`列。  
  
```  
-- Uses AdventureWorks  
  
SELECT EmployeeKey, LastName  
FROM DimEmployee  
WHERE LastName LIKE N'%and%';  
```  
  
## <a name="see-also"></a>另请参阅  
 [聚合函数 &#40;Transact SQL &#41;](../../t-sql/functions/aggregate-functions-transact-sql.md)   
 [用例 &#40;Transact SQL &#41;](../../t-sql/language-elements/case-transact-sql.md)   
 [CONTAINSTABLE (Transact-SQL)](../../relational-databases/system-functions/containstable-transact-sql.md)   
 [游标 (Transact-SQL)](../../t-sql/language-elements/cursors-transact-sql.md)   
 [DELETE (Transact-SQL)](../../t-sql/statements/delete-transact-sql.md)   
 [表达式 &#40;Transact SQL &#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [FREETEXTTABLE (Transact-SQL)](../../relational-databases/system-functions/freetexttable-transact-sql.md)   
 [FROM (Transact-SQL)](../../t-sql/queries/from-transact-sql.md)   
 [运算符 &#40;Transact SQL &#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [UPDATE (Transact-SQL)](../../t-sql/queries/update-transact-sql.md)  
  
  

