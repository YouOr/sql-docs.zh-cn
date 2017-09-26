---
title: "用例 (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 06/28/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CASE_TSQL
- CASE
dev_langs:
- TSQL
helpviewer_keywords:
- CASE expression [Transact-SQL]
- simple CASE expression
- comparing expressions
- searched CASE expression
ms.assetid: 658039ec-8dc2-4251-bc82-30ea23708cee
caps.latest.revision: 59
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: b366f7b6d57adbed5f028171617abb7516f3260b
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="case-transact-sql"></a>CASE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  计算条件列表，并返回多个可能的结果表达式之一。  
  
 CASE 表达式有两种格式：  
  
-   CASE 简单表达式，它通过将表达式与一组简单的表达式进行比较来确定结果。  
  
-   CASE 搜索表达式，它通过计算一组布尔表达式来确定结果。  
  
 这两种格式都支持可选的 ELSE 参数。  
  
 CASE 可用于允许使用有效表达式的任意语句或子句。 例如，可以在 SELECT、UPDATE、DELETE 和 SET 等语句以及 select_list、IN、WHERE、ORDER BY 和 HAVING 等子句中使用 CASE。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
Simple CASE expression:   
CASE input_expression   
     WHEN when_expression THEN result_expression [ ...n ]   
     [ ELSE else_result_expression ]   
END   
Searched CASE expression:  
CASE  
     WHEN Boolean_expression THEN result_expression [ ...n ]   
     [ ELSE else_result_expression ]   
END  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
CASE  
     WHEN when_expression THEN result_expression [ ...n ]   
     [ ELSE else_result_expression ]   
END  
```  
  
## <a name="arguments"></a>参数  
 *input_expression*  
 使用简单 CASE 格式时计算的表达式。 *input_expression*是任何有效[表达式](../../t-sql/language-elements/expressions-transact-sql.md)。  
  
 当*when_expression*  
 是一个简单的表达式，向其*input_expression*进行比较时使用的简单的大小写格式。 *when_expression*为任何有效表达式。 数据类型的*input_expression*和每个*when_expression*必须相同或必须是隐式转换。  
  
 然后*result_expression*  
 返回的表达式时*input_expression*等于*when_expression*计算结果为 TRUE，或*Boolean_expression*计算结果为 TRUE。 *导致表达式*是任何有效[表达式](../../t-sql/language-elements/expressions-transact-sql.md)。  
  
 其他*else_result_expression*  
 比较运算计算结果不为 TRUE 时返回的表达式。 如果忽略此参数且比较运算计算结果不为 TRUE，则 CASE 返回 NULL。 *else_result_expression*为任何有效表达式。 数据类型的*else_result_expression*和任何*result_expression*必须相同或必须是隐式转换。  
  
 当*Boolean_expression*  
 使用 CASE 搜索格式时所计算的布尔表达式。 *Boolean_expression*是任何有效的布尔表达式。  
  
## <a name="return-types"></a>返回类型  
 从的类型集中返回优先级高的类型*result_expressions*和可选*else_result_expression*。 有关详细信息，请参阅[数据类型优先级 (Transact-SQL)](../../t-sql/data-types/data-type-precedence-transact-sql.md)。  
  
### <a name="return-values"></a>返回值  
 **简单 CASE 表达式：**  
  
 CASE 简单表达式的工作方式如下：将第一个表达式与每个 WHEN 子句中的表达式进行比较，以确定它们是否等效。 如果这些表达式等效，将返回 THEN 子句中的表达式。  
  
-   仅用于等同性检查。  
  
-   在指定的顺序，将计算 input_expression = when_expression 为每个 WHEN 子句。  
  
-   返回*result_expression*的第一个*input_expression* = *when_expression*计算结果为 TRUE。  
  
-   如果没有*input_expression* = *when_expression*计算结果为 TRUE，[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]返回*else_result_expression*如果 ELSE 子句，则指定，或如果没有 ELSE 子句指定一个 NULL 值。  
  
 **搜索 CASE 表达式：**  
  
-   计算结果，按顺序指定， *Boolean_expression*为每个 WHEN 子句。  
  
-   返回*result_expression*的第一个*Boolean_expression*计算结果为 TRUE。  
  
-   如果没有*Boolean_expression*计算结果为 TRUE，[!INCLUDE[ssDE](../../includes/ssde-md.md)]返回*else_result_expression*如果指定了 ELSE 子句，或如果没有 ELSE 子句指定一个 NULL 值。  
  
## <a name="remarks"></a>注释  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 仅允许在 CASE 表达式中嵌套 10 个级别。  
  
 CASE 表达式不能用于控制 Transact-SQL 语句、语句块、用户定义函数以及存储过程的执行流。 控制流方法的列表，请参阅[控制流语言 &#40;Transact SQL &#41;](~/t-sql/language-elements/control-of-flow.md).  
  
 CASE 语句按顺序评估其条件并在满足第一个条件时停止。 在某些情况下，将会先计算表达式，然后 CASE 语句会将表达式的结果作为其输入接收。 在计算这些表达式时可能会出现错误。 首先计算在 CASE 语句的 WHEN 参数中出现的聚合表达式，然后将结果提供给 CASE 语句。 例如，下面的查询将在生成 MAX 聚合的值时生成被零除错误。 在计算 CASE 表达式之前会出现这种情况。  
  
```tsql  
WITH Data (value) AS   
(   
SELECT 0   
UNION ALL   
SELECT 1   
)   
SELECT   
   CASE   
      WHEN MIN(value) <= 0 THEN 0   
      WHEN MAX(1/value) >= 100 THEN 1   
   END   
