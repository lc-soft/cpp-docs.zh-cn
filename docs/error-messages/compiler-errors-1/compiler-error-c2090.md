---
title: 编译器错误 C2090
ms.date: 11/04/2016
f1_keywords:
- C2090
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
ms.openlocfilehash: d805a4d6e0da0e94288ac36c6680a952b7633b86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347241"
---
# <a name="compiler-error-c2090"></a>编译器错误 C2090

函数返回数组

函数不能返回数组。 而是返回指向数组的指针。

下面的示例生成 C2090:

```
// C2090.cpp
int func1(void)[] {}   // C2090
```

可能的解决方法：

```
// C2090b.cpp
// compile with: /c
int* func2(int * i) {
   return i;
}
```