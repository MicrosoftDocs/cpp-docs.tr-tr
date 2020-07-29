---
title: __int8, __int16, __int32, __int64
ms.date: 10/09/2018
f1_keywords:
- __int8_cpp
- __int16_cpp
- __int32_cpp
- __int64_cpp
- __int8
- __int16
- __int32
- __int64
- _int8
- _int16
- _int32
- _int64
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type [C++], integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
ms.openlocfilehash: 7888a282fffbaa2a23783c3875e02838fd0b1826
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227406"
---
# <a name="__int8-__int16-__int32-__int64"></a>__int8, __int16, __int32, __int64

**Microsoft'a özgü**

Microsoft C/C++ özellikleri, boyutlandırılmış tamsayı türlerini destekler. 8, 16, **`__intN`** ***`N`*** 32 veya 64 olan tür belirticisini kullanarak 8, 16-, 32-veya 64-bit tamsayı değişkenleri bildirebilirsiniz.

Aşağıdaki örnekte, bu tür boyutlandırılmış tamsayıların her biri için bir değişken bildirilir:

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

, **`__int8`** Ve türleri **`__int16`** **`__int32`** aynı boyutta olan ANSI türleri için eş anlamlılardır ve birden çok platformda aynı şekilde davranan taşınabilir kod yazmak için yararlıdır. **`__int8`** Veri türü türü ile eşanlamlıdır, türü ile eşanlamlıdır **`char`** **`__int16`** **`short`** ve **`__int32`** türüyle **`int`** eşanlamlı olur. **`__int64`** Tür, türü ile eşanlamlıdır **`long long`** .

Önceki sürümlerle uyumluluk için,,, ve,,, ve **`_int8`** **`_int16`** **`_int32`** **`_int64`** için eş anlamlılardır, **`__int8`** **`__int16`** **`__int32`** ve **`__int64`** derleyici seçeneği [ `/Za` \( devre dışı bırak ' ı devre dışı bırakır)](../build/reference/za-ze-disable-language-extensions.md) belirtilirse.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `__intN` parametresinin Yükseltilecek olduğunu gösterir **`int`** :

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

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Yerleşik türler](../cpp/fundamental-types-cpp.md)<br/>
[Veri türü aralıkları](../cpp/data-type-ranges.md)<br/>
