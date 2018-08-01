---
title: __int8, __int16, __int64 __int32 türünün int | Microsoft Docs
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
ms.openlocfilehash: c1be48b2e6972ca3a291ab57dbcb1976e6a56d87
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401386"
---
# <a name="int8-int16-int32-int64"></a>__int8, __int16, __int32, __int64
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Microsoft C/C++ özellikleri, boyutlandırılmış tamsayı türlerini destekler. Kullanarak 8, 16, 32 veya 64-bit tamsayı değişkenleri bildirebilirsiniz **__int *** n* tür tanımlayıcısı, burada *n* 8, 16, 32 veya 64.  
  
 Aşağıdaki örnekte, bu tür boyutlandırılmış tamsayıların her biri için bir değişken bildirilir:  
  
```cpp 
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Türleri **__int8**, **__int16**, ve **__int32** eşanlamlıdır aynı sahip ANSI türleri, boyut ve aynı şekilde davranan taşınabilir kod yazmak için yararlıdır birden çok platformda. **__İnt8** veri türü olan türü ile eşanlamlı **char**, **__int16** türüyle eşanlamlıdır **kısa**, ve **__int32 türünün int**  türüyle eşanlamlıdır **int**. **__İnt64** türüdür türüyle eşanlamlıdır **uzun uzun**.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir __int gösteren*xx* parametresi için yükseltilecek **int**:  
  
```cpp 
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
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Temel türler](../cpp/fundamental-types-cpp.md)   
 [Veri Türü Aralıkları](../cpp/data-type-ranges.md)