---
title: 编译器警告（等级 3）C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 81445ff42aca78a8e40e9c88eff4bb76a41a8669
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401873"
---
# <a name="compiler-warning-level-3-c4534"></a>编译器警告（等级 3）C4534

constructor 不会类 class 由于默认自变量的默认构造函数

非托管的类可以具有默认值的参数的构造函数，并且编译器将使用此为默认构造函数。 标记的类`value`关键字将不用作构造函数使用默认值对于其参数的默认构造函数。

有关详细信息，请参阅[类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md)。

下面的示例生成 C4534:

```
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```