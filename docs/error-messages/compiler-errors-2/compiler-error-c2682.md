---
title: 编译器错误 C2682
ms.date: 11/04/2016
f1_keywords:
- C2682
helpviewer_keywords:
- C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
ms.openlocfilehash: 8a9ec2f59f362df284e9bd5cd8df6ae986d59d77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266265"
---
# <a name="compiler-error-c2682"></a>编译器错误 C2682

不能使用 casting_operator 将从 type1 转换为 type2

已尝试强制转换运算符不兼容类型之间进行转换。 例如，不能使用[dynamic_cast](../../cpp/dynamic-cast-operator.md)运算符将指针转换为引用。 `dynamic_cast`运算符不能用于转换掉限定符。 必须匹配类型上的所有限定符。

可以使用`const_cast`运算符来删除属性，如`const`， `volatile`，或`__unaligned`。

下面的示例生成 C2682:

```
// C2682.cpp
class A { virtual void f(); };
class B: public A {};

void g(A* pa) {
    B& rb = dynamic_cast<B&>(pa); // C2682
}
```

下面的示例生成 C2682:

```
// C2682b.cpp
// compile with: /clr
ref struct R{};
ref struct RR : public R{};
ref struct H {
   RR^ r ;
   short s;
   int i;
};

int main() {
   H^ h = gcnew H();
   interior_ptr<int>lr = &(h->i);
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK
}
```