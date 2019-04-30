---
title: function (C/C++)
ms.date: 11/04/2016
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
ms.openlocfilehash: c57ff2053b3c1fd52474c7eb0dd598641632f789
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409934"
---
# <a name="function-cc"></a>function (C/C++)
Pragmanın bağımsız değişken listesinde belirtilen işlevlere çağrıları oluşturulacağını belirtir.

## <a name="syntax"></a>Sözdizimi

```
#pragma function( function1 [, function2, ...] )
```

## <a name="remarks"></a>Açıklamalar

Kullanırsanız `intrinsic` pragması (veya /Oi) derleyici iç işlevleri (işlev çağrıları olarak değil, satır içi kod olarak iç işlevleri oluşturulur) bildirmek için kullanabileceğiniz **işlevi** açıkça pragma bir işlev çağrısı. Bir kez bir işlev pragma görüldüğünde, belirtilen bir iç işlevi içeren ilk fonksiyon tanımında etkili olur. Kaynak dosyanın sonuna veya görünümünü etkisi devam bir `intrinsic` aynı iç işlevi belirten pragması. **İşlevi** pragması, yalnızca bir işlev dışında kullanılabilir — genel düzeyde.

İç biçimlere sahip işlevlerin bir listesi için bkz. [#pragma iç](../preprocessor/intrinsic.md).

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

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)