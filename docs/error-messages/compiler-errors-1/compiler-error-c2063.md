---
title: 编译器错误 C2063
ms.date: 11/04/2016
f1_keywords:
- C2063
helpviewer_keywords:
- C2063
ms.assetid: 0a90c18f-4029-416a-9128-e8713b53e6f1
ms.openlocfilehash: 5d91dc595798793899eb8ac33e2a6c71cabad02a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408636"
---
# <a name="compiler-error-c2063"></a>编译器错误 C2063

“identifier”: 不是函数

该标识符用作函数，但未声明为函数。

下面的示例生成 C2063：

```
// C2063.c
int main() {
   int i, j;
   j = i();    // C2063, i is not a function
}
```

可能的解决方法：

```
// C2063b.c
int i() { return 0;}
int main() {
   int j;
   j = i();
}
```