---
title: 编译器错误 C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 86c043889c5342ed4f3edfc4d8a298bcbd345b3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400235"
---
# <a name="compiler-error-c3765"></a>编译器错误 C3765

event： 不能在类/结构 type 标记为 event_receiver 中定义的事件

如果标记的类[event_receiver](../../windows/event-receiver.md)属性中，类不能包含[__event](../../cpp/event.md)声明。

下面的示例生成 C3765:

```
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```