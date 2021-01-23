---
description: pragmaMicrosoft C/C++ ' da işlev yönergesi hakkında daha fazla bilgi edinin
title: çalışmayacaktır pragma
ms.date: 01/22/2021
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragma, function
no-loc:
- pragma
ms.openlocfilehash: 3d4b1e2f50cd118e613235271428588ac585affc
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712836"
---
# <a name="function-no-locpragma"></a>`function` pragma

Derleyiciye, bağımsız değişken listesinde belirtilen işlevlere çağrı oluşturmasını söyler pragma .

## <a name="syntax"></a>Syntax

> **`#pragma function(`***işlev1* [ **`,`** *function2* ...]**`)`**

## <a name="remarks"></a>Açıklamalar

İç işlevler normalde satır içi kod olarak oluşturulur, işlev çağrıları olarak değildir. Derleyiciye iç işlevler oluşturmasını söylemek için [veya derleyici seçeneğini kullanırsanız, işlevini açıkça bir işlev çağrısına zorlamak için kullanabilirsiniz. `intrinsic` pragma](intrinsic.md) [`/Oi`](../build/reference/oi-generate-intrinsic-functions.md) **`function`** pragma Bir kez **`function`** pragma görüldüğünde, belirtilen bir iç işlevi içeren ilk işlev tanımında geçerli olur. Efekt, kaynak dosyanın sonuna veya `intrinsic` pragma aynı iç işlevi belirten görünümün görünümüne devam eder. **`function`** pragma Genel düzeyde yalnızca bir işlev dışında kullanabilirsiniz.

İç formlara sahip işlevlerin listesi için bkz [ `intrinsic` pragma ](intrinsic.md)..

## <a name="example"></a>Örnek

```cpp
// pragma_directive_function.cpp
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// use intrinsic forms of memset and strlen
#pragma intrinsic(memset, strlen)

// Find first word break in string, and set remaining
// chars in string to specified char value.
char *set_str_after_word(char *string, char ch) {
   int i;
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */

   for(i = 0; i < len; i++) {
      if (isspace(*(string + i)))
         break;
   }

   for(; i < len; i++)
      *(string + i) = ch;

   return string;
}

// do not use strlen intrinsic
#pragma function(strlen)

// Set all chars in string to specified char value.
char *set_str(char *string, char ch) {
   // Uses intrinsic for memset, but calls strlen library function
   return (char *) memset(string, ch, strlen(string));
}

int main() {
   char *str = (char *) malloc(20 * sizeof(char));

   strcpy_s(str, sizeof("Now is the time"), "Now is the time");
   printf("str is '%s'\n", set_str_after_word(str, '*'));
   printf("str is '%s'\n", set_str(str, '!'));
}
```

```Output
str is 'Now************'
str is '!!!!!!!!!!!!!!!'
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
