---
title: 编译器警告（等级 1）C4997
ms.date: 11/04/2016
f1_keywords:
- C4997
helpviewer_keywords:
- C4997
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
ms.openlocfilehash: 298653e7ebed272db1baa11514ac5bff27944b3c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384102"
---
# <a name="compiler-warning-level-1-c4997"></a>编译器警告（等级 1）C4997

“class”：组件类不实现 COM 接口或伪接口

以 [coclass](../../windows/coclass.md) 特性标记的类不实现接口。

以下示例生成 C4997：

```
// C4997.cpp
// compile with: /WX
// to resolve this C4997, uncomment all code
#include <objbase.h>

[ object ]
__interface I {
   HRESULT func();
};

[ coclass ]
struct C /*: I*/ {
   /*
   HRESULT func() {
      return S_OK;
   }
   */
};   // C4997
```