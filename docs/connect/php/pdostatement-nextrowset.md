---
title: 'Pdostatement:: Nextrowset |Microsoft Docs'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 048a6d8f-7fc4-449e-8161-19268c68f41d
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: fd5f05fb3f63434d134289b52d3445d749066da2
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38006459"
---
# <a name="pdostatementnextrowset"></a>PDOStatement::nextRowset
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

将光标移到下一个结果集。  
  
## <a name="syntax"></a>语法  
  
```  
  
bool PDOStatement::nextRowset();  
```  
  
## <a name="return-value"></a>返回值  
如果成功，则为 True；否则为 False。  
  
## <a name="remarks"></a>Remarks  
已在 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]的版本 2.0 中添加了对 PDO 的支持。  
  
## <a name="example"></a>示例  
  
```  
<?php  
   $server = "(local)";  
   $database = "AdventureWorks";  
   $conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
   $query1 = "select * from Person.Address where City = 'Bothell';";  
   $query2 = "select * from Person.ContactType;";  
  
   $stmt = $conn->query( $query1 . $query2 );  
  
   $rowset1 = $stmt->fetchAll();  
   $stmt->nextRowset();  
   $rowset2 = $stmt->fetchAll();  
   var_dump( $rowset1 );  
   var_dump( $rowset2 );  
?>  
```  
  
## <a name="see-also"></a>另请参阅  
[PDOStatement 类](../../connect/php/pdostatement-class.md)

[PDO](http://php.net/manual/book.pdo.php)  
  
