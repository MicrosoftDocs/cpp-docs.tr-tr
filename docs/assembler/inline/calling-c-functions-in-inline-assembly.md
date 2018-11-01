---
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
ms.openlocfilehash: 4d12321cd90f596c94c2337e100663436d512107
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435353"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C İşlevlerini Çağırma

**Microsoft'a özgü**

Bir `__asm` blok, C Kitaplık yordamları da dahil olmak üzere, C işlevleri çağırabilir. Aşağıdaki örnek çağrıları `printf` yordamı:

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

İşlev bağımsız değişkenleri yığında geçirildiğinden, gerekli bağımsız değişkenler yalnızca gönderme — dize işaretçileri, önceki örnekte — işlevi çağırmadan önce. Bunlar istenen sırada yığından gelmesi için bağımsız değişkenler ters sırada itilir. C deyimi benzetmek için

```cpp
printf( format, hello, world );
```

Örnek gönderim işaretçileri `world`, `hello`, ve `format`, o sırada ve ardından aramaları `printf`.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>