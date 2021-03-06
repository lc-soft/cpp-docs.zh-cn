---
title: 预定义宏
ms.custom: update_every_version
ms.date: 10/01/2019
f1_keywords:
- _ATL_VER
- __ATOM__
- __AVX__
- __AVX2__
- __AVX512BW__
- __AVX512CD__
- __AVX512DQ__
- __AVX512F__
- __AVX512VL__
- _CHAR_UNSIGNED
- __CLR_VER
- _CONTROL_FLOW_GUARD
- __COUNTER__
- __cplusplus
- __cplusplus_cli
- __cplusplus_winrt
- _CPPRTTI
- _CPPUNWIND
- __DATE__
- _DEBUG
- _DLL
- __FILE__
- __FUNCDNAME__
- __FUNCSIG__
- __FUNCTION__
- _INTEGRAL_MAX_BITS
- _ISO_VOLATILE
- _KERNEL_MODE
- __LINE__
- _M_AMD64
- _M_ARM
- _M_ARM_ARMV7VE
- _M_ARM_FP
- _M_ARM64
- _M_CEE
- _M_CEE_PURE
- _M_CEE_SAFE
- _M_FP_EXCEPT
- _M_FP_FAST
- _M_FP_PRECISE
- _M_FP_STRICT
- _M_IX86
- _M_IX86_FP
- _M_X64
- _MANAGED
- _MFC_VER
- _MSC_BUILD
- _MSC_EXTENSIONS
- _MSC_FULL_VER
- _MSC_VER
- _MSVC_LANG
- __MSVC_RUNTIME_CHECKS
- _MT
- _NATIVE_WCHAR_T_DEFINED
- _NO_SIZED_DEALLOCATION
- _OPENMP
- _PREFAST_
- _RESUMABLE_FUNCTIONS_SUPPORTED
- _RTC_CONVERSION_CHECKS_ENABLED
- __STDC__
- __STDC_HOSTED__
- __STDCPP_THREADS__
- __TIME__
- __TIMESTAMP__
- __VA_ARGS__
- _VC_NODEFAULTLIB
- _WCHAR_T_DEFINED
- _WIN32
- _WIN64
- _WINRT_DLL
- __func__
helpviewer_keywords:
- timestamps, preprocessor macro
- cl.exe compiler, version number
- version numbers, C/C++ compiler (cl.exe)
- macros, predefined C++
- preprocessor, macros
- predefined macros
- _ATL_VER macro
- __ATOM__ macro
- __AVX__ macro
- __AVX2__ macro
- __AVX512BW__ macro
- __AVX512CD__ macro
- __AVX512DQ__ macro
- __AVX512F__ macro
- __AVX512VL__ macro
- _CHAR_UNSIGNED macro
- __CLR_VER macro
- _CONTROL_FLOW_GUARD macro
- __COUNTER__ macro
- __cplusplus macro
- __cplusplus_cli macro
- __cplusplus_winrt macro
- _CPPRTTI macro
- _CPPUNWIND macro
- __DATE__ macro
- _DEBUG macro
- _DLL macro
- __FILE__ macro
- __FUNCDNAME__ macro
- __FUNCSIG__ macro
- __FUNCTION__ macro
- _INTEGRAL_MAX_BITS macro
- _ISO_VOLATILE macro
- _KERNEL_MODE macro
- __LINE__ macro
- _M_AMD64 macro
- _M_ARM macro
- _M_ARM_ARMV7VE macro
- _M_ARM_FP macro
- _M_ARM64 macro
- _M_CEE macro
- _M_CEE_PURE macro
- _M_CEE_SAFE macro
- _M_FP_EXCEPT macro
- _M_FP_FAST macro
- _M_FP_PRECISE macro
- _M_FP_STRICT macro
- _M_IX86 macro
- _M_IX86_FP macro
- _M_X64 macro
- _MANAGED macro
- _MFC_VER macro
- _MSC_BUILD macro
- _MSC_EXTENSIONS macro
- _MSC_FULL_VER macro
- _MSC_VER macro
- _MSVC_LANG macro
- __MSVC_RUNTIME_CHECKS macro
- _MT macro
- _NATIVE_WCHAR_T_DEFINED macro
- _NO_SIZED_DEALLOCATION macro
- _OPENMP macro
- _PREFAST_ macro
- _RESUMABLE_FUNCTIONS_SUPPORTED macro
- _RTC_CONVERSION_CHECKS_ENABLED macro
- __STDC__ macro
- __STDC_HOSTED__ macro
- __STDCPP_THREADS__ macro
- __TIME__ macro
- __TIMESTAMP__ macro
- __VA_ARGS__ macro
- _VC_NODEFAULTLIB macro
- _WCHAR_T_DEFINED macro
- _WIN32 macro
- _WIN64 macro
- _WINRT_DLL macro
- __func__ identifier
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
ms.openlocfilehash: eb75273bc8cbe5ccbf62edc82a1e7deccc605757
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816605"
---
# <a name="predefined-macros"></a>预定义宏

