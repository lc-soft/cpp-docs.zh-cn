---
title: 属性 (C++)
ms.date: 11/04/2016
f1_keywords:
- property_cpp
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
ms.openlocfilehash: ece1016b7a18873dfa477b0f8b6ae4271a0f8001
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301482"
---
# <a name="property-c"></a>属性 (C++)

**Microsoft 专用**

此特性可应用于类或结构定义中的非静态“虚拟数据成员”。 编译器通过将这些“虚拟数据成员”的引用更改为函数调用来将其作为数据成员处理。

## <a name="syntax"></a>语法

```
   __declspec( property( get=get_func_name ) ) declarator
   __declspec( property( put=put_func_name ) ) declarator
   __declspec( property( get=get_func_name, put=put_func_name ) ) declarator
```

## <a name="remarks"></a>备注

当编译器发现与此特性声明成员选择运算符右侧的数据成员 ("**。**"**->**")，它会将转换到的操作`get`或`put`函数，具体取决于此类表达式是左值或右值。 在更复杂的上下文中，如"`+=`"，由两项操作都执行重写`get`和`put`。

此特性还可用于类或结构定义中的空数组的声明。 例如：

```cpp
__declspec(property(get=GetX, put=PutX)) int x[];
```

上面的语句指示 `x[]` 可用于一个或多个数组索引。 在这种情况下，`i=p->x[a][b]` 将变为 `i=p->GetX(a, b)`，`p->x[a][b] = i` 将变为 `p->PutX(a, b, i);`

**结束 Microsoft 专用**

## <a name="example"></a>示例

```cpp
// declspec_property.cpp
struct S {
   int i;
   void putprop(int j) {
      i = j;
   }

   int getprop() {
      return i;
   }

   __declspec(property(get = getprop, put = putprop)) int the_prop;
};

int main() {
   S s;
   s.the_prop = 5;
   return s.the_prop;
}
```

## <a name="see-also"></a>请参阅

[__declspec](../cpp/declspec.md)<br/>
[关键字](../cpp/keywords-cpp.md)