FROM Data ;  
```  
  
 您应该仅依赖于标量表达式（包括返回标量的非相关子查询）的 WHEN 条件的计算顺序，而不应依赖于聚合表达式。  
  
## <a name="examples"></a>示例  
  
### <a name="a-using-a-select-statement-with-a-simple-case-expression"></a>A. 使用带有 CASE 简单表达式的 SELECT 语句  
 在 `SELECT` 语句中，`CASE` 简单表达式只能用于等同性检查，而不进行其他比较。 下面的示例使用 `CASE` 表达式更改产品系列类别的显示，以使这些类别更易于理解。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   ProductNumber, Category =  
      CASE ProductLine  
         WHEN 'R' THEN 'Road'  
         WHEN 'M' THEN 'Mountain'  
         WHEN 'T' THEN 'Touring'  
         WHEN 'S' THEN 'Other sale items'  
         ELSE 'Not for sale'  
      END,  
   Name  
FROM Production.Product  
ORDER BY ProductNumber;  
GO  
  
```  
  
### <a name="b-using-a-select-statement-with-a-searched-case-expression"></a>B. 使用带有 CASE 搜索表达式的 SELECT 语句  
 在 `SELECT` 语句中，`CASE` 搜索表达式允许根据比较值替换结果集中的值。 下面的示例根据产品的价格范围将标价显示为文本注释。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   ProductNumber, Name, "Price Range" =   
      CASE   
         WHEN ListPrice =  0 THEN 'Mfg item - not for resale'  
         WHEN ListPrice < 50 THEN 'Under $50'  
         WHEN ListPrice >= 50 and ListPrice < 250 THEN 'Under $250'  
         WHEN ListPrice >= 250 and ListPrice < 1000 THEN 'Under $1000'  
         ELSE 'Over $1000'  
      END  
FROM Production.Product  
ORDER BY ProductNumber ;  
GO  
  
```  
  
### <a name="c-using-case-in-an-order-by-clause"></a>C. 在 ORDER BY 子句中使用 CASE  
 下面的示例在 ORDER BY 子句中使用 CASE 表达式，以根据给定的列值确定行的排序顺序。 在第一个示例中，会计算 `SalariedFlag` 表中 `HumanResources.Employee` 列的值。 `SalariedFlag` 设置为 1 的员工将按 `BusinessEntityID` 以降序顺序返回。 `SalariedFlag` 设置为 0 的员工将按 `BusinessEntityID` 以升序顺序返回。 在第二个示例中，当 `TerritoryName` 列等于“United States”时，结果集会按 `CountryRegionName` 列排序，对于所有其他行则按 `CountryRegionName` 排序。  
  
```  
SELECT BusinessEntityID, SalariedFlag  
FROM HumanResources.Employee  
ORDER BY CASE SalariedFlag WHEN 1 THEN BusinessEntityID END DESC  
        ,CASE WHEN SalariedFlag = 0 THEN BusinessEntityID END;  