Microsoft C/C++编译器（MSVC）根据语言（C 或C++）、编译目标和所选编译器选项预定义某些预处理器宏。

MSVC 支持 ANSI/ISO C99 标准所需的预定义预处理器宏，以及 ISO c + + 14 和 c + + 17 标准。 实现还支持多个特定于 Microsoft 的预处理器宏。 某些宏仅针对特定生成环境或编译器选项定义。 除非注明，否则在整个翻译单元中定义宏，就好像这些宏指定为 **/d**编译器选项参数一样。 定义后，在编译之前，将由预处理器将宏扩展为指定值。 预定义的宏不带参数，并且不能重新定义。

## <a name="standard-predefined-identifier"></a>标准预定义标识符

编译器支持 ISO C99 和 ISO c + + 11 指定的预定义标识符。

- **&#95; func &#95; &#95;** 封闭函数的非限定名称和未修饰名称作为**char**的函数本地**静态常量**数组。

    ```cpp
    void example(){
        printf("%s\n", __func__);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>标准预定义宏

编译器支持 ISO C99 和 ISO c + + 17 标准指定的这些预定义的宏。

- **&#95;cplusplus &#95;** 当翻译单元编译为C++时，定义为整数文本值。 否则为 undefined。

- **&#95;日期&#95; &#95;** 当前源文件的编译日期。 日期是以*Mmm dd yyyy*形式的常量长度字符串文本。 月份名称*Mmm*与 C 运行时库（CRT） [asctime](../c-runtime-library/reference/asctime-wasctime.md)函数生成的缩写月份名称相同。 如果值小于10，则日期*dd*的第一个字符为空格。 始终定义此宏。

- **&#95;文件&#95; &#95;** 当前源文件的名称。 文件扩展到字符串文字。 **&#95; &#95;&#95;** 若要确保显示文件的完整路径，请使用[/FC （诊断中源代码文件的完整路径）](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)。 始终定义此宏。

- **&#95;行&#95; &#95;** 定义为当前源文件中的整数行号。 可以使用 @no__t 5 指令更改 **&#95; &#95;行&#95;** 宏的值。 始终定义此宏。

- **&#95; STDC &#95; &#95;** 仅在编译为 C 和指定[/za](../build/reference/za-ze-disable-language-extensions.md)编译器选项时定义为1。 否则为 undefined。

- **&#95;&#95;如果&#95;实现&#95;** 是*托管实现*，则将托管的 STDC 定义为1，它支持整个所需的标准库。 否则，定义为0。

- **&#95;&#95;当&#95;且&#95;** 仅当程序可以有多个执行线程并将其编译为C++时，STDCPP 定义为1的线程。 否则为 undefined。

- **&#95;时间&#95; &#95;** 预处理翻译单元的转换时间。 此时间为*hh： mm： ss*格式的字符串文字，与 CRT [asctime](../c-runtime-library/reference/asctime-wasctime.md)函数返回的时间相同。 始终定义此宏。

## <a name="microsoft-specific-predefined-macros"></a>特定于 Microsoft 的预定义宏

MSVC 支持这些其他预定义的宏。

- **&#95; ATOM &#95; &#95;** 如果设置了[/favor： ATOM](../build/reference/favor-optimize-for-architecture-specifics.md)编译器选项并且编译器目标为 x86 或 x64，则定义为1。 否则为 undefined。

- **&#95; AVX &#95; &#95;** 如果设置了[/arch： AVX](../build/reference/arch-x86.md)、 [/arch： AVX2](../build/reference/arch-x86.md)或[/arch： AVX512](../build/reference/arch-x86.md)编译器选项，并且编译器目标为 x86 或 x64，则定义为1。 否则为 undefined。

- **&#95; AVX2 &#95; &#95;** 如果设置了[/arch： AVX2](../build/reference/arch-x86.md)或[/arch： AVX512](../build/reference/arch-x86.md)编译器选项，并且编译器目标为 x86 或 x64，则定义为1。 否则为 undefined。

- **&#95; AVX512BW &#95; &#95;** 如果设置了[/arch： AVX512](../build/reference/arch-x86.md)编译器选项并且编译器目标为 x86 或 x64，则定义为1。 否则为 undefined。

- **&#95; AVX512CD &#95; &#95;** 如果设置了[/arch： AVX512](../build/reference/arch-x86.md)编译器选项并且编译器目标为 x86 或 x64，则定义为1。 否则为 undefined。

- **&#95; AVX512DQ &#95; &#95;** 如果设置了[/arch： AVX512](../build/reference/arch-x86.md)编译器选项并且编译器目标为 x86 或 x64，则定义为1。 否则为 undefined。

- **&#95; AVX512F &#95; &#95;** 如果设置了[/arch： AVX512](../build/reference/arch-x86.md)编译器选项并且编译器目标为 x86 或 x64，则定义为1。 否则为 undefined。

- **&#95; AVX512VL &#95; &#95;** 如果设置了[/arch： AVX512](../build/reference/arch-x86.md)编译器选项并且编译器目标为 x86 或 x64，则定义为1。 否则为 undefined。

- **&#95;如果&#95;** 默认**char**类型为无符号，则将 CHAR 无符号定义为1。 此值在设置了[/j （默认 Char 类型为无符号）](../build/reference/j-default-char-type-is-unsigned.md)编译器选项时定义。 否则为 undefined。

- **&#95;CLR 版本&#95;&#95;** 定义为一个整数文本，表示用于编译应用程序的公共语言运行时（CLR）的版本。 此值的编码格式为 `Mmmbbbbb`，其中 @no__t 为运行时的主版本，`mm` 为运行时的次版本，`bbbbb` 为生成号。 **&#95;&#95;如果&#95;** 设置了[/clr](../build/reference/clr-common-language-runtime-compilation.md)编译器选项，则定义 CLR 版本。 否则为 undefined。

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(__CLR_VER);
    }
    ```

