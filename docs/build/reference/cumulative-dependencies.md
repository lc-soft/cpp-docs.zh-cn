---
title: 累计依赖项
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
ms.openlocfilehash: de0a9649be8f0dae58f45d8980d2df610ff2febe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294078"
---
# <a name="cumulative-dependencies"></a>累计依赖项

如果重复目标依赖关系是累积在描述块中。

例如，此设置的规则，

```Output
bounce.exe : jump.obj
bounce.exe : up.obj
   echo Building bounce.exe...
```

计算如下：

```Output
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

评估单个描述块中的多个依赖关系行中的多个目标就像在单独的描述块中，指定了每个但不在最后一个依赖关系行中的目标不使用命令块。 NMAKE 尝试使用此类目标的推断规则。

例如，此设置的规则，

```Output
leap.exe bounce.exe : jump.obj
bounce.exe climb.exe : up.obj
   echo Building bounce.exe...
```

计算如下：

```Output

leap.exe : jump.obj
# invokes an inference rule
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
climb.exe : up.obj
   echo Building bounce.exe...
```

## <a name="see-also"></a>请参阅

[目标](targets.md)
