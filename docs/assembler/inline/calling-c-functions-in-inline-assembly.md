---
description: 'Hakkında daha fazla bilgi edinin: satır Içi derlemede C Işlevlerini çağırma'
title: Satır İçi Derlemede C İşlevlerini Çağırma
ms.date: 08/30/2018
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
ms.openlocfilehash: 5cdace4a909cbc49567988f85085eed5d84eadf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117997"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C İşlevlerini Çağırma

**Microsoft'a Özgü**

Bir **`__asm`** blok, c Kitaplığı yordamları dahil olmak üzere c işlevlerini çağırabilir. Aşağıdaki örnek, `printf` kitaplık yordamını çağırır:

```cpp
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

İşlev bağımsız değişkenleri yığına geçirildiğinden, işlev çağrılmadan önce gerekli bağımsız değişkenleri (önceki örnekte yer alan dize işaretçileri) göndermeniz yeterlidir. Bağımsız değişkenler ters sırada gönderilir, bu nedenle yığının istenen sırada kapalı olması gerekir. C ifadesine öykünmek için

```cpp
printf( format, hello, world );
```

örnek,, ve için `world` işaretçileri `hello` `format` Bu sırayla iter ve ardından çağırır `printf` .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
