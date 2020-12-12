---
description: 'Daha fazla bilgi edinin: işlev pragması'
title: işlev pragması
ms.date: 08/29/2019
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
ms.openlocfilehash: 77b215458f9ffdb6be605d0ae4b239451a1fe1bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269308"
---
# <a name="function-pragma"></a>işlev pragması

Derleyiciye, pragmanın bağımsız değişken listesinde belirtilen işlevlere çağrı oluşturmasını söyler.

## <a name="syntax"></a>Syntax

> **#pragma işlevi (** *işlev1* [ **,** *function2* ...] **)**

## <a name="remarks"></a>Açıklamalar

İç işlevler normalde satır içi kod olarak oluşturulur, işlev çağrıları olarak değildir. Derleyiciye iç işlevler oluşturmasını söylemek için [iç pragma](intrinsic.md) veya [/Oi](../build/reference/oi-generate-intrinsic-functions.md) derleyici seçeneğini kullanırsanız, işlev çağrısını açıkça zorlamak için pragma **işlevini** kullanabilirsiniz. Bir **işlev** pragması görüldüğünde, belirtilen bir iç işlevi içeren ilk işlev tanımında geçerli olur. Efekt kaynak dosyanın sonuna veya `intrinsic` aynı iç işlevi belirten bir pragma görünümüne devam eder. Yalnızca pragma **işlevini** bir işlevin dışında, genel düzeyde kullanabilirsiniz.

İç formlara sahip işlevlerin listesi için bkz. [iç pragma](intrinsic.md).

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

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
