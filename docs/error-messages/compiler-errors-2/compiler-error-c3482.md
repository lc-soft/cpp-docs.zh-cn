---
title: 编译器错误 C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 6ff269d719dd354932ef79946ae99a9b60490199
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173218"
---
# <a name="compiler-error-c3482"></a>编译器错误 C3482

“this”只能在非静态成员函数中用作 lambda 捕获

不能将 `this` 传递至在静态方法或全局函数中声明的 lambda 表达式的捕获列表中。

### <a name="to-correct-this-error"></a>更正此错误

- 将封闭函数转换为非静态方法，或

- 从 lambda 表达式的捕获列表中删除 `this` 指针。

## <a name="example"></a>示例

以下示例生成 C3482：

```
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>请参阅

[Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)