---
title: 向版本分配标志 (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], assigning flags
- versions [Master Data Services], assigning flags
ms.assetid: 6629ec7e-32e7-4a1e-8b31-eb43c5923766
caps.latest.revision: 5
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 1f470f23f5c84bc5a665b09d0f2f988642f75a81
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37166888"
---
# <a name="assign-a-flag-to-a-version-master-data-services"></a>向版本分配标志 (Master Data Services)
  在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]中，向版本分配标志以便指示用户或订阅系统应使用的版本。  
  
> [!NOTE]  
>  版本标志一次只能分配给一个版本。 如果您分配的标志已分配给另一个版本，则该标志将移到您选择的版本。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行此过程：  
  
-   您必须有权访问 **“版本管理”** 功能区域。  
  
-   您必须是模型管理员。 有关详细信息，请参阅[管理员 (Master Data Services)](administrators-master-data-services.md)。  
  
-   您必须已创建要分配的版本标志。 有关详细信息，请参阅[创建版本标志 (Master Data Services)](../../2014/master-data-services/create-a-version-flag-master-data-services.md)。  
  
### <a name="to-assign-a-flag-to-a-version"></a>向版本分配标志  
  
1.  在 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]中，单击 **“版本管理”**。  
  
2.  在“管理版本”页上，在与你要分配标志的版本相对应的行中，双击“标志”列中的单元格。  
  
3.  从列表中，选择要分配的标志。  
  
    > [!NOTE]  
    >  如果您想要的标志不可用，则该标志可能仅可用于 **“已提交”** 版本。 若要确认，请转到 **“管理版本标志”** 页并查看标志的 **“仅提交的版本”** 字段。  
  
4.  按 Enter 以保存更改。  
  
## <a name="see-also"></a>请参阅  
 [创建版本标志&#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md)   
 [版本&#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md)  
  
  
