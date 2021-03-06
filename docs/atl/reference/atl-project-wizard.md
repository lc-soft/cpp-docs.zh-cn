---
title: ATL 项目向导
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.atl.com.overview
helpviewer_keywords:
- ATL projects, creating
- ATL Project Wizard
ms.assetid: 564d2aaf-5b8e-4c2a-a925-ca40a283ea34
ms.openlocfilehash: 384847738f5410d750d53d3125c18f6a5256cccf
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221254"
---
# <a name="atl-project-wizard"></a>ATL 项目向导

活动模板库 (ATL) 是一套基于模板的C++类，用于简化编写小巧快捷的 COM 对象。 ATL 项目向导创建一个项目使用的结构，以包含 COM 对象。

## <a name="overview"></a>概述

此向导页描述当前[ATL 项目的应用程序设置](../../atl/reference/application-settings-atl-project-wizard.md)创建。 默认情况下，该项目具有以下设置：

- 动态链接库指定你的服务器是一个 DLL，因此一个进程内服务器。

- 特性化的指定项目使用的属性。

若要更改这些默认值，请单击**应用程序设置**ATL 项目向导页中的向导并进行更改的左侧列中。

有关默认项目设置的信息，包括选择的字符集，以及链接默认设置，请参阅[默认 ATL 项目配置](../../atl/reference/default-atl-project-configurations.md)。

创建 ATL 项目后，可以将对象或控件添加到你的项目使用视觉对象C++[代码向导](../../ide/adding-functionality-with-code-wizards-cpp.md)。 您可以进行以下类型的使用代码向导的基本 ATL 项目的增强功能：

- [将对象和控件添加到 ATL 项目](../../atl/reference/adding-objects-and-controls-to-an-atl-project.md)

- [在 ATL 项目中添加新接口](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)

- [将 COM + 1.0 组件添加到 ATL 项目](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

创建和增强的 ATL 项目时，此外，请考虑这些任务：

- [使 ATL 对象不可创建](../../atl/reference/making-an-atl-object-noncreatable.md)

- [优化编译器为 ATL 项目](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

您可以指定项目属性 (例如，[是否以静态方式链接到 CRT](../../atl/programming-with-atl-and-c-run-time-code.md)) 中[项目属性](../../build/reference/general-property-page-project.md)页上，并且可以设置[生成配置](/visualstudio/ide/understanding-build-configurations)为ATL 项目。

## <a name="see-also"></a>请参阅

[Visual Studio 项目 - C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[C++在 Visual Studio 中的项目类型](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL COM 对象基础知识](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[使用 ATL 和 C 运行时代码进行编程](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[教程](../../atl/active-template-library-atl-tutorial.md)
