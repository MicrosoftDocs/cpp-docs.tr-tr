---
description: 'Hakkında daha fazla bilgi edinin: __int8, __int16, __int32, __int64'
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
ms.openlocfilehash: 8dddb8dc63b8aa9898b78ee02ea2dc904b362442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332518"
---
# <a name="__int8-__int16-__int32-__int64"></a>__int8, __int16, __int32, __int64

**Microsoft'a özgü**

Microsoft C/C++ özellikleri, boyutlandırılmış tamsayı türlerini destekler. Tür belirticisini kullanarak 8, 16, 32-veya 64-bit tamsayı değişkenleri bildirebilirsiniz **`__intN`** ; burada * *_`N`_* _, 8, 16, 32 veya 64.

Aşağıdaki örnekte, bu tür boyutlandırılmış tamsayıların her biri için bir değişken bildirilir:

```cpp
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

_ * `__int8` * *, Ve türleri **`__int16`** **`__int32`** aynı boyutta olan ANSI türleri için eş anlamlılardır ve birden çok platformda aynı şekilde davranan taşınabilir kod yazmak için faydalıdır. **`__int8`** Veri türü türü ile eşanlamlıdır, türü ile eşanlamlıdır **`char`** **`__int16`** **`short`** ve **`__int32`** türüyle **`int`** eşanlamlı olur. **`__int64`** Tür, türü ile eşanlamlıdır **`long long`** .

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
