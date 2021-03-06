---
title: 删除呈现扩展插件 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
caps.latest.revision: 37
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: dd559679afa7575f285737f289f66201fd06671e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37153028"
---
# <a name="removing-a-rendering-extension"></a>删除呈现扩展插件
  若要删除[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]呈现扩展插件，只需删除`Extension`元素的呈现扩展插件从 rsreportserver.config 文件中，位于 **%ProgramFiles%\Microsoft SQL Server\MSRS10_50。\<实例名称 > services\reportserver**文件夹。 如果为报表服务器或报表设计器生成条目，则删除`Extension`元素从[RSReportDesigner Configuration File](../../report-server/rsreportdesigner-configuration-file.md)也。 在删除配置信息之后，该呈现扩展插件对于该组件将不再可用。  
  
## <a name="see-also"></a>请参阅  
 [Reporting Services 配置文件](../../report-server/reporting-services-configuration-files.md)   
 [实现呈现扩展插件](implementing-a-rendering-extension.md)   
 [呈现扩展插件概述](rendering-extensions-overview.md)   
 [实现 IRenderingExtension 接口](implementing-the-irenderingextension-interface.md)   
 [扩展插件的安全注意事项](../security-considerations-for-extensions.md)   
 [部署呈现扩展插件](deploying-a-rendering-extension.md)  
  
  
