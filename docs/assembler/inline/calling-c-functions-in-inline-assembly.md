---
title: "Satır içi derlemede çağırma C işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d337e7a276318d6a1d39087b6809e3f62838cad8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C İşlevlerini Çağırma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bir `__asm` blok C Kitaplık yordamları dahil C işlevleri çağırabilir. Aşağıdaki örnek çağrıları `printf` kitaplık yordamı:  
  
```  
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp  
// processor: x86  
#include <stdio.h>  
  
char format[] = "%s %s\n";  
char hello[] = "Hello";  
char world[] = "world";  
int main( void )  
{  
   __asm  
   {  
      mov  eax, offset world  
      push eax  
      mov  eax, offset hello  
      push eax  
      mov  eax, offset format  
      push eax  
      call printf  
      //clean up the stack so that main can exit cleanly  
      //use the unused register ebx to do the cleanup  
      pop  ebx  
      pop  ebx  
      pop  ebx  
   }  
}  
```  
  
 İşlev bağımsız değişkenleri yığında geçirildiğinden, gerekli bağımsız değişken yalnızca push — dize önceki örnekte işaretçileri — işlevi çağrılmadan önce. Bağımsız değişkenler, istenen sırada yığından geldikleri şekilde ters sırada atılır. C deyimi benzetmek için  
  
```  
printf( format, hello, world );  
```  
  
 Örnek işaretçileri iter `world`, `hello`, ve `format`, o sırada ve ardından çağrıları `printf`.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)