- **&#95;设置&#95;了&#95;** [/Guard： cf （启用控制流防护）](../build/reference/guard-enable-control-flow-guard.md)编译器选项时，控制流防护定义为1。 否则为 undefined。

- **&#95;计数器&#95; &#95;** 展开为从0开始的整数文本。 每次将该值用于源文件或源文件的包含标头时，该值将递增1。 当使用预编译头时， **&#95;计数器会记住其状态。 &#95; &#95;** 始终定义此宏。

  此示例使用 `__COUNTER__` 将唯一标识符分配给同一类型的三个不同对象。 @No__t-0 构造函数采用整数作为参数。 在 `main` 中，应用程序声明类型为 @no__t 的三个对象，并使用 `__COUNTER__` 作为唯一标识符参数：

    ```cpp
    // macro__COUNTER__.cpp
    // Demonstration of __COUNTER__, assigns unique identifiers to
    // different objects of the same type.
    // Compile by using: cl /EHsc /W4 macro__COUNTER__.cpp
    #include <stdio.h>

    class exampleClass {
        int m_nID;
    public:
        // initialize object with a read-only unique ID
        exampleClass(int nID) : m_nID(nID) {}
        int GetID(void) { return m_nID; }
    };

    int main()
    {
        // __COUNTER__ is initially defined as 0
        exampleClass e1(__COUNTER__);

        // On the second reference, __COUNTER__ is now defined as 1
        exampleClass e2(__COUNTER__);

        // __COUNTER__ is now defined as 2
        exampleClass e3(__COUNTER__);

        printf("e1 ID: %i\n", e1.GetID());
        printf("e2 ID: %i\n", e2.GetID());
        printf("e3 ID: %i\n", e3.GetID());

        // Output
        // ------------------------------
        // e1 ID: 0
        // e2 ID: 1
        // e3 ID: 2

        return 0;
    }
    ```

- **&#95;&#95;当&#95;** 编译为C++且设置了[/clr](../build/reference/clr-common-language-runtime-compilation.md)编译器选项时，cplusplus cli 定义为整数文本值200406。 否则为 undefined。 定义后，  **&#95; &#95;cplusplus&#95;cli**在整个翻译单元中都有效。

    ```cpp
    // cplusplus_cli.cpp
    // compile by using /clr
    #include "stdio.h"
    int main() {
       #ifdef __cplusplus_cli
          printf("%d\n", __cplusplus_cli);
       #else
          printf("not defined\n");
       #endif
    }
    ```

