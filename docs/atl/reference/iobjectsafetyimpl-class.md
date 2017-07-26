---
title: "IObjectSafetyImpl 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: cdcc008797e94988fb42fd6239603fa300a84233
ms.contentlocale: zh-cn
ms.lasthandoff: 03/31/2017

---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl 类
此类提供的默认实现`IObjectSafety`接口以允许客户端来检索和设置对象的安全级别。  
  
> [!IMPORTANT]
>  该类及其成员无法在 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]中执行的应用程序中使用。  
  
## <a name="syntax"></a>语法  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>参数  
 `T`  
 你的类，派生自`IObjectSafetyImpl`。  
  
 *dwSupportedSafety*  
 指定控件的支持的安全选项。 可以是以下值之一：  
  
- **INTERFACESAFE_FOR_UNTRUSTED_CALLER**由标识的接口[SetInterfaceSafetyOptions](#setinterfacesafetyoptions)参数`riid`应设为可安全执行脚本。  
  
- **INTERFACESAFE_FOR_UNTRUSTED_DATA**由标识的接口`SetInterfaceSafetyOptions`参数`riid`应安全的不受信任数据期间进行初始化。  
  
## <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
  
|名称|说明|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|检索对象，支持的安全选项，以及当前设置的对象的安全选项。|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|使得该对象可安全执行初始化或脚本。|  
  
### <a name="public-data-members"></a>公共数据成员  
  
|名称|说明|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|存储对象的当前安全级别。|  
  
## <a name="remarks"></a>备注  
 类`IObjectSafetyImpl`提供的默认实现`IObjectSafety`。 `IObjectSafety`接口允许客户端检索和设置对象的安全级别。 例如，web 浏览器可以调用**IObjectSafety::SetInterfaceSafetyOptions**以使控件，用于初始化安全或可安全执行脚本。  
  
 请注意，使用[IMPLEMENTED_CATEGORY](category-macros.md#implemented_category)宏与一起**CATID_SafeForScripting**和**CATID_SafeForInitializing**组件类别提供的替代方式的指定组件的安全。  
  
 **相关文章** [ATL 教程](../../atl/active-template-library-atl-tutorial.md)，[创建 ATL 项目](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>要求  
 **标头︰** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions  
 检索对象，支持的安全选项，以及当前设置的对象的安全选项。  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>备注  
 实现返回适当的值的支持的对象的实现任何接口**iunknown:: Queryinterface**。  
  
> [!IMPORTANT]
>  支持的任何对象`IObjectSafety`负责自己的安全性，和，则委托任何对象。 程序员必须考虑在用户的上下文中运行代码时产生的帐户问题、 跨站点脚本和执行适合区域检查。  
  
 请参阅[IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety  
 存储对象的当前安全级别。  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterfaceSafetyOptions  
 使对象初始化或通过设置脚本编写安全[m_dwCurrentSafety](#m_dwcurrentsafety)为适当的值的成员。  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>备注  
 实现返回**E_NOINTERFACE**不支持的对象的实现任何接口**iunknown:: Queryinterface**。  
  
> [!IMPORTANT]
>  支持的任何对象`IObjectSafety`负责自己的安全性，和，则委托任何对象。 程序员必须考虑在用户的上下文中运行代码时产生的帐户问题、 跨站点脚本和执行适合区域检查。  
  
 请参阅[IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
## <a name="see-also"></a>另请参阅  
 [IObjectSafety 接口](https://msdn.microsoft.com/library/aa768224.aspx)   
 [类概述](../../atl/atl-class-overview.md)
