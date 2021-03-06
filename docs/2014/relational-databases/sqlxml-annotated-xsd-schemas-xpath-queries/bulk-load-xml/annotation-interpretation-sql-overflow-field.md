---
title: sql:overflow 的字段 (SQLXML 4.0) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: f005182b-6151-432d-ab22-3bc025742cd3
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 3b78db405442ea15fe3d62db4688eb82440dfb2c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37246239"
---
# <a name="sqloverflow-field-sqlxml-40"></a>sql:overflow-field (SQLXML 4.0)
  在架构中，可以将某列标识为溢出列，以接收 XML 文档中所有未用完的数据。 通过使用 `sql:overflow-field` 批注在架构中指定此列。 可能有多个溢出列。  
  
 一旦有定义了 `sql:overflow-field` 批注的 XML 节点（元素或属性）进入了作用域，溢出列即被激活并会接收未用完的数据。 节点离开作用域时，溢出列将不再活动，XML 大容量加载将激活上一个溢出字段（如果有）。  
  
 在将数据存储在溢出列中的过程中，XML 大容量加载还会存储定义了 `sql:overflow-field` 的父元素的开始标记和结束标记。  
  
 例如，以下架构描述**\<客户 >** 并 **\<CustOrder >** 元素。 上述每个元素都标识一个溢出列：  
  
```  
<?xml version="1.0" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
 <xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
        parent="Cust"  
        parent-key="CustomerID"  
        child="CustOrder"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
 </xsd:annotation>  
 <xsd:element name="ROOT" sql:is-constant="1">  
  <xsd:complexType>  
    <xsd:sequence>   
      <xsd:element name="Customers"   
                   sql:relation="Cust"  
                   sql:overflow-field="OverflowColumn">  
        <xsd:complexType>  
             <xsd:sequence>   
             <xsd:element name="CustomerID" type="xsd:integer"/>  
             <xsd:element name="CompanyName"  type="xsd:string"/>  
             <xsd:element name="City" type="xsd:string"/>  
             <xsd:element name="Order"  
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder"  
                          sql:overflow-field="OverflowColumn">  
               <xsd:complexType>  
                 <xsd:attribute name="OrderID"/>  
                 <xsd:attribute name="CustomerID"/>  
               </xsd:complexType>  
             </xsd:element>  
          </xsd:sequence>   
        </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 在架构中， **\<客户 >** 元素映射到 Cust 表和**\<顺序 >** 元素映射到 CustOrder 表。  
  
 这两个**\<客户 >** 并**\<顺序 >** 元素标识一个溢出列。 因此，XML 大容量加载会将所有未用完的子元素和属性的**\<客户 >** Cust 表的溢出列中的元素和所有未用完的子元素和属性的**\<顺序 >** CustOrder 表的溢出列中的元素。  
  
### <a name="to-test-a-working-sample"></a>测试工作示例  
  
1.  将在该示例中提供的架构另存为 SampleSchema.xml。  
  
2.  创建这些表：  
  
    ```  
    CREATE TABLE Cust (  
              CustomerID     int         PRIMARY KEY,  
              CompanyName    varchar(20) NOT NULL,  
              City           varchar(20) DEFAULT 'Seattle',  
              OverflowColumn nvarchar(200))  
    GO  
    CREATE TABLE CustOrder (  
              OrderID        int         PRIMARY KEY,  
              CustomerID     int         FOREIGN KEY REFERENCES  
                                              Cust(CustomerID),  
              OverflowColumn nvarchar(200))  
    GO  
    ```  
  
3.  将以下示例 XML 数据另存为 SampleXMLData.xml：  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City><![CDATA[NY]]> </City>  
          <Junk>garbage in overflow</Junk>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
     </Customers>  
     <Customers>  
       <CustomerID>1112</CustomerID>  
       <CompanyName>Toms Spezialitten</CompanyName>  
       <City><![CDATA[LA]]> </City>  
       <xyz><address>111 Maple, Seattle</address></xyz>     
       <Order OrderID="3" />  
     </Customers>  
       <Customers>  
       <CustomerID>1113</CustomerID>  
       <CompanyName>Victuailles en stock</CompanyName>  
       <Order OrderID="4" />  
      </Customers>  
    </ROOT>  
    ```  
  
4.  若要执行 XML 大容量加载，将此 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) 示例另存为 Sample.vbs 并执行该示例：  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
