---
title: 编译器错误 C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: 5a9d897686fc915c9892fa2bcd51fa3ca3c8b05e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165660"
---
# <a name="compiler-error-c2218"></a>编译器错误 C2218

“__vectorcall”不能和“/arch:IA32”一起使用

`__vectorcall` 调用约定仅受到包括流式处理 SIMD 扩展 2 (SSE2) 和更高版本的 x86 和 x64 处理器上的本机代码的支持。 有关详细信息，请参阅[__vectorcall](../../cpp/vectorcall.md)。

若要修复此错误，请将编译器选项更改为目标 SSE2、AVX 或 AVX2 指令集的。 有关详细信息，请参阅 [/arch (x86)](../../build/reference/arch-x86.md)。