﻿---
title: C++ 语言参考
ms.custom: index-page
ms.date: 05/06/2019
helpviewer_keywords:
- C++, language reference
ms.assetid: 4be9cacb-c862-4391-894a-3a118c9c93ce
ms.openlocfilehash: 1790f5d7ecf834c97a9242e8f42d1fb402604ac6
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222490"
---
# <a name="c-language-reference"></a>C++ 语言参考

此参考文章介绍C++编程语言在 Microsoft 中实现C++编译器。 基于组织[*带批注的C++参考手册*](http://www.stroustrup.com/arm.html) Margaret Ellis 和 Bjarne Stroustrup 和 ANSI/ISO 上C++国际标准 (ISO/IEC FDIS 14882)。 本文涵盖了 C++ 语言功能的 Microsoft 专用实现。

有关现代 C++ 编程做法的概述，请参阅[欢迎回到 C++](welcome-back-to-cpp-modern-cpp.md)。

请参阅下面的表以快速查找关键字或运算符：

- [C++ 关键字](../cpp/keywords-cpp.md)

- [C++ 运算符](../cpp/cpp-built-in-operators-precedence-and-associativity.md)

## <a name="in-this-section"></a>本节内容

[词法约定](../cpp/lexical-conventions.md)<br/>
C++ 程序的基本词法元素：标记、注释、运算符、关键字、标点符号、文本。 此外，还有文件转换、运算符优先级别/关联性。

[基本概念](../cpp/basic-concepts-cpp.md)<br/>
范围、链接、程序启动和终止、存储类以及类型。

[标准转换](../cpp/standard-conversions.md)<br/>
内置类型或“基础”类型之间的类型转换。 此外，算术转换和指针、引用与成员指针类型之间的转换。

[运算符、 优先级和结合性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
C++ 中的运算符。

[表达式](../cpp/expressions-cpp.md)<br/>
表达式的类型、表达式的语义、有关运算符的参考主题、强制转换和强制转换运算符、运行时类型信息。

[Lambda 表达式](../cpp/lambda-expressions-in-cpp.md)<br/>
隐式定义函数对象类和构造该类类型的函数对象的编程技术。

[语句](../cpp/statements-cpp.md)<br/>
表达式、null、复合、选择、迭代、跳转和声明语句。

[声明和定义](declarations-and-definitions-cpp.md)<br/>
存储类说明符、函数定义、初始化、枚举、**类**、**结构**和**联合**声明以及 **typedef** 声明。 此外，还有**内联**函数、**const** 关键字、命名空间。

[类、 结构和联合](../cpp/classes-and-structs-cpp.md)<br/>
介绍类、结构和联合。 此外，还有成员函数，特殊成员函数，数据成员，位域，**this** 指针和嵌套的类。

[派生的类](../cpp/inheritance-cpp.md)<br/>
单个和多个继承、**虚拟**函数、多个基类、**抽象**类、作用域规则。 还有 **__super** 和 **__interface** 关键字。

[成员访问控制](../cpp/member-access-control-cpp.md)<br/>
控制对类成员的访问权限：**公共**，**专用**，并**保护**关键字。 友元函数和友元类。

[重载](operator-overloading.md)<br/>
重载的运算符，运算符重载的规则。

[异常处理](../cpp/exception-handling-in-visual-cpp.md)<br/>
C++ 异常处理、结构化异常处理 (SEH)、编写异常处理语句所使用的关键字。

[断言和用户提供的消息](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
`#error` 指令**static_assert**关键字，`assert`宏。

[模板](../cpp/templates-cpp.md)<br/>
模板规范、 函数模板、 类模板，而**typename**关键字、 模板与宏、 模板和智能指针。

[事件处理](../cpp/event-handling.md)<br/>
声明事件和事件处理程序。

[Microsoft 专用的修饰符](../cpp/microsoft-specific-modifiers.md)<br/>
Microsoft C++ 专用修饰符。 内存寻址、 调用约定、**裸**函数，扩展的存储类特性 (**__declspec**)， **__w64**。

[内联汇编程序](../assembler/inline/inline-assembler.md)<br/>
使用程序集语言和 C++ 中的 **__asm**块。

[编译器 COM 支持](../cpp/compiler-com-support.md)<br/>
有关用于支持 COM 类型的 Microsoft 专用类和全局函数的参考。

[Microsoft 扩展](../cpp/microsoft-extensions.md)<br/>
Microsoft 的 C++ 扩展。

[非标准行为](../cpp/nonstandard-behavior.md)<br/>
使用了非标准行为的 Microsoft 信息C++编译器。

[欢迎回到 C++](welcome-back-to-cpp-modern-cpp.md)<br/>
现代 C++ 编程做法编写安全、 正确、 有效的程序的概述。

## <a name="related-sections"></a>相关章节

[适用于运行时平台的组件扩展](../extensions/component-extensions-for-runtime-platforms.md)<br/>
参考资料上使用 MicrosoftC++到目标.NET 编译器。

[C/C++ 生成参考](../build/reference/c-cpp-building-reference.md)<br/>
编译器选项、链接器选项和其他生成工具。

[C/C++ 预处理器参考](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
有关杂注、预处理器指令、预定义宏和预处理器的参考材料。

[Visual C++ 库](../standard-library/cpp-standard-library-reference.md)<br/>
一组指向参考起始页的各种 MicrosoftC++库。

## <a name="see-also"></a>请参阅

[C 语言参考](../c-language/c-language-reference.md)
