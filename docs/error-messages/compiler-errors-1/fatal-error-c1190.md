---
title: 错误 C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: 8bd0332770dd0771ac7a02574185a506cf6fd416
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228899"
---
# <a name="fatal-error-c1190"></a>错误 C1190

托管目标代码需要“/clr”选项

你当前使用的是 CLR 构造，但未指定 **/clr**。

有关更多信息，请参见 [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md)。

下面的示例生成 C1190：

```
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```