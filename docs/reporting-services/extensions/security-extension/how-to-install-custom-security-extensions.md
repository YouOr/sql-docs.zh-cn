---
title: "如何安装自定义安全扩展 |Microsoft 文档"
ms.custom: 
ms.date: 04/18/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: bfa0a35b-ccfb-4279-bae6-106c227c5f16
caps.latest.revision: 3
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: e7058e9c0edce2b457dc63bf9e2d5cf61b6ee64f
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="how-to-install-custom-security-extensions"></a>如何安装自定义安全扩展插件
Reporting Services 2016 引入的新的 web 门户，以承载新的 Odata Api 和也承载新的报表工作负荷，如移动报表和 KPI。 此新门户依赖于较新的技术，并且是独立于熟悉 ReportingServicesService 通过在单独的进程中运行。 此过程不是托管的 ASP.NET 应用程序，这种情况下中断从现有的自定义安全扩展的假设。 此外，不允许自定义安全扩展插件的当前接口要传入的任何外部上下文，离开实施者只能选择要检查的已知全局 ASP.NET 对象，这需要对接口进行一些更改。

## <a name="what-changed"></a>发生什么变化？

引入新接口，可实现提供 IRSRequestContext 提供扩展用于决定与身份验证相关的更常见属性。
    
在以前版本中，报表管理器已前端和曾经可以使用自己的自定义登录页配置。 在 Reporting Services 2016，只有一个报表服务器所托管的页面支持，并且应该对这两个应用程序进行身份验证。

## <a name="implementation"></a>实现
在早期版本中，扩展可能依赖于 ASP.NET 对象将可随时提供一个常见假设。 由于新门户并非运行在 ASP.NET，扩展可能正在 NULL 的对象与命中问题。
    
大多数泛型示例访问 HttpContext.Current 读取请求的信息，如标头和 cookie。 若要允许扩展做出相同的决策我们引入了扩展，它提供请求信息并从门户进行身份验证时，将调用中的新方法。 
    
扩展需要实现<xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension2>为了利用此接口。 扩展需要实现这两个版本<xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A>方法，如由 reportserver 上下文和其他在 webhost 过程中使用。 下面的示例演示一个位置通过 reportserver 解决了标识，则使用门户的简单实现。

``` 
      public void GetUserInfo(IRSRequestContext requestContext, out IIdentity userIdentity, out IntPtr userId)
      {
           userIdentity = null;
           if (requestContext.User != null)
           {
               userIdentity = requestContext.User;
           }

          // initialize a pointer to the current user id to zero
           userId = IntPtr.Zero;
      }
```

## <a name="deployment-and-configuration"></a>部署和配置
基本配置所需的自定义安全扩展插件是以前的版本相同。 有关 web.config 和 rsreportserver.config 需要更改： 有关详细信息，请参阅[配置自定义或报表服务器上的窗体身份验证](../../../reporting-services/security/configure-custom-or-forms-authentication-on-the-report-server.md)。
    
不再单独 web.config 为报表管理器中，门户将继承与 reportserver 终结点相同的设置。

## <a name="machine-keys"></a>计算机密钥

对于需要身份验证 cookie 解密窗体身份验证的情况下，这两个过程需要使用相同的计算机密钥和解密算法进行配置。 这是熟悉为那些具有以前安装的 Reporting Services，用于向外扩展的环境中，但现在即使对于一台计算机上的部署是必需的步骤。

例如：
    
**\ReportServer\web.config**

添加下`<system.web>`。
    
```
    <machineKey validationKey="[YOUR KEY]" decryptionKey=="[YOUR KEY]" validation="AES" decryption="AES" />
```

**\RSWebApp\Microsoft.ReportingServices.Portal.WebHost.exe.config**

添加下`<configuration>`。

```
    <system.web>
        <machineKey validationKey=="[YOUR KEY]" decryptionKey=="[YOUR KEY]" validation="AES" decryption="AES" />
    </system.web>
```

应使用为您的部署特定的验证密钥，有几种工具来生成密钥如 Internet 信息服务管理器 (IIS)。 在 internet 上找不到其他工具。

## <a name="configure-passthrough-cookies"></a>配置传递 cookie

新的门户和 reportserver 进行通信的某些操作 （类似于以前版本的报表管理器） 使用内部 soap Api。 从门户传递到服务器所需的其他 cookie PassThroughCookies 属性时，仍然可用。 有关详细信息，请参阅[配置 Web 门户来传递自定义身份验证 Cookie](../../../reporting-services/security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)。

```
<UI>
   <CustomAuthenticationUI>
      <PassThroughCookies>
         <PassThroughCookie>sqlAuthCookie</PassThroughCookie>
      </PassThroughCookies>
   </CustomAuthenticationUI>
</UI>
```

## <a name="see-also"></a>另请参阅

[报表服务器上配置自定义或窗体身份验证](../../../reporting-services/security/configure-custom-or-forms-authentication-on-the-report-server.md)  
[配置报表管理器以便传递自定义身份验证 Cookie](https://msdn.microsoft.com/library/ms345241(v=sql.120).aspx)