---
title: /Ox （启用最大速度优化）
ms.date: 10/18/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /Ox
- /Oxs
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
ms.openlocfilehash: e39905608087425fe5a445f4ef88434d73bb2ded
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320092"
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox （启用最大速度优化）

**/Ox**编译器选项启用的优选速度的优化组合。 在某些版本的 Visual Studio IDE 和编译器帮助消息，这称为*完全优化*，但 **/Ox**编译器选项让情况下启用的速度优化选项的一个子集 **/O2**。

## <a name="syntax"></a>语法

> **/Ox**

## <a name="remarks"></a>备注

**/Ox**编译器选项启用 **/O**编译器选项，该优选速度。 **/Ox**编译器选项不包括的附加[/GF （消除重复字符串）](gf-eliminate-duplicate-strings.md)并[/Gy （启用函数级链接）](gy-enable-function-level-linking.md) 所启用的选项[/O1 或/o2 （最小化大小、 最大化速度）](o1-o2-minimize-size-maximize-speed.md)。 通过应用了其他选项 **/o1**并 **/o2**可能会导致为字符串或共享的目标地址，这可能会影响调试和严格语言合规性的函数的指针。 **/Ox**选项是启用但未包含的最大优化的简单办法 **/GF**并 **/Gy**。 有关详细信息，请参阅的说明[/GF](gf-eliminate-duplicate-strings.md)并[/Gy](gy-enable-function-level-linking.md)选项。

**/Ox**编译器选项等同于结合使用以下选项：

- [/Ob （内联函数扩展）](ob-inline-function-expansion.md)，其中的选项参数是 2 (**/ob2**)

- [/Og（全局优化）](og-global-optimizations.md)

- [/Oi（生成内部函数）](oi-generate-intrinsic-functions.md)

- [/Ot （代码速度优先）](os-ot-favor-small-code-favor-fast-code.md)

- [/Oy （框架指针省略）](oy-frame-pointer-omission.md)

**/Ox**从相互排斥：

- [/ O1 （最小大小）](o1-o2-minimize-size-maximize-speed.md)

- [/ O2 （最大化速度）](o1-o2-minimize-size-maximize-speed.md)

- [/Od（禁用（调试））](od-disable-debug.md)

可以取消的速度趋向偏差 **/Ox**编译器选项，如果指定 **/Oxs**，它结合 **/Ox**编译器选项与[/Os （优选小代码）](os-ot-favor-small-code-favor-fast-code.md)。 组合的选项优选代码大小更小。  **/Oxs**选项是完全与指定相同 **/Ox** **/Os**的选项时的顺序显示。

若要优化应用于所有可用文件级别的发布版本，我们建议您指定[/o2 （最大化速度）](o1-o2-minimize-size-maximize-speed.md)而不是 **/Ox**，并[/o1 （最小化大小）](o1-o2-minimize-size-maximize-speed.md)改为 **/Oxs**。 对于版本中的更多优化版本，还应考虑[/GL （全程序优化）](gl-whole-program-optimization.md)编译器选项和[/LTCG （链接时间代码生成）](ltcg-link-time-code-generation.md)链接器选项。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[设置C++Visual Studio 中的编译器和生成属性](../working-with-project-properties.md)。

1. 下**配置属性**，打开**C /C++**  ，然后选择**优化**属性页。

1. 修改**优化**属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>。

## <a name="see-also"></a>请参阅

[/O 选项（优化代码）](o-options-optimize-code.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器命令行语法](compiler-command-line-syntax.md)
