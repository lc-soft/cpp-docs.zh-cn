---
title: 编译器警告（等级 1）C4722
ms.date: 11/04/2016
f1_keywords:
- C4722
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
ms.openlocfilehash: 320061c2daf2be042afe45828af637638399beaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327283"
---
# <a name="compiler-warning-level-1-c4722"></a>编译器警告（等级 1）C4722

“function”：析构函数永远不会返回，可能会发生内存泄漏

控制流在析构函数中终止。 该线程或整个程序将终止且分配的资源可能不会发布。  此外，如果在异常处理期间为堆栈展开调用了析构函数，则无法确定可执行文件的行为。

若要解决，请删除导致析构函数不能返回的函数调用。

## <a name="example"></a>示例

下面的示例生成 C4722：

```
// C4722.cpp
// compile with: /O1 /W1 /c
#include <stdlib.h>
class C {
public:
   C();
   ~C() { exit(1); };   // C4722
};

extern void func (C*);

void Test(){
   C x;
   func(&x);
   // control will not leave Test because destructor will exit
}
```