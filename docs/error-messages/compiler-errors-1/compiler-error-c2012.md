---
title: 编译器错误 C2012
ms.date: 11/04/2016
f1_keywords:
- C2012
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
ms.openlocfilehash: 85c3ad1d127dcabeeed0c5727ba6bbbca86f7898
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364462"
---
# <a name="compiler-error-c2012"></a>编译器错误 C2012

之后缺少名称 ' <'

`#include` 指令缺少必需的文件名。

以下示例生成 C2012：

```
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

可能的解决方法：

```
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```