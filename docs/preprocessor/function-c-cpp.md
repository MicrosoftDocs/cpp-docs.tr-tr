---
title: "işlevi (C/C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- function_CPP
- vc-pragma.function
dev_langs: C++
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ff72fb22adf3b81e936e3591f2a60b2aa2e30fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="function-cc"></a>function (C/C++)
Pragma ait bağımsız değişken listesinde belirtilen işlevler çağrıları oluşturulabilir belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanırsanız **iç** pragma (veya /Oi) iç işlevler (işlev çağrılarını olarak değil, satır içi kod olarak iç işlevler oluşturulur) oluşturmak için derleyici bildirmek için kullanabileceğiniz **işlevi** pragması bir işlev çağrısı açıkça zorlamak için. İşlev pragması görülen sonra belirtilen bir iç işlevi içeren ilk işlev tanımı etkili olur. Kaynak dosyanın sonuna veya görünümünü etkisi devam bir **iç** pragma aynı iç işlevi belirtme. **İşlevi** pragma yalnızca bir işlevi dışında kullanılabilir — genel düzeyde.  
  
 İç formları işlevleri bir listesi için bkz: [#pragma iç](../preprocessor/intrinsic.md).  
  
## <a name="example"></a>Örnek  
  
```  
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