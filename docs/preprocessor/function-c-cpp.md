---
title: işlevi (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- function_CPP
- vc-pragma.function
dev_langs:
- C++
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 76ab5b2911d349c62ff18967e7a660cdc3589ddd
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42464543"
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
  
## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)