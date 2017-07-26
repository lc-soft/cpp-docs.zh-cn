---
title: "定义带有 dllexport 和 dllimport 的内联 C 函数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dllexport 特性 [C++]"
  - "dllexport 特性 [C++], 内联函数"
  - "dllimport 特性 [C++], 内联函数"
  - "内联函数 [C++], 带有 dllexport 和 dllimport"
ms.assetid: 41418f7c-1c11-470b-bb2e-1f8269a239f0
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 定义带有 dllexport 和 dllimport 的内联 C 函数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 专用**  
  
 可以定义为将函数与 `dllexport` 特性内联。  在这种情况下，将始终实例化并导出该函数，无论程序中是否有模块引用该函数。  假定该函数由另一个程序导入。  
  
 您还可以定义为将声明的函数与 **dllimport** 特性内联。  在这种情况下，函数可以展开（遵从 \/Ob（内联）编译器选项规范），但决不实例化。  具体而言，如果采用内联导入函数的地址，则返回驻留在 DLL 中的函数地址。  此行为与采用非内联导入函数的地址相同。  
  
 内联函数中的静态本地数据和字符串在 DLL 和客户端之间保持的标识与它们在单一程序（即，没有 DLL 接口的可执行文件）中保持的一样。  
  
 在提供导入的内联函数时谨慎操作。  例如，如果更新 DLL，请不要假定该客户端将使用更改后的 DLL 版本。  若要确保加载 DLL 的适当版本，请重新生成 DLL 的客户端。  
  
 **结束 Microsoft 专用**  
  
## 请参阅  
 [DLL 导入和导出函数](../c-language/dll-import-and-export-functions.md)