- **&#95;&#95;当&#95;** 编译为C++且设置了[/ZW （Windows 运行时编译）](../build/reference/zw-windows-runtime-compilation.md)编译器选项时，cplusplus winrt 定义为整数文本值201009。 否则为 undefined。

- **&#95;CPPRTTI**如果设置了[/GR （启用运行时类型信息）](../build/reference/gr-enable-run-time-type-information.md)编译器选项，则定义为1。 否则为 undefined。

- **&#95;CPPUNWIND**如果设置了一个或多个[/gx （启用异常处理）](../build/reference/gx-enable-exception-handling.md)、 [/Clr （公共语言运行时编译）](../build/reference/clr-common-language-runtime-compilation.md)或[/EH （异常处理模型）](../build/reference/eh-exception-handling-model.md)编译器选项，则定义为1。 否则为 undefined。

- **&#95;调试**如果设置了[/LDd](../build/reference/md-mt-ld-use-run-time-library.md)、 [/MDd](../build/reference/md-mt-ld-use-run-time-library.md)或[/MTd](../build/reference/md-mt-ld-use-run-time-library.md)编译器选项，则定义为1。 否则为 undefined。

- 如果设置了[/md](../build/reference/md-mt-ld-use-run-time-library.md)或[/MDd](../build/reference/md-mt-ld-use-run-time-library.md) （多线程 DLL）编译器选项，则 DLL 定义为1。  **&#95;** 否则为 undefined。

- **&#95; FUNCDNAME &#95; &#95;** 定义为包含封闭函数的[修饰名](../build/reference/decorated-names.md)的字符串文字。 仅在函数中定义宏。 如果使用[/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)或[/p](../build/reference/p-preprocess-to-a-file.md)编译器选项，则不会扩展 **&#95;FUNCDNAME&#95;宏。 &#95;**

   此示例使用 `__FUNCDNAME__`、`__FUNCSIG__` 和 `__FUNCTION__` 宏来显示函数信息。

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- **&#95; FUNCSIG &#95; &#95;** 定义为包含封闭函数的签名的字符串文字。 仅在函数中定义宏。 如果使用[/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)或[/p](../build/reference/p-preprocess-to-a-file.md)编译器选项，则不会扩展 **&#95;FUNCSIG&#95;宏。 &#95;** 为64位目标编译时，默认情况下，调用约定 `__cdecl`。 有关用法的示例，请参阅 @no__t 的宏。

- **&#95;函数&#95; &#95;** 定义为包含封闭函数的未修饰名的字符串文字。 仅在函数中定义宏。 如果使用[/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)或[/p](../build/reference/p-preprocess-to-a-file.md)编译器选项，则不扩展 **&#95;函数&#95;宏。 &#95;** 有关用法的示例，请参阅 @no__t 的宏。

