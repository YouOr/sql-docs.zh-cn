---
title: 项目设置 （类型映射） (MySQLToSQL) |Microsoft 文档
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 136fdf6d-657f-447b-af41-49bbc6e0e93e
caps.latest.revision: 13
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 9bf1d1c219b8673345d5f2074fe8885b5c58223f
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34776757"
---
# <a name="project-settings-type-mapping-mysqltosql"></a>项目设置 （类型映射） (MySQLToSQL)
类型映射的项目设置，可以设置 SSMA 项目的默认类型映射。  

在项目设置和默认项目设置对话框中，类型映射将可用：  
  
-   使用项目设置对话框中设置为当前项目的配置选项。 若要访问工具菜单上的类型映射设置选择项目设置，然后单击左窗格中的类型映射。  
  
-   使用默认项目设置对话框中设置的所有项目的配置选项。 若要访问的类型映射设置，请在工具菜单中，选择默认项目设置，选择迁移项目类型的设置为需要查看 / 更改，不再是**迁移目标版本**下拉列表中，然后单击左窗格中的类型映射。  
  
## <a name="options"></a>“常规”  
  
##### <a name="source-type"></a>源类型  
它是 MySQL 数据类型，它已被映射到目标数据库数据类型。  
  
##### <a name="target-type"></a>目标类型  
目标数据库数据类型指定的 MySQL 数据类型。  
  
##### <a name="add"></a>添加  
单击此项可将数据类型添加到映射列表。  
  
##### <a name="edit"></a>编辑  
单击要编辑所选的数据类型映射列表中。  
  
##### <a name="remove"></a>删除  
单击以从映射列表中删除所选的数据类型映射。  
  
##### <a name="reset-to-default"></a>重置为默认值  
单击以将类型映射列表重置为 SSMA 默认值。  
  
## <a name="type-mappings"></a>类型映射  
下表显示源和目标数据类型之间的默认映射  
  
