---
title: 编译器错误 C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 3c198168b4445e619148e5611621fa3ddba95d6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408782"
---
# <a name="compiler-error-c2055"></a>编译器错误 C2055

应输入形参表，不是类型表

函数定义中包含参数类型列表，而不是形参列表。 ANSI C 要求形参，除非它们是 void 或省略号命名为 (`...`)。

下面的示例生成 C2055:

```
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```