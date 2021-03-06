---
title: 依赖项副作用
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
ms.openlocfilehash: b89306b6e4d85e0e08729fb1d35fb041d69647e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272108"
---
# <a name="dependency-side-effects"></a>依赖项副作用

如果使用冒号 （:） 在不同位置中的两个依赖关系行中指定的目标和命令显示在行之一后，NMAKE 将解释依赖项，如同相邻或组合。 它不会调用没有命令，而是改为假定依赖项属于一个描述块，并执行与其他依赖项指定的命令的依赖关系的推理规则。 例如，此设置的规则：

```Output
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
```

计算如下：

```Output
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

这种效果，则不会使用两个冒号 (`::`) 使用。 例如，此设置的规则：

```Output
bounce.exe :: jump.obj
   echo Building bounce.exe...

bounce.exe :: up.obj
```

计算如下：

```Output
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
# invokes an inference rule
```

## <a name="see-also"></a>请参阅

[目标](targets.md)