GO  
  
```  
  
```  
SELECT BusinessEntityID, LastName, TerritoryName, CountryRegionName  
FROM Sales.vSalesPerson  
WHERE TerritoryName IS NOT NULL  
ORDER BY CASE CountryRegionName WHEN 'United States' THEN TerritoryName  
         ELSE CountryRegionName END;  
  
```  
  
### <a name="d-using-case-in-an-update-statement"></a>D. 在 UPDATE 语句中使用 CASE  
 下面的示例在 UPDATE 语句中使用 CASE 表达式，以确定为 `VacationHours` 设置为 0 的员工的 `SalariedFlag` 列所设置的值。 如果 `VacationHours` 减去 10 小时后会得到一个负值，则 `VacationHours` 将增加 40 小时；否则 `VacationHours` 将增加 20 小时。 OUTPUT 子句用于显示前后的休假时间值。  
  
```  
USE AdventureWorks2012;  
GO  
UPDATE HumanResources.Employee  
SET VacationHours =   
    ( CASE  
         WHEN ((VacationHours - 10.00) < 0) THEN VacationHours + 40  
         ELSE (VacationHours + 20.00)  
       END  
    )  
OUTPUT Deleted.BusinessEntityID, Deleted.VacationHours AS BeforeValue,   
       Inserted.VacationHours AS AfterValue  
WHERE SalariedFlag = 0;  
  
```  
  
### <a name="e-using-case-in-a-set-statement"></a>E. 在 SET 语句中使用 CASE  
 下面的示例在表值函数 `dbo.GetContactInfo` 中的 SET 语句中使用 CASE 表达式。 在 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 数据库中，与人员有关的所有数据都存储在 `Person.Person` 表中。 例如，人员可能是一名员工、 供应商代表或客户。 该函数将返回的第一个和最后一个名称给定`BusinessEntityID`和该用户的联系人类型。SET 语句中的 CASE 表达式确定要显示的列的值`ContactType`基于是否存在`BusinessEntityID`中的列`Employee`， `Vendor`，或`Customer`表。  
  
```  
  
USE AdventureWorks2012;  
GO  
CREATE FUNCTION dbo.GetContactInformation(@BusinessEntityID int)  
    RETURNS @retContactInformation TABLE   
(  
BusinessEntityID int NOT NULL,  
FirstName nvarchar(50) NULL,  
LastName nvarchar(50) NULL,  
ContactType nvarchar(50) NULL,  
    PRIMARY KEY CLUSTERED (BusinessEntityID ASC)  
)   
AS   
-- Returns the first name, last name and contact type for the specified contact.  
BEGIN  
    DECLARE   
        @FirstName nvarchar(50),   
        @LastName nvarchar(50),   
        @ContactType nvarchar(50);  
  
    -- Get common contact information  
    SELECT   
        @BusinessEntityID = BusinessEntityID,   
@FirstName = FirstName,   
        @LastName = LastName  
    FROM Person.Person   
    WHERE BusinessEntityID = @BusinessEntityID;  
  
    SET @ContactType =   
        CASE   
            -- Check for employee  
            WHEN EXISTS(SELECT * FROM HumanResources.Employee AS e   
                WHERE e.BusinessEntityID = @BusinessEntityID)   
                THEN 'Employee'  
  
            -- Check for vendor  
            WHEN EXISTS(SELECT * FROM Person.BusinessEntityContact AS bec  
                WHERE bec.BusinessEntityID = @BusinessEntityID)   
                THEN 'Vendor'  
  
            -- Check for store  
            WHEN EXISTS(SELECT * FROM Purchasing.Vendor AS v            
                WHERE v.BusinessEntityID = @BusinessEntityID)   
                THEN 'Store Contact'  
  
            -- Check for individual consumer  
            WHEN EXISTS(SELECT * FROM Sales.Customer AS c   
                WHERE c.PersonID = @BusinessEntityID)   
                THEN 'Consumer'  
        END;  
  
    -- Return the information to the caller  
    IF @BusinessEntityID IS NOT NULL   
    BEGIN  
        INSERT @retContactInformation  
        SELECT @BusinessEntityID, @FirstName, @LastName, @ContactType;  
    END;  
  
    RETURN;  
