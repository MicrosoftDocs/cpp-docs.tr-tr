---
title: __int8, __int16, __int32, __int64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8083d37d2526820ccd75104f9ee8a748eb5d33bc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="int8-int16-int32-int64"></a>__int8, __int16, __int32, __int64
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Microsoft C/C++ özellikleri, boyutlandırılmış tamsayı türlerini destekler. 8 - 16-, 32 veya 64 bit tamsayı değişkenleri kullanarak bildirebilirsiniz **__int *** n* tür tanımlayıcısı, burada *n* 8, 16, 32 ya da 64.  
  
 Aşağıdaki örnekte, bu tür boyutlandırılmış tamsayıların her biri için bir değişken bildirilir:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 `__int8`, `__int16` ve `__int32` türleri aynı boyuttaki ANSI türleri ile eşanlamlıdır ve çeşitli platformlarda aynı şekilde çalışan taşınabilir kodlar yazmak için yararlıdır. `__int8` Veri türü olan türüyle eşanlamlı `char`, `__int16` türüyle çalışır **kısa**, ve `__int32` türüyle çalışır `int`. `__int64` Türüdür türüyle eşanlamlı `long long`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir __int gösterir*xx* parametresi tanıtılması için `int`:  
  
```  
// sized_int_types.cpp  
  
#include <stdio.h>  
  
void func(int i) {  
    printf_s("%s\n", __FUNCTION__);  
}  
  
int main()  
{  
    __int8 i8 = 100;  
    func(i8);   // no void func(__int8 i8) function  
                // __int8 will be promoted to int  
}  
```  
  
```Output  
func  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Temel türler](../cpp/fundamental-types-cpp.md)   
 [Veri Türü Aralıkları](../cpp/data-type-ranges.md)