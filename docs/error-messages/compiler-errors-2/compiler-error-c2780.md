---
title: "编译器错误 C2780 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2780"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2780"
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 编译器错误 C2780
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“声明”: 应输入 N 个参数，却提供了 M 个  
  
 函数模板的参数太少或太多。  
  
 下面的示例生成 C2780，并演示如何修复此错误：  
  
```  
// C2780.cpp  
template<typename T>  
void f(T, T){}  
  
int main() {  
   f(1);  // C2780  
   // try the following line instead  
   // f(1,2);  
}  
```