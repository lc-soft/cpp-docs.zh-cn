---
title: 编译器错误 C2736
ms.date: 11/04/2016
f1_keywords:
- C2736
helpviewer_keywords:
- C2736
ms.assetid: 95a6bc28-c0cb-49dc-87e6-e993dbbba881
ms.openlocfilehash: 7ce63c1e9d9e6ab04a7f7200c5b34f346100733b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300761"
---
# <a name="compiler-error-c2736"></a>编译器错误 C2736

强制转换中不允许使用 keyword 关键字

关键字无效强制转换中。

下面的示例生成 C2736:

```
// C2736.cpp
int main() {
   return (virtual) 0;   // C2736
   // try the following line instead
   // return 0;
}
```