END;  
GO  
  
SELECT BusinessEntityID, FirstName, LastName, ContactType  
FROM dbo.GetContactInformation(2200);  
GO  
SELECT BusinessEntityID, FirstName, LastName, ContactType  
FROM dbo.GetContactInformation(5);  
  
```  
  
### <a name="f-using-case-in-a-having-clause"></a>F. 在 HAVING 子句中使用 CASE  
 下面的示例在 HAVING 子句中使用 CASE 表达式，以限制由 SELECT 语句返回的行。 该语句返回为每个作业标题中的最大每小时速率`HumanResources.Employee`表。 HAVING 子句将职位限制为两类员工：一是最高每小时薪金超过 40 美元的男性员工，二是最高每小时薪金超过 42 美元的女性员工。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT JobTitle, MAX(ph1.Rate)AS MaximumRate  
FROM HumanResources.Employee AS e  
JOIN HumanResources.EmployeePayHistory AS ph1 ON e.BusinessEntityID = ph1.BusinessEntityID  
GROUP BY JobTitle  
HAVING (MAX(CASE WHEN Gender = 'M'   
        THEN ph1.Rate   
        ELSE NULL END) > 40.00  
     OR MAX(CASE WHEN Gender  = 'F'   
        THEN ph1.Rate    
        ELSE NULL END) > 42.00)  
ORDER BY MaximumRate DESC;  
  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="g-using-a-select-statement-with-a-case-expression"></a>G. SELECT 语句使用 CASE 表达式  
 SELECT 语句中 CASE 表达式允许在结果集中比较值为基础的替换值。 下面的示例使用 CASE 表达式来更改显示的产品行类别，以使它们更易于理解。 不存在一个值时，文本"不能为销售会显示。  
  
```  
-- Uses AdventureWorks  
  
SELECT   ProductAlternateKey, Category =  
      CASE ProductLine  
         WHEN 'R' THEN 'Road'  
         WHEN 'M' THEN 'Mountain'  
         WHEN 'T' THEN 'Touring'  
         WHEN 'S' THEN 'Other sale items'  
         ELSE 'Not for sale'  
      END,  
   EnglishProductName  
FROM dbo.DimProduct  
ORDER BY ProductKey;  
```  
  
### <a name="h-using-case-in-an-update-statement"></a>H. 在 UPDATE 语句中使用 CASE  
 下面的示例在 UPDATE 语句中使用 CASE 表达式，以确定为 `VacationHours` 设置为 0 的员工的 `SalariedFlag` 列所设置的值。 如果 `VacationHours` 减去 10 小时后会得到一个负值，则 `VacationHours` 将增加 40 小时；否则 `VacationHours` 将增加 20 小时。  
  
```  
-- Uses AdventureWorks   
  
UPDATE dbo.DimEmployee  
SET VacationHours =   
    ( CASE  
         WHEN ((VacationHours - 10.00) < 0) THEN VacationHours + 40  
         ELSE (VacationHours + 20.00)   
       END  
    )   
WHERE SalariedFlag = 0;  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [表达式 &#40;Transact SQL &#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [SELECT (Transact-SQL)](../../t-sql/queries/select-transact-sql.md)   
 [将合并 &#40;Transact SQL &#41;](../../t-sql/language-elements/coalesce-transact-sql.md)   
 [IIF &#40;Transact SQL &#41;](../../t-sql/functions/logical-functions-iif-transact-sql.md)   
 [选择 &#40;Transact SQL &#41;](../../t-sql/functions/logical-functions-choose-transact-sql.md)  
  
  



