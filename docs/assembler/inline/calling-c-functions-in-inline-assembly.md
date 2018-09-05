---
title: Satır içi derlemede çağırma C işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
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
ms.openlocfilehash: a080c05aee58a2e6ffae17d14e99c66922aa1f17
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686693"
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