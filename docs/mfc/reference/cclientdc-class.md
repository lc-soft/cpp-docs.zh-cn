---
title: "CClientDC 类 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CClientDC class
- device contexts, client area
- client-area device context
- CDC class, device contexts for client areas
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 619bed4d31994bde8464ad710e9f050d6ba0696a
ms.contentlocale: zh-cn
ms.lasthandoff: 02/24/2017

---
# <a name="cclientdc-class"></a>CClientDC 类
负责调用 Windows 函数[GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)在构造时和[ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920)在析构时。  
  
## <a name="syntax"></a>语法  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|构造`CClientDC`对象连接到`CWnd`。|  
  
### <a name="protected-data-members"></a>受保护的数据成员  
  
|名称|说明|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|`HWND`此窗口的`CClientDC`是否有效。|  
  
## <a name="remarks"></a>备注  
 这意味着，与关联的设备上下文`CClientDC`对象是一个窗口的工作区。  
  
 有关详细信息`CClientDC`，请参阅[设备上下文](../../mfc/device-contexts.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>要求  
 **标头:** afxwin.h  
  
##  <a name="cclientdc"></a>CClientDC::CClientDC  
 构造`CClientDC`访问的工作区的对象[CWnd](../../mfc/reference/cwnd-class.md)指向`pWnd`。  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>参数  
 `pWnd`  
 设备上下文对象将访问其工作区窗口中。  
  
### <a name="remarks"></a>备注  
 构造函数调用 Windows 函数[GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)。  
  
 异常 (类型的`CResourceException`) 如果则会引发 Windows`GetDC`调用将失败。 设备上下文可能不可用，如果 Windows 已分配所有可用的设备上下文。 您的应用程序都可用在 Windows 下任何给定时间的五个常见显示上下文争用。  
  
### <a name="example"></a>示例  
 [!code-cpp[NVC_MFCDocView #&42;](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CClientDC::m_hWnd  
 `HWND`的`CWnd`指针，用于构造`CClientDC`对象。  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>备注  
 `m_hWnd`是一个受保护的变量。  
  
### <a name="example"></a>示例  
  请参阅示例[CClientDC::CClientDC](#cclientdc)。  
  
## <a name="see-also"></a>另请参阅  
 [MFC 示例 MDI](../../visual-cpp-samples.md)   
 [CDC 类](../../mfc/reference/cdc-class.md)   
 [层次结构图](../../mfc/hierarchy-chart.md)   
 [CDC 类](../../mfc/reference/cdc-class.md)
