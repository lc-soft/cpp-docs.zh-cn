---
title: 解释复杂声明符
ms.date: 11/04/2016
helpviewer_keywords:
- complex declarators
- interpreting complex declarators
ms.assetid: dd5b7019-c86d-4645-a5cc-21f834de6f4a
ms.openlocfilehash: 13c81728f02963863b641348b58380da099b0013
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148239"
---
# <a name="interpreting-more-complex-declarators"></a>解释复杂声明符

您可以将任何声明符括在圆括号中以指定“复杂声明符”的特殊解释。 复杂声明符是由多个数组、指针或函数修饰符限定的标识符。 您可以将数组、指针和函数修饰符的各种组合应用于单个标识符。 通常 `typedef` 可用来简化声明。 请参阅 [Typedef 声明](../c-language/typedef-declarations.md)。

在解释复杂声明符时，方括号和圆括号（即，标识符右侧的修饰符）优先于星号（即，标识符左侧的修饰符）。 方括号和圆括号具有相同的优先级并且都是从左到右关联。 在完全解释声明符之后，将应用类型说明符以作为最后一步。 通过使用圆括号，您可以重写默认关联顺序和强制实施特定解释。 但是，绝不要单独在标识符名称两边使用圆括号。 这可能会被错误解释为参数列表。

解释复杂声明符的一个简单方法是通过下列 4 个步骤“从里到外”地读取它们：

1. 从标识符开始并直接查找方括号或圆括号（如果有）的右侧。

1. 解释这些方括号或圆括号，然后查找星号的左侧。

1. 如果在任何阶段遇到一个右圆括号，请返回并将规则 1 和 2 应用于圆括号内的所有内容。

1. 应用类型说明符。

    ```
    char *( *(*var)() )[10];
     ^   ^  ^ ^ ^   ^    ^
     7   6  4 2 1   3    5
    ```

在此示例中，步骤是按顺序编号的，并且可以按如下方式解释：

1. 标识符 `var` 声明为

1. 指向以下内容的指针

1. 返回以下内容的函数

1. 指向以下内容的指针

1. 包含 10 个元素的数组，这些元素分别为

1. 指向以下内容的指针

1. `char` 值。

## <a name="examples"></a>示例

以下示例阐释了其他复杂声明并演示了圆括号如何影响声明的含义。

```
int *var[5]; /* Array of pointers to int values */
```

数组修饰符的优先级高于指针修饰符，因此，`var` 将声明为数组。 指针修饰符将应用于数组元素的类型；因此，数组元素是指向 `int` 值的指针。

```
int (*var)[5]; /* Pointer to array of int values */
```

在对 `var` 的此声明中，圆括号为指针修饰符赋予了高于数组修饰符的优先级，并且 `var` 被声明为指向包含 5 个 `int` 值的数组的指针。

```
long *var( long, long ); /* Function returning pointer to long */
```

函数修饰符的优先级也高于指针修饰符，因此对 `var` 的此声明将 `var` 声明为返回指向 long 值的指针的函数。 该函数被声明为采用两个 long 值作为参数。

```
long (*var)( long, long ); /* Pointer to function returning long */
```

此示例与前一个示例类似。 圆括号为指针修饰符赋予了高于函数修饰符的优先级，`var` 被声明为指向返回 long 值的函数的指针。 同样，该函数采用两个 long 参数。

```
struct both       /* Array of pointers to functions */
{                 /*   returning structures         */
    int a;
    char b;
} ( *var[5] )( struct both, struct both );
```

数组的元素不能是函数，但此声明演示了如何将指针数组声明为函数。 在此示例中，`var` 被声明为包含 5 个指向函数（返回具有两个成员的结构）的指针的数组。 函数的参数被声明为具有同一结构类型 `both` 的两个结构。 请注意，`*var[5]` 两边需要圆括号。 如果没有它们，声明将是对声明函数数组的非法尝试，如下所示：

```
/* ILLEGAL */
struct both *var[5](struct both, struct both);
```

以下语句声明指针的数组。

```
unsigned int *(* const *name[5][10] ) ( void );
```

`name` 数组具有组织在一个多维数组中的 50 个元素。 这些元素是指向常量指针的指针。 此常量指针指向没有参数并返回指向无符号类型的指针的函数。

下一个示例是函数，该函数返回指向包含三个 double 值的数组的指针。

```
double ( *var( double (*)[3] ) )[3];
```

在此声明中，函数将返回指向数组的指针，因为返回数组的函数是非法的。 在此处，`var` 被声明为一个函数，该函数返回了指向包含三个 double 值的数组的指针。 函数 `var` 将采用一个参数。 参数（如返回值）是指向包含三个 double 值的数组的指针。 参数类型由一个复杂 abstract-declarator 给定。 参数类型中的星号两边需要圆括号；如果没有圆括号，参数类型将是一个包含三个指向 double 值的指针的数组。 有关抽象声明符的讨论和示例，请参阅[抽象声明符](../c-language/c-abstract-declarators.md)。

```
union sign         /* Array of arrays of pointers */
{                  /* to pointers to unions       */
     int x;
     unsigned y;
} **var[5][5];
```

如上面的示例所示，指针可以指向另一个指针，数组可包含数组作为元素。 这里的 `var` 是一个包含五个元素的数组。 每个元素都是一个五元素指针数组，这些指针指向指向具有两个成员的联合的指针。

```
union sign *(*var[5])[5]; /* Array of pointers to arrays
                             of pointers to unions        */
```

此示例演示圆括号的放置如何更改声明的含义。 在此示例中，`var` 是一个五元素指针数组，这些指针指向联合的五元素指针数组。 有关如何使用 `typedef` 避免复杂声明的示例，请参阅 [Typedef 声明](../c-language/typedef-declarations.md)。

## <a name="see-also"></a>请参阅

[声明和类型](../c-language/declarations-and-types.md)
