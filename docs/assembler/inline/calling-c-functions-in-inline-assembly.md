---
title: Satır içi derlemede çağırma C işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3f6d03ba77c7a4cdb3478a1bfe8729019dea002
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
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