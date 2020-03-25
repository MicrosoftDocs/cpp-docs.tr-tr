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
ms.openlocfilehash: 94bbfda3a5fd15885f3d8276d506541418a9489f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169597"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C İşlevlerini Çağırma

**Microsoft 'a özgü**

`__asm` bloğu C Kitaplığı yordamları dahil olmak üzere C işlevlerini çağırabilir. Aşağıdaki örnek `printf` kitaplığı yordamını çağırır:

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

örnek, `world`, `hello`ve `format`işaretçileri bu sırayla iter ve sonra `printf`çağırır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