|||  
|-|-|  
|**MySQL 数据类型**|**SQL Server 数据类型**|  
|BIGINT|BIGINT|  
|bigint[*..255]|BIGINT|  
|BINARY|二进制 [1]|  
|binary[0..1]|二进制 [1]|  
|binary[2..255]|binary[*]|  
|bit|二进制 [1]|  
|bit[0..8]|二进制 [1]|  
|bit[17..24]|二进制文件 [3]|  
|bit[25..32]|二进制文件 [4]|  
|bit[33..40]|二进制 [5]|  
|bit[41..48]|二进制 [6]|  
|bit[49..56]|二进制 [7]|  
|bit[57..64]|二进制 [8]|  
|bit[9..16]|二进制文件 [2]|  
|blob|varbinary(max)|  
|blob[0..1]|varbinary [1]|  
|blob[2..8000]|varbinary[*]|  
|blob[8001..*]|varbinary(max)|  
|bool|bit|  
|boolean|bit|  
|char|nchar [1]|  
|char 字节|二进制 [1]|  
|char 字节 [0..1]|二进制 [1]|  
|char 字节 [2..255]|binary[*]|  
|char[0..1]|nchar [1]|  
|char[2..255]|nchar[*]|  
|character|nchar [1]|  
|字符不同 [0..1]|nvarchar [1]|  
|字符不同 [2..255]|NVARCHAR|  
|character[0..1]|nchar [1]|  
|character[2..255]|nchar[*]|  
|日期|日期|  
|DATETIME|datetime2[0]|  
|dec|Decimal|  
|dec[*..65]|decimal[*][0]|  
|dec[*..65][\*..30]|decimal[*][\*]|  
|Decimal|Decimal|  
|decimal[*..65]|decimal[*][0]|  
|decimal[*..65][\*..30]|decimal[*][\*]|  
|double|float [53]|  
|双精度|float [53]|  
|双精度 [*...255][\*..30]|numeric[*][\*]|  
|double[*..255][\*..30]|numeric[*][\*]|  
|固定|NUMERIC|  
|fixed[*..65][\*..30]|numeric[*][\*]|  
|FLOAT|float[24]|  
|float[*..255][\*..30]|numeric[*][\*]|  
|float[*..53]|float [53]|  
|ssNoversion|ssNoversion|  
|int[*..255]|ssNoversion|  
|integer|ssNoversion|  
|integer[*..255]|ssNoversion|  
|longblob|varbinary(max)|  
|长文本|nvarchar(max)|  
|mediumblob|varbinary(max)|  
|mediumint|ssNoversion|  
|mediumint[*..255]|ssNoversion|  
|mediumtext|nvarchar(max)|  
|国家/地区 char|nchar [1]|  
|国家/地区 char [0..1]|nchar [1]|  
|国家/地区 char [2..255]|nchar[*]|  
|国家/地区字符|nchar [1]|  
|不同的国家/地区字符|nvarchar [1]|  
|国家/地区字符不同 [0..1]|nvarchar [1]|  
|国家/地区字符不同 [2..4000]|nvarchar[*]|  
|不同的国家/地区字符 [4001..*]|nvarchar(max)|  
|国家/地区字符 [0..1]|nchar [1]|  
|国家/地区字符 [2..255]|nchar[*]|  
|国家/地区 varchar|nvarchar [1]|  
|国家/地区 varchar [0..1]|nvarchar [1]|  
|国家/地区 varchar [2..4000]|nvarchar[*]|  
|国家/地区 varchar [4001..*]|nvarchar(max)|  
|NCHAR|nchar [1]|  
|nchar varchar|nvarchar [1]|  
|nchar varchar [0..1]|nvarchar [1]|  
|nchar varchar [2..4000]|nvarchar[*]|  
|nchar varchar [4001..*]|nvarchar(max)|  
|nchar[0..1]|nchar [1]|  
|nchar[2..255]|nchar[*]|  
|NUMERIC|NUMERIC|  
|numeric[*..65]|numeric[*][0]|  
|numeric[*..65][\*..30]|numeric[*][\*]|  
|NVARCHAR|nvarchar [1]|  
|nvarchar[0..1]|nvarchar [1]|  
|nvarchar[2..4000]|nvarchar[*]|  
|nvarchar[4001..*]|nvarchar(max)|  
|REAL|float [53]|  
|real[*..255][\*..30]|numeric[*][\*]|  
|串行|BIGINT|  
|SMALLINT|SMALLINT|  
|smallint[*..255]|SMALLINT|  
|text|nvarchar(max)|  
|text[0..1]|nvarchar [1]|  
|text[2..4000]|nvarchar[*]|  
|text[4001..*]|nvarchar(max)|  
|time|time|  
|TIMESTAMP|DATETIME|  
|tinyblob|varbinary [255]|  
|TINYINT|SMALLINT|  
|tinyint[*..255]|SMALLINT|  
|tinytext|nvarchar[255]|  
|无符号的 bigint|BIGINT|  
|无符号的 bigint [*...255]|BIGINT|  
|无符号年 12 月|Decimal|  
|无符号的 dec [*...65]|decimal[*][0]|  
|无符号的 dec [*...65][\*..30]|decimal[*][\*]|  
|无符号的十进制数|Decimal|  
|无符号的十进制 [*...65]|decimal[*][0]|  
|无符号的十进制 [*...65][\*..30]|decimal[*][\*]|  
|无符号的双|float [53]|  
|无符号的双精度|float [53]|  
|未签名的双精度 [*...255][\*..30]|numeric[*][\*]|  
|未签名的双精度 [*...255][\*..30]|numeric[*][\*]|  
|未签名的固定|NUMERIC|  
|未签名的固定 [*...65][\*..30]|numeric[*][\*]|  
|无符号的浮点|float[24]|  
|无符号的浮点型 [*...255][\*..30]|numeric[*][\*]|  
|无符号的浮点型 [*...53]|float [53]|  
|unsigned int|BIGINT|  
|无符号的整数 [*...255]|BIGINT|  
|无符号的整数|BIGINT|  
|无符号的整数 [*...255]|BIGINT|  
|无符号的 mediumint|ssNoversion|  
|无符号的 mediumint [*...255]|ssNoversion|  
|无符号的数字|NUMERIC|  
|无符号的数值 [*...65]|numeric[*][0]|  
|无符号的数值 [*...65][\*..30]|numeric[*][\*]|  
|未签名的实际|float [53]|  
|未签名的实际 [*...255[[\*..30]|numeric[*][\*]|  
|无符号的 smallint|ssNoversion|  
|无符号的 smallint [*...255]|ssNoversion|  
|无符号的 tinyint|TINYINT|  
|无符号的 tinyint [*...255]|TINYINT|  
|varbinary[0..1]|varbinary [1]|  
|varbinary[2..8000]|varbinary[*]|  
|varbinary[8001..*]|varbinary(max)|  
|varchar[0..1]|nvarchar [1]|  
|varchar[2..4000]|nvarchar[*]|  
|varchar[4001..*]|nvarchar(max)|  
|year|SMALLINT|  
|year[2..2]|SMALLINT|  
|year[4..4]|SMALLINT|  
  
##### <a name="add"></a>添加  
单击此项可将数据类型添加到映射列表。  
  
##### <a name="edit"></a>编辑  
单击此项可编辑的映射列表中的数据类型。  
  
##### <a name="remove"></a>删除  
单击以从映射列表中删除所选的数据类型映射。  
  
##### <a name="reset-to-default"></a>重置为默认值  
单击以将所有数据类型映射重都置为 SSMA 默认值。  
  
