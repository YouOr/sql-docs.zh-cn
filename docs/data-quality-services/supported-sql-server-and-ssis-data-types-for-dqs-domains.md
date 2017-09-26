---
title: "DQS 域支持的 SQL Server 和 SSIS 数据类型 | Microsoft Docs"
ms.custom: ""
ms.date: "11/08/2011"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4931143a-b84d-478b-9b45-174128d36ed3
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# DQS 域支持的 SQL Server 和 SSIS 数据类型
  SQL Server 和 SQL Server Integration Services (SSIS) 中有很多数据类型，但是只有四种数据类型用于 DQS 域：Date、Decimal、Integer 和 String。 并非所有 SQL Server 和 SSIS 数据类型在 DQS 中都受支持。 仅当源数据类型在 DQS 中受支持且与 DQS 域数据类型匹配时，才能将源数据映射到 DQS 域来执行数据质量活动。 本主题提供有关支持的可映射到 DQS 中四种域数据类型之一的 SQL Server 和 SSIS 数据类型信息。  
  
> [!NOTE]  
>  在 .xlsx 和 .xls 文件中，源列的数据类型由前八行中最主要的数据类型确定。 如果某一单元不符合该数据类型，将向它提供 null 值。 同样，在 .csv 文件中，源列的数据类型由前八行中最主要的数据类型确定。  
  
##  <a name="SQLServer"></a> 支持的 SQL Server 数据类型  
 下表提供有关对于每种 DQS 域数据类型支持的 SQL Server 数据类型的信息：  
  
|DQS 域数据类型|支持的 SQL Server 数据类型|  
|--------------------------|------------------------------------|  
|日期|日期|  
|Decimal|Decimal<br /><br /> float<br /><br /> money<br /><br /> numeric<br /><br /> real<br /><br /> smallmoney|  
|Integer|bigint<br /><br /> int<br /><br /> smallint<br /><br /> tinyint|  
|字符串|char<br /><br /> nchar<br /><br /> nvarchar<br /><br /> varchar|  
  
 其余 SQL Server 数据类型在 DQS 中不受支持。 有关所有 SQL Server 数据类型的信息，请参阅 [数据类型和 #40;Transact SQL & #41;](../t-sql/data-types/data-types-transact-sql.md)。  
  
##  <a name="SSIS"></a> 支持的 SSIS 数据类型  
 下表提供有关对于每种 DQS 域数据类型支持的 SSIS 数据类型的信息：  
  
|DQS 域数据类型|支持的 SSIS 数据类型|  
|--------------------------|------------------------------|  
|日期|DT_DATE|  
|Decimal|DT_DECIMAL<br /><br /> DT_NUMERIC<br /><br /> DT_R4<br /><br /> DT_R8|  
|Integer|DT_I1<br /><br /> DT_I2<br /><br /> DT_I4<br /><br /> DT_I8<br /><br /> DT_U1<br /><br /> DT_U2<br /><br /> DT_U4<br /><br /> DT_U8|  
|字符串|DT_STR<br /><br /> DT_WSTR|  
  
 其余 SSIS 数据类型在 DQS 中不受支持。 有关所有 SSIS 数据类型的信息，请参阅 [Integration Services Data Types](../integration-services/data-flow/integration-services-data-types.md)。  
  
## 另请参阅  
 [管理域](../data-quality-services/managing-a-domain.md)  
  
  