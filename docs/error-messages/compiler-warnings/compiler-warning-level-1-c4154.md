---
title: "编译器警告（等级 1）C4154 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4154"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4154"
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 编译器警告（等级 1）C4154
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

删除数组表达式；转换到提供的指针  
  
 不能对数组使用 `delete`，因此编译器将数组转换为指针。  
  
## 示例  
  
```  
// C4154.cpp  
// compile with: /c /W1  
int main() {  
   int array[ 10 ];  
   delete array;   // C4154 can't delete stack object  
  
   int *parray2 = new int [10];  
   int (&array2)[10] = (int(&)[10]) parray2;  
   delete [] array2;   // C4154  
  
   // try the following line instead  
   delete [] &array2;  
}  
```