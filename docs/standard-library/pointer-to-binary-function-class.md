---
title: pointer_to_binary_function 类
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: fcc643d7569bd4f71b11249babdb49ef1362dc8b
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240496"
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function 类

将二元函数指针转换为自适应二元函数。 在 C + + 11 中，在 C + + 17 中删除不推荐使用。

## <a name="syntax"></a>语法

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>参数

*pfunc*\
要转换的二元函数。

*左侧*\
对其调用 *\*pfunc* 的左侧对象。

*右侧*\
对其调用 *\*pfunc* 的右侧对象。

## <a name="return-value"></a>返回值

此模板类存储一份`pfunc`。 它定义其成员函数`operator()`为返回`(* pfunc)(Left, right)`。

## <a name="remarks"></a>备注

二元函数指针是一个函数对象，且可能会被传递到期望将二元函数作为参数的任何 C++ 标准库算法，但这不适用。 若要使用与适配器，如向其绑定值或将它与配合，它必须提供嵌套类型一起`first_argument_type`， `second_argument_type`，和`result_type`，使这种适应成为可能。 `pointer_to_binary_function` 执行的转换允许函数适配器与二元函数指针配合使用。

## <a name="example"></a>示例

很少直接使用 `pointer_to_binary_function` 的构造函数。 有关如何声明和使用 `pointer_to_binary_function` 适配器谓词的示例，请参阅帮助程序函数 [ptr_fun](../standard-library/functional-functions.md#ptr_fun)。
