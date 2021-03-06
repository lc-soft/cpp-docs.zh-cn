---
title: '&lt;list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
- std::<list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: 8eb497e6a4380affd0f13f41c7b55990c562b7d3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453661"
---
# <a name="ltlistgt"></a>&lt;list&gt;

定义容器模板类列表和几个支持模板。

## <a name="syntax"></a>语法

```cpp
#include <list>
```

> [!NOTE]
> > \<库的列表也使用该`#include <initializer_list>`语句。

## <a name="members"></a>成员

### <a name="operators"></a>运算符

|||
|-|-|
|[operator!=](../standard-library/list-operators.md#op_neq)|测试运算符左侧的列表对象是否不等于右侧的列表对象。|
|[operator<](../standard-library/list-operators.md#op_lt)|测试运算符左侧的列表对象是否小于右侧的列表对象。|
|[operator\<=](../standard-library/list-operators.md#op_gt_eq)|测试运算符左侧的列表对象是否小于或等于右侧的列表对象。|
|[operator==](../standard-library/list-operators.md#op_eq_eq)|测试运算符左侧的列表对象是否等于右侧的列表对象。|
|[operator>](../standard-library/list-operators.md#op_gt)|测试运算符左侧的列表对象是否大于右侧的列表对象。|
|[operator>=](../standard-library/list-operators.md#op_gt_eq)|测试运算符左侧的列表对象是否大于或等于右侧的列表对象。|

### <a name="functions"></a>函数

|||
|-|-|
|[swap](../standard-library/list-functions.md#swap)|交换两个列表的元素。|

### <a name="classes"></a>类

|||
|-|-|
|[list 类](../standard-library/list-class.md)|用于保持其元素为线性排列并允许在序列内任何位置上的高效插入和删除的序列容器的模板类。|

## <a name="see-also"></a>请参阅

[头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C++ 标准库中的线程安全性](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 标准库参考](../standard-library/cpp-standard-library-reference.md)