- **整数&#95;最&#95;大位&#95;** 定义为整数文本值64，非向量整型的最大大小（位）。 始终定义此宏。

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", _INTEGRAL_MAX_BITS);
   }
   ```

- **&#95; INTELLISENSE &#95; &#95;** 在 Visual Studio IDE 中的 IntelliSense 编译器传递过程中定义为1。 否则为 undefined。 您可以使用此宏保护 IntelliSense 编译器不理解的代码，或使用它在生成和 IntelliSense 编译器之间进行切换。 有关详细信息，请参阅[IntelliSense 缓慢的故障排除提示](https://devblogs.microsoft.com/cppblog/troubleshooting-tips-for-intellisense-slowness/)。

- **&#95;如果&#95;** 设置了[/volatile： iso](../build/reference/volatile-volatile-keyword-interpretation.md)编译器选项，则 ISO VOLATILE 定义为1。 否则为 undefined。

- **&#95;如果&#95;** 设置了[/Kernel （创建内核模式二进制）](../build/reference/kernel-create-kernel-mode-binary.md)编译器选项，则内核模式定义为1。 否则为 undefined。

- **&#95;M&#95;AMD64**定义为面向 x64 处理器的编译的整数文本值100。 否则为 undefined。

- **&#95;M&#95;ARM**定义为面向 ARM 处理器的编译的整数文本值7。 否则为 undefined。

- **&#95;如果&#95;为&#95;** 面向 ARM 处理器的编译设置[/arch： ARMV7VE](../build/reference/arch-arm.md)编译器选项，则 M ARM ARMV7VE 定义为1。 否则为 undefined。

- **&#95;M&#95;ARM&#95;FP**定义为整数文本值，该值指示为 ARM 处理器目标设置了哪个[/arch](../build/reference/arch-arm.md)编译器选项。 否则为 undefined。

  - 如果未指定 `/arch` ARM 选项，则为30-39 范围内的一个值，指示已设置 ARM 的默认体系结构（@no__t 为-1）。

  - 如果设置了 `/arch:VFPv4`，则为40-49 范围内的值。

  - 有关详细信息，请参阅[/arch （ARM）](../build/reference/arch-arm.md)。

- **&#95;M&#95;ARM64**对于目标为64位 ARM 处理器的编译，定义为1。 否则为 undefined。

- **&#95;如果&#95;** 设置了任何[/Clr （公共语言运行时编译）](../build/reference/clr-common-language-runtime-compilation.md)编译器选项，则 M CEE 定义为001。 否则为 undefined。

- **M&#95;CEE&#95;PURE &#95;** 从 Visual Studio 2015 开始已弃用。 如果设置了[/clr： pure](../build/reference/clr-common-language-runtime-compilation.md)编译器选项，则定义为001。 否则为 undefined。

- **M&#95;CEE&#95;SAFE &#95;** 从 Visual Studio 2015 开始已弃用。 如果设置了[/clr： safe](../build/reference/clr-common-language-runtime-compilation.md)编译器选项，则定义为001。 否则为 undefined。

- **&#95;如果&#95;已&#95;** 设置[/fp： except](../build/reference/fp-specify-floating-point-behavior.md)或[/Fp： strict](../build/reference/fp-specify-floating-point-behavior.md)编译器选项，则除定义为1的 M FP 除外。 否则为 undefined。

- **&#95;如果&#95;设置&#95;** 了[/fp： fast](../build/reference/fp-specify-floating-point-behavior.md)编译器选项，则 M FP FAST 定义为1。 否则为 undefined。

- **&#95;如果&#95;设置&#95;** 了[/fp：精确](../build/reference/fp-specify-floating-point-behavior.md)编译器选项，则 M FP 精确定义为1。 否则为 undefined。

- **&#95;如果&#95;设置&#95;** 了[/fp： strict](../build/reference/fp-specify-floating-point-behavior.md)编译器选项，则 M FP STRICT 定义为1。 否则为 undefined。

- **&#95;M&#95;IX86**定义为面向 x86 处理器的编译的整数文本值600。 未为 x64 或 ARM 编译目标定义此宏。

- **&#95;M&#95;IX86&#95;FP**定义为整数文本值，该值指示已设置的[/arch](../build/reference/arch-arm.md)编译器选项或默认值。 当编译目标为 x86 处理器时，将始终定义此宏。 否则为 undefined。 定义后，值为：

  - 如果已设置 `/arch:IA32` 编译器选项，则为0。

  - 如果已设置 `/arch:SSE` 编译器选项，则为1。

  - 如果已设置 `/arch:SSE2`、`/arch:AVX`、`/arch:AVX2` 或 `/arch:AVX512` 编译器选项，则为2。 如果未指定 `/arch` 编译器选项，则此值为默认值。 如果指定 `/arch:AVX`，还将定义 **&#95; &#95;宏&#95; AVX** 。 如果指定 `/arch:AVX2`， **&#95; &#95;&#95;** 则同时定义 AVX  **&#95; &#95;和&#95; AVX2** 。 如果指定 **&#95; &#95;&#95;** `/arch:AVX512`，AVX，  **&#95; &#95;AVX2&#95;** ，  **&#95; &#95;AVX512BW&#95;** ， **&#95;AVX512CD， &#95; &#95;**  **&#95;还定义了&#95;AVX512DQ、AVX512F 和 AVX512VL。 &#95;** **&#95; &#95;&#95;** **&#95; &#95;&#95;**

  - 有关详细信息，请参阅 [/arch (x86)](../build/reference/arch-x86.md)。

- **&#95;M&#95;X64**定义为面向 x64 处理器的编译的整数文本值100。 否则为 undefined。

- **&#95;托管**如果设置了[/clr](../build/reference/clr-common-language-runtime-compilation.md)编译器选项，则定义为1。 否则为 undefined。

- **&#95;MSC&#95;版本**定义为包含编译器版本号的修订号元素的整数文本。 修订号是句点分隔版本号的第四个元素。 例如，如果 Microsoft C/C++编译器的版本号为15.00.20706.01，则 **&#95;MSC&#95;BUILD**宏的计算结果为1。 始终定义此宏。

- **&#95;如果&#95;** 设置了默认的[/Ze （启用语言扩展）](../build/reference/za-ze-disable-language-extensions.md)编译器选项，则将 services.msc 扩展定义为1。 否则为 undefined。

- **MSC&#95;完整&#95;版&#95;** 定义为一个整数文本，用于对编译器版本号的主要版本号、次要版本号和内部版本号元素进行编码。 主编号是句点分隔版本号的第一个元素，次版本号是第二个元素，而生成号是第三个元素。 例如，如果 MicrosoftC++ C/编译器的版本号为15.00.20706.01，则 **&#95;MSC&#95;FULL&#95;VER**宏的计算结果为150020706。 在命令行中输入 `cl /?` 以查看编译器的版本号。 始终定义此宏。

- **&#95;MSC&#95;VER**定义为一个整数文本，用于对编译器版本号的主要和次要元素进行编码。 主编号是句点分隔版本号的第一个元素，次版本号是第二个元素。 例如，如果 Microsoft C/C++编译器的版本号为17.00.51106.1，则 **&#95;MSC&#95;VER**宏的计算结果为1700。 在命令行中输入 `cl /?` 以查看编译器的版本号。 始终定义此宏。

   |Visual Studio 版本|**&#95;MSC&#95;VER**|
   |-|-|
   |Visual Studio 6.0|1200|
   |Visual Studio .NET 2002 （7.0）|1300|
   |Visual Studio .NET 2003 （7.1）|1310|
   |Visual Studio 2005 （8.0）|1400|
   |Visual Studio 2008 （9.0）|1500|
   |Visual Studio 2010 （10.0）|1600|
   |Visual Studio 2012 （11.0）|1700|
   |Visual Studio 2013 （12.0）|1800|
   |Visual Studio 2015 （14.0）|1900|
   |Visual Studio 2017 RTW （15.0）|1910|
   |Visual Studio 2017 版本 15.3|1911|
   |Visual Studio 2017 版本 15.5|1912|
   |Visual Studio 2017 版本 15.6|1913|
   |Visual Studio 2017 15.7 版|1914|
   |Visual Studio 2017 版本 15.8|1915|
   |Visual Studio 2017 版本15。9|1916|
   |Visual Studio 2019 RTW （16.0）|1920|
   |Visual Studio 2019 版本 16.1|1921|
   |Visual Studio 2019 版本 16.2|1922|
   |Visual Studio 2019 版本16。3|1923|

   若要测试的编译器版本或更新的 Visual Studio 或之后的给定版本中，使用 **>=** 运算符。 可以在条件指令中使用它来比较 **&#95;MSC&#95;VER**和该已知版本。 如果要比较多个互相排斥的版本，请按版本号的降序顺序进行比较。 例如，以下代码将检查 Visual Studio 2017 和更高版本中发布的编译器。 接下来，它将检查 Visual Studio 2015 或之后发布的编译器。 然后，它会检查 Visual Studio 2015 之前发布的所有编译器：

   ```cpp
   #if _MSC_VER >= 1910
   // . . .
   #elif _MSC_VER >= 1900
   // . . .
   #else
   // . . .
   #endif
   ```

   有关详细信息，请参阅 Microsoft C++团队博客中的[Visual C++编译器版本](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/)。

- **&#95;MSVC&#95;** 语言定义为指定编译器所针对的C++语言标准的整数文本。 仅在编译为C++的代码中设置。 默认情况下，如果指定了[/std： c + + 14](../build/reference/std-specify-language-standard-version.md)编译器选项，则宏是整数文本值201402L。 如果指定了[/std： c + + 17](../build/reference/std-specify-language-standard-version.md)编译器选项，则宏将设置为201703L。 如果指定了[/std： c + + 最新](../build/reference/std-specify-language-standard-version.md)选项，则将其设置为较高的未指定值。 否则，宏将未定义。 **&#95;MSVC&#95;LANG**宏和[/std （指定语言标准版本）](../build/reference/std-specify-language-standard-version.md)编译器选项是在 Visual Studio 2015 Update 3 开始提供。

- **&#95;&#95;当&#95;设置&#95;** 了某个[/Rtc](../build/reference/rtc-run-time-error-checks.md)编译器选项时，MSVC 运行时检查定义为1。 否则为 undefined。

- **&#95;如果&#95;** 设置了预处理器一致性模式[/experimental：预处理器](../build/reference/rtc-run-time-error-checks.md)编译器选项，则 MSVC 传统定义为0。 默认情况下，在设置为1时，或在设置[/experimental：预处理器](../build/reference/rtc-run-time-error-checks.md)时，指示正在使用传统预处理器。 从 Visual Studio 2017 版本15.8 开始，可以使用 **&#95;MSVC&#95;传统**宏 and [/experimental：预处理器（启用预处理器一致性模式）](../build/reference/experimental-preprocessor.md)编译器选项。

   ```cpp
   #if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
   // Logic using the traditional preprocessor
   #else
   // Logic using cross-platform compatible preprocessor
   #endif
   ```

- **&#95;MT**当指定[/md 或/MDd](../build/reference/md-mt-ld-use-run-time-library.md) （多线程 DLL）或[/mt 或/MTd](../build/reference/md-mt-ld-use-run-time-library.md) （多线程）时，定义为1。 否则为 undefined。

- **&#95;在&#95;设置&#95;&#95;** [/zc： wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)编译器选项时，将定义为1的本机 WCHAR T 定义为1。 否则为 undefined。

- **&#95;OPENMP**如果设置了[/openmp （Enable openmp 2.0 支持）](../build/reference/openmp-enable-openmp-2-0-support.md)编译器选项，则定义为整数文本200203。 此值表示 MSVC 实现的 OpenMP 规范的日期。 否则为 undefined。

   ```cpp
   // _OPENMP_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", _OPENMP);
   }
   ```

- **&#95;PREFAST&#95;** 如果设置了[/analyze](../build/reference/analyze-code-analysis.md)编译器选项，则定义为1。 否则为 undefined。

- **&#95; TIMESTAMP &#95; &#95;** 定义为一个字符串文字，其中包含上次修改当前源文件的日期和时间，格式为 CRT [asctime](../c-runtime-library/reference/asctime-wasctime.md)函数返回的缩写的常量长度窗体，例如 `Fri 19 Aug 13:32:58 2016`。 始终定义此宏。

- **&#95;如果&#95;** 设置了[/Zl （省略默认库名称）](../build/reference/zl-omit-default-library-name.md)编译器选项，则将 VC NODEFAULTLIB 定义为1。 否则为 undefined。

- **&#95;设置&#95;默认&#95;** 的[/zc： wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)编译器选项时，WCHAR T 定义为1。 **&#95;WCHAR&#95;T&#95;定义**宏定义的但如果不具有任何值`/Zc:wchar_t-`编译器选项设置，并**wchar_t**中包含的系统标头文件中定义应用项目。 否则为 undefined。

- **&#95;WIN32**当编译目标为32位 ARM、64位 ARM、x86 或 x64 时，定义为1。 否则为 undefined。

- **&#95;WIN64**当编译目标为64位 ARM 或 x64 时，定义为1。 否则为 undefined。

- **&#95;&#95;** 设置为 1 C++时，将设置为1，同时设置了[/ZW （Windows 运行时编译）](../build/reference/zw-windows-runtime-compilation.md)和[/ld 或/LDd](../build/reference/md-mt-ld-use-run-time-library.md)编译器选项。 否则为 undefined。

编译器未预定义用于识别 ATL 或 MFC 库版本的预处理器宏。 ATL 和 MFC 库标头在内部定义这些版本宏。 它们在包含所需标头之前所做的预处理器指令中未定义。

- **&#95;ATL&#95;VER**在 @no__t 中定义 > 为编码 ATL 版本号的整数文本。

- **&#95;MFC&#95;VER**在 \<afxver_ > 中定义为对 MFC 版本号进行编码的整数文本。

## <a name="see-also"></a>请参阅

[宏 (C/C++)](../preprocessor/macros-c-cpp.md)<br/>
[预处理器运算符](../preprocessor/preprocessor-operators.md)<br/>
[预处理器指令](../preprocessor/preprocessor-directives.md)
