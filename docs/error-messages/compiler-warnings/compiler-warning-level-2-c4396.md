---
title: 编译器警告（等级 2）C4396
ms.date: 11/04/2016
f1_keywords:
- C4396
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
ms.openlocfilehash: 84045ea2c285be8b1c1c9d1fd62b417db00dd29c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402445"
---
# <a name="compiler-warning-level-2-c4396"></a>编译器警告（等级 2）C4396

“name”：友元声明引用函数模板的专用化时，无法使用内联说明符

函数模板的专用化不能指定任何 [内联](../../cpp/inline-functions-cpp.md) 说明符。 编译器发出警告 C4396 并忽略内联说明符。

### <a name="to-correct-this-error"></a>更正此错误

- 从友元函数声明中删除 `inline`、 `__inline`，或 `__forceinline` 说明符。

## <a name="example"></a>示例

下面的代码示例演示了一个带有 `inline` 说明符的无效友元函数声明。

```
// C4396.cpp
// compile with: /W2 /c

class X;
template<class T> void Func(T t, int i);

class X {
    friend inline void Func<char>(char t, int i);  //C4396
// try the following line instead
//    friend void Func<char>(char t, int i);
    int i;
};
```