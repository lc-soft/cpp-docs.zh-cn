---
title: 可变参数宏
ms.date: 08/29/2019
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: 171ea797adc1e407a8b7ef0592508653f758df64
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216516"
---
# <a name="variadic-macros"></a>可变参数宏

可变参数宏是类似于函数的宏, 其中包含可变数量的参数。

## <a name="remarks"></a>备注

若要使用可变参数宏, 可以在宏定义中将省略号指定为最后一个形参, 并且可以在定义中使用`__VA_ARGS__`替换标识符来插入额外参数。  `__VA_ARGS__`替换为与省略号匹配的所有参数, 其中包括它们之间的逗号。

C 标准指定必须至少将一个参数传递给省略号, 以确保宏不会解析为带有尾随逗号的表达式。 如果没有参数C++传递给省略号, 则传统的 Microsoft 实现会禁止使用尾随逗号。

## <a name="example"></a>示例

```cpp
// variadic_macros.cpp
#include <stdio.h>
#define EMPTY

#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }
#define CHECK3(...) { printf(__VA_ARGS__); }
#define MACRO(s, ...) printf(s, __VA_ARGS__)

int main() {
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print

    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");

    // always invokes printf in the macro
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");

    MACRO("hello, world\n");

    MACRO("error\n", EMPTY); // would cause error C2059, except VC++
                             // suppresses the trailing comma
}
```

```Output
here are some varargs1(1)
here are some varargs2(4)
here are some varargs3(5)
hello, world
error
```

## <a name="see-also"></a>请参阅

[宏 (C/C++)](../preprocessor/macros-c-cpp.md)
