---
title: Name 属性 (ADOX) |Microsoft 文档
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Table::PutName
- _Table::GetName
- _Key::Name
- _Key::get_Name
- _Column::GetName
- _Index::Name
- _Index::put_Name
- _Column::PutName
- _Key::put_Name
- _Table::put_Name
- _User25::PutName
- _Index::get_Name
- _Column::get_Name
- _Group25::Name
- _Group25::get_Name
- _Column::Name
- _User25::get_Name
- _Table::Name
- _Group25::GetName
- _Index::PutName
- _Column::put_Name
- _Key::GetName
- _Table::get_Name
- _User25::Name
- _User25::put_Name
- _Index::GetName
- _User25::GetName
helpviewer_keywords:
- Name property [ADOX]
ms.assetid: 81b92baf-b6b9-4f4e-9f33-4503795518cd
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: a9bb6d6e570de4595e2c6b3130432b8829da137b
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35286596"
---
# <a name="name-property-adox"></a>Name 属性 (ADOX)
指示对象的名称。  
  
## <a name="settings-and-return-values"></a>设置和返回值  
 设置或返回**字符串**值。  
  
## <a name="remarks"></a>Remarks  
 不必在集合中是唯一名称。  
  
 **名称**属性为读/写上[列](../../../ado/reference/adox-api/column-object-adox.md)，[组](../../../ado/reference/adox-api/group-object-adox.md)，[密钥](../../../ado/reference/adox-api/key-object-adox.md)，[索引](../../../ado/reference/adox-api/index-object-adox.md)， [表](../../../ado/reference/adox-api/table-object-adox.md)，和[用户](../../../ado/reference/adox-api/user-object-adox.md)对象。 **名称**属性为只读上[目录](../../../ado/reference/adox-api/catalog-object-adox.md)，[过程](../../../ado/reference/adox-api/procedure-object-adox.md)，和[视图](../../../ado/reference/adox-api/view-object-adox.md)对象。  
  
 为读/写对象 (**列**，**组**，**密钥**，**索引**，**表**和**用户**对象)，默认值为空字符串 ("")。  
  
> [!NOTE]
>  对于密钥，此属性是在只读**密钥**已追加到集合的对象。 对于表，此属性是只读的**表**已追加到集合的对象。  
  
## <a name="applies-to"></a>适用范围  
  
||||  
|-|-|-|  
|[列对象 (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)|[组对象 (ADOX)](../../../ado/reference/adox-api/group-object-adox.md)|[索引对象 (ADOX)](../../../ado/reference/adox-api/index-object-adox.md)|  
|[项对象 (ADOX)](../../../ado/reference/adox-api/key-object-adox.md)|[过程对象 (ADOX)](../../../ado/reference/adox-api/procedure-object-adox.md)|[属性对象 (ADO)](../../../ado/reference/ado-api/property-object-ado.md)|  
|[表对象 (ADOX)](../../../ado/reference/adox-api/table-object-adox.md)|[用户对象 (ADOX)](../../../ado/reference/adox-api/user-object-adox.md)|[视图对象 (ADOX)](../../../ado/reference/adox-api/view-object-adox.md)|  
  
## <a name="see-also"></a>请参阅  
 [列和表追加方法名称的属性示例 (VB)](../../../ado/reference/adox-api/columns-and-tables-append-methods-name-property-example-vb.md)   
 [密钥追加方法、 密钥类型、 RelatedColumn、 RelatedTable 和 UpdateRule 属性示例 (VB)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [ParentCatalog 属性示例 (VB)](../../../ado/reference/adox-api/parentcatalog-property-example-vb